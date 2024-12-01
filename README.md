!DOCTYPE html>
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
          
