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

            // Start the selected game
            switch (gameName) {
                case "2048":
                    start2048Game(gameCanvas);
                    break;
                case "Doodle Jump":
                    startDoodleJumpGame(gameCanvas);
                    break;
                default:
                    console.log("Invalid game name.");
                    break;
            }
        }

        function start2048Game(canvas) {
            // Add your implementation for the 2048 game here
            // Use JavaScript to create the game logic, graphics, and interaction on the canvas
        }

        function startDoodleJumpGame(canvas) {
            // Add your implementation for the Doodle Jump game here
            // Use JavaScript to create the game logic, graphics, and interaction on the canvas
        }
    </script>
</body>
</html>
