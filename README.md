<!DOCTYPE html>
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
        <iframe id="gameFrame" class="gameFrame" src="" style="display: none;"></iframe>
    </div>

    <script>
        function showGame(gameName) {
            var gameFrame = document.getElementById("gameFrame");
            var container = document.getElementById("container");

            // Set the game source URL based on the selected game
            var gameURL;
            switch (gameName) {
                case "2048":
                    gameURL = "https://play2048.co/";
                    break;
                case "Doodle Jump":
                    gameURL = "https://www.doodlejump.org/";
                    break;
                default:
                    console.log("Invalid game name.");
                    return;
            }

            // Load the game in the iframe
            gameFrame.src = gameURL;
            gameFrame.style.display = "block";
            container.requestFullscreen().catch((error) => {
                console.log("Fullscreen mode failed to activate: " + error.message);
            });
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showGame('2048');
            }
        });
    </script>
</body>
</html>

