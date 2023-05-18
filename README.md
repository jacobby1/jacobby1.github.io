# jacobby1.github.io
<html>
<head>
    <title>Show Games</title>
    <style>
        #gameFrame2048,
        #gameFrameDoodleJump {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <button onclick="show2048()">2048</button>
    <button onclick="showDoodleJump()">Doodle Jump</button>
    <br><br>
    <div id="container">
        <iframe id="gameFrame2048" src="https://play2048.co/" style="display: none;"></iframe>
        <iframe id="gameFrameDoodleJump" src="https://www.doodlejump.org/" style="display: none;"></iframe>
    </div>

    <script>
        function show2048() {
            var gameFrame2048 = document.getElementById("gameFrame2048");
            var gameFrameDoodleJump = document.getElementById("gameFrameDoodleJump");
            var container = document.getElementById("container");

            // Toggle visibility and fullscreen mode
            if (gameFrame2048.style.display === "none") {
                gameFrameDoodleJump.style.display = "none";
                gameFrame2048.style.display = "block";
                container.requestFullscreen().catch((error) => {
                    console.log("Fullscreen mode failed to activate: " + error.message);
                });
            } else {
                gameFrame2048.style.display = "none";
                document.exitFullscreen().catch((error) => {
                    console.log("Fullscreen mode failed to exit: " + error.message);
                });
            }
        }

        function showDoodleJump() {
            var gameFrame2048 = document.getElementById("gameFrame2048");
            var gameFrameDoodleJump = document.getElementById("gameFrameDoodleJump");
            var container = document.getElementById("container");

            // Toggle visibility and fullscreen mode
            if (gameFrameDoodleJump.style.display === "none") {
                gameFrame2048.style.display = "none";
                gameFrameDoodleJump.style.display = "block";
                container.requestFullscreen().catch((error) => {
                    console.log("Fullscreen mode failed to activate: " + error.message);
                });
            } else {
                gameFrameDoodleJump.style.display = "none";
                document.exitFullscreen().catch((error) => {
                    console.log("Fullscreen mode failed to exit: " + error.message);
                });
            }
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                if (document.getElementById("gameFrame2048").style.display === "block") {
                    showDoodleJump();
                } else {
                    show2048();
                }
            }
        });
    </script>
</body>
</html>
