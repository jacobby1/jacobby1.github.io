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
            <h2>2048 Game</h2>
            <div id="game2048Container"></div>
        </div>
        <div id="gameDoodleJump" class="gameContainer">
            <h2>Doodle Jump Game</h2>
            <div id="gameDoodleJumpContainer"></div>
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

            // Initialize the game based on the selected game name
            switch (gameName) {
                case "2048":
                    initialize2048();
                    break;
                case "Doodle Jump":
                    initializeDoodleJump();
                    break;
                default:
                    console.log("Invalid game name.");
            }
        }

        function initialize2048() {
            var game2048Container = document.getElementById("game2048Container");

            // Add your implementation for launching and initializing the 2048 game here
            // Example: game2048Container.innerHTML = "<canvas id='game2048Canvas'></canvas>";
            //          // Initialize the game logic using JavaScript
            //          var canvas = document.getElementById("game2048Canvas");
            //          // ... rest of the game initialization code
        }

        function initializeDoodleJump() {
            var gameDoodleJumpContainer = document.getElementById("gameDoodleJumpContainer");

            // Add your implementation for launching and initializing the Doodle Jump game here
            // Example: gameDoodleJumpContainer.innerHTML = "<canvas id='gameDoodleJumpCanvas'></canvas>";
            //          // Initialize the game logic using JavaScript
            //          var canvas = document.getElementById("gameDoodleJumpCanvas");
            //          // ... rest of the game initialization code
        }
    </script>
</body>
</html>
