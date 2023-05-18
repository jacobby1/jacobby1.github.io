# jacobby1.github.io
<html>
<head>
    <title>Show 2048</title>
    <style>
        #gameFrame {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <button onclick="show2048()">2048</button>
    <br><br>
    <div id="container">
        <iframe id="gameFrame" src="https://play2048.co/" style="display: none;"></iframe>
    </div>

    <script>
        function show2048() {
            var gameFrame = document.getElementById("gameFrame");
            var container = document.getElementById("container");

            // Toggle visibility of the game frame
            if (gameFrame.style.display === "none") {
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

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                show2048();
            }
        });
    </script>
</body>
</html>
