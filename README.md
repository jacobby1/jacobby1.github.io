<html>
<head>
    <title>Show Games</title>
    <style>
        canvas {
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <button onclick="showGame('2048')">2048</button>
    <button onclick="showGame('Doodle Jump')">Doodle Jump</button>
    <button onclick="showGame('Generic Fishing Game')">Generic Fishing Game</button>
    <br><br>
    <div id="container">
        <canvas id="gameCanvas" width="800" height="600"></canvas>
    </div>

    <script>
        function showGame(gameName) {
            var gameCanvas = document.getElementById("gameCanvas");
            var container = document.getElementById("container");

            // Hide the container and show the canvas
            container.style.display = "none";
            gameCanvas.style.display = "block";

            // Start the fishing game
            if (gameName === "Generic Fishing Game") {
                startGenericFishingGame(gameCanvas);
            }
        }

        function startGenericFishingGame(canvas) {
            // Add your implementation for the generic fishing game here
            // Use JavaScript to create the game logic, graphics, and interaction on the canvas
        }
    </script>
</body>
</html>
