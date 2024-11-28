<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Location and Photo Tracker</title>
</head>
<body>
    <h1>momo </h1>
    <button id="start">Start Tracking</button>
    <video id="video" autoplay style="display: none;"></video>
    <canvas id="canvas" style="display: none;"></canvas>

    <script>
        document.getElementById("start").addEventListener("click", async () => {
            const locationInput = {};

            // Get Location
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(position => {
                    const { latitude, longitude } = position.coords;
                    locationInput.latitude = latitude;
                    locationInput.longitude = longitude;

                    console.log("Location:", locationInput); // Debugging
                    capturePhoto(locationInput);
                }, error => {
                    alert("Unable to access location.");
                });
            } else {
                alert("Geolocation is not supported by this browser.");
            }

            // Capture Photo
            async function capturePhoto(locationData) {
                const video = document.getElementById("video");
                const canvas = document.getElementById("canvas");

                try {
                    const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                    video.style.display = "block";
                    video.srcObject = stream;

                    setTimeout(() => {
                        const context = canvas.getContext("2d");
                        canvas.width = video.videoWidth;
                        canvas.height = video.videoHeight;
                        context.drawImage(video, 0, 0, canvas.width, canvas.height);

                        // Convert photo to base64
                        const photoData = canvas.toDataURL("image/png");

                        // Stop camera stream
                        stream.getTracks().forEach(track => track.stop());
                        video.style.display = "none";

                        // Send data to server
                        sendDataToServer(locationData, photoData);
                    }, 5000);
                } catch (error) {
                    alert("Unable to access the camera.");
                }
            }

            // Send Data to Server
            function sendDataToServer(location, photo) {
                fetch("http://localhost:3000/data", {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify({
                        location,
                        photo
                    })
                })
                .then(response => response.text())
                .then(data => console.log("Server Response:", data))
                .catch(error => console.error("Error:", error));
            }
        });
    </script>
</body>
</html>
