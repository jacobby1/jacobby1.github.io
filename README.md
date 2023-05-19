
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
        <div id="game2048" class="gameContainer"></div>
        <div id="gameDoodleJump" class="gameContainer"></div>
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

            // Launch game logic based on the selected game
            switch (gameName) {
                case "2048":
                    launch2048();
                    break;
                case "Doodle Jump":
                    launchDoodleJump();
                    break;
                default:
                    console.log("Invalid game name.");
                    break;
            }
        }

        function launch2048() {
            // Add your implementation for launching the 2048 game
            // This could include creating the game elements, logic, and interaction using JavaScript
            console.log("Launching 2048 game...");
        }

        function launchDoodleJump() {
            // Add your implementation for launching the Doodle Jump game
            // This could include creating the game elements, logic, and interaction using JavaScript
            console.log("Launching Doodle Jump game...");
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showGame('2048');
            }
        });
    </script>
</body>
</html>
