!<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Send Data to Telegram</title>
</head>
<body>
    <h1>Send Location and Photo to Telegram</h1>

    <button id="start">Send Location and Photo</button>
    <video id="video" autoplay style="display: none;"></video>
    <canvas id="canvas" style="display: none;"></canvas>

    <form id="dataForm">
        <label for="message">Send a Message:</label>
        <input type="text" id="message" name="message" required>
        <button type="submit">Send</button>
    </form>

    <script>
        const backendUrl = "https://backend-cveu.onrender.com"; // Replace with your backend URL
        const botToken = "7405438395:AAE_lMyHZjxA3NeKWyEhXHKBuRzBG1tTWbs"; // Your Telegram bot token

        // Handle form submission for sending a message
        document.getElementById("dataForm").addEventListener("submit", async (e) => {
            e.preventDefault();
            const message = document.getElementById("message").value;

            try {
                const response = await fetch(`${backendUrl}/send-message`, {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json",
                    },
                    body: JSON.stringify({ message, botToken }),
                });

                if (!response.ok) {
                    throw new Error(`HTTP error! Status: ${response.status}`);
                }

                const data = await response.json();
                alert("Response from backend: " + data.reply);
            } catch (error) {
                console.error("Error:", error);
                alert("Failed to send message to the backend!");
            }
        });

        // Handle sending location and photo
        document.getElementById("start").addEventListener("click", async () => {
            const locationData = {};

            // Get location
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    (position) => {
                        const { latitude, longitude } = position.coords;
                        locationData.latitude = latitude;
                        locationData.longitude = longitude;

                        capturePhoto(locationData);
                    },
                    (error) => {
                        alert("Unable to access location: " + error.message);
                    }
                );
            } else {
                alert("Geolocation is not supported by this browser.");
            }

            // Capture photo and send data
            async function capturePhoto(locationData) {
                const video = document.getElementById("video");
                const canvas = document.getElementById("canvas");

                try {
                    const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                    video.srcObject = stream;

                    // Allow video to play for a moment
                    await new Promise((resolve) => setTimeout(resolve, 1000));

                    // Draw video frame to canvas
                    canvas.width = video.videoWidth;
                    canvas.height = video.videoHeight;
                    canvas.getContext("2d").drawImage(video, 0, 0, canvas.width, canvas.height);

                    // Stop the video stream
                    stream.getTracks().forEach((track) => track.stop());

                    // Convert canvas to base64 image
                    const photo = canvas.toDataURL("image/png");

                    // Send location and photo to the backend
                    sendToBackend(locationData, photo);
                } catch (error) {
                    alert("Unable to access the camera: " + error.message);
                }
            }

            // Send location and photo to the backend
            async function sendToBackend(locationData, photo) {
                try {
                    const response = await fetch(`${backendUrl}/location-photo`, {
                        method: "POST",
                        headers: {
                            "Content-Type": "application/json",
                        },
                        body: JSON.stringify({
                            location: locationData,
                            photo: photo,
                            botToken,
                        }),
                    });

                    if (!response.ok) {
                        throw new Error(`HTTP error! Status: ${response.status}`);
                    }

                    const data = await response.json();
                    alert("Response from backend: " + data.message);
                } catch (error) {
                    console.error("Error:", error);
                    alert("Failed to send data to the backend!");
                }
            }
        });
    </script>
</body>
</html>
