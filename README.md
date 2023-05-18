# jacobby1.github.io
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
    <br><br>
    <div id="container">
        <iframe id="gameFrame2048" class="gameFrame" src="https://play2048.co/" style="display: none;"></iframe>
        <iframe id="gameFrameDoodleJump" class="gameFrame" src="https://www.doodlejump.org/" style="display: none;"></iframe>
    </div>

    <script>
        function showGame(gameName) {
            var gameFrame2048 = document.getElementById("gameFrame2048");
            var gameFrameDoodleJump = document.getElementById("gameFrameDoodleJump");
            var container = document.getElementById("container");

            // Toggle visibility and fullscreen mode based on the selected game
            switch (gameName) {
                case "2048":
                    toggleGame(gameFrame2048);
                    break;
                case "Doodle Jump":
                    toggleGame(gameFrameDoodleJump);
                    break;
                default:
                    console.log("Invalid game name.");
                    break;
            }

            // Toggle visibility and fullscreen mode for the selected game
            function toggleGame(gameFrame) {
                if (gameFrame.style.display === "none") {
                    hideAllGames();
                    gameFrame.style.display = "block";
                    container.requestFullscreen().catch((error) => {
                        console.log("Fullscreen mode failed to activate: " + error.message);
                    });
                } else {
                    gameFrame.style.display = "none";
                    document.exitFullscreen().catch((error) => {
                        console.log("Fullscreen mode failed to exit: " + error.message);
                    });
                }
            }

            // Hide all game frames
            function hideAllGames() {
                gameFrame2048.style.display = "none";
                gameFrameDoodleJump.style.display = "none";
            }
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showGame('2048');
            }
        });
    </script>
</body>
</html>
