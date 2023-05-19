<html>
<head>
    <title>Show Games</title>
    <style>
        .gameFrame {
            width: 100%;
            height: 100%;
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

            // Hide the game frame and show the canvas
            gameCanvas.style.display = "block";
            container.style.display = "none";

            // Start the fishing game
            if (gameName === "Generic Fishing Game") {
                startGenericFishingGame();
            }
        }

        function startGenericFishingGame() {
            // Add your implementation for the generic fishing game here
            // Use JavaScript to create the game logic, graphics, and interaction
        }
    </script>
</body>
</html>
