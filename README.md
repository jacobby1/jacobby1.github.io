<html>
<head>
    <title>Show Games</title>
    <style>
        .gameContainer {
            display: none;
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
        <div id="game2048" class="gameContainer">
            <iframe id="game2048Frame" class="gameFrame" src="" style="width: 100%; height: 100%;"></iframe>
        </div>
        <div id="gameDoodleJump" class="gameContainer">
            <iframe id="gameDoodleJumpFrame" class="gameFrame" src="" style="width: 100%; height: 100%;"></iframe>
        </div>
    </div>

    <script>
        function showGame(gameName) {
            var gameContainer = document.getElementById("container");

            // Hide all game containers
            var gameContainers = gameContainer.getElementsByClassName("gameContainer");
            for (var i = 0; i < gameContainers.length; i++) {
                gameContainers[i].style.display = "none";
            }

            // Show the selected game container
            var selectedGameContainer = document.getElementById("game" + gameName.replace(" ", ""));
            selectedGameContainer.style.display = "block";

            // Set the source URL for the selected game
            var gameFrame;
            switch (gameName) {
                case "2048":
                    gameFrame = document.getElementById("game2048Frame");
                    gameFrame.src = "https://your-2048-game-url.com";
                    break;
                case "Doodle Jump":
                    gameFrame = document.getElementById("gameDoodleJumpFrame");
                    gameFrame.src = "https://your-doodle-jump-game-url.com";
                    break;
                default:
                    console.log("Invalid game name.");
                    return;
            }
        }
    </script>
</body>
</html>
