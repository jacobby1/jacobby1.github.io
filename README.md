# jacobby1.github.io
<html>
<head>
    <title>Show Cookie Clicker</title>
    <style>
        #cookieClickerFrame {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <button onclick="showCookieClicker()">Show Cookie Clicker</button>
    <br><br>
    <div id="container">
        <iframe id="cookieClickerFrame" src="https://orteil.dashnet.org/cookieclicker/" style="display: none;"></iframe>
    </div>

    <script>
        function showCookieClicker() {
            var iframe = document.getElementById("cookieClickerFrame");
            var container = document.getElementById("container");

            // Toggle fullscreen mode
            if (!document.fullscreenElement) {
                container.requestFullscreen().then(() => {
                    iframe.style.display = "block";
                }).catch((error) => {
                    console.log("Fullscreen mode failed to activate: " + error.message);
                });
            } else {
                document.exitFullscreen().then(() => {
                    iframe.style.display = "none";
                }).catch((error) => {
                    console.log("Fullscreen mode failed to exit: " + error.message);
                });
            }
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showCookieClicker();
            }
        });
    </script>
</body>
</html>
