<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather Forecast</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            color: #333;
            text-align: center;
            padding: 50px;
        }
        h1 {
            color: #4CAF50;
        }
        input {
            padding: 10px;
            width: 300px;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            margin-left: 10px;
            font-size: 16px;
            cursor: pointer;
        }
        .loading {
            font-size: 20px;
            color: #ff9800;
            display: none;
        }
        .response {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
        .emoji {
            font-size: 30px;
        }
    </style>
</head>
<body>
    <h1>Weather Forecast</h1>
    <p>Type your weather query below:</p>
    <input type="text" id="query" placeholder="How's the weather today?">
    <button onclick="getWeather()">Check Weather</button>
    <div id="loadingMessage" class="loading">Getting request, determining weather outside for today, gathering information...</div>
    <div id="response" class="response"></div>
    <script>
        function getWeather() {
            const query = document.getElementById("query").value.toLowerCase();
            const loadingMessage = document.getElementById("loadingMessage");
            const response = document.getElementById("response");
            loadingMessage.style.display = "block";
            response.innerHTML = '';
            setTimeout(() => {
                loadingMessage.style.display = "none";
                if (query.includes("weather") || query.includes("how's the weather")) {
                    response.innerHTML = "Just look outside the window bro <span class='emoji'>😊</span>";
                } else {
                    response.innerHTML = "I couldn't quite understand that. Try asking about the weather!";
                }
            }, 3000);
        }
    </script>
</body>
</html>