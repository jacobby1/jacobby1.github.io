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
            <!-- Insert your 2048 game implementation here -->
            <!-- Example: -->
            <h1>2048 Game Implementation</h1>
            <!-- Replace this with your actual 2048 game code -->
            <p>Game code goes here</p>
        </div>
        <div id="gameDoodleJump" class="gameContainer">
            <!-- Insert your Doodle Jump game implementation here -->
            <!-- Example: -->
            <h1>Doodle Jump Game Implementation</h1>
            <!-- Replace this with your actual Doodle Jump game code -->
            <p>Game code goes here</p>
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
        }
    </script>
</body>
</html>
