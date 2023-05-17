# jacobby1.github.io
<html>
<head>
    <title>Show Cookie Clicker</title>
</head>
<body>
    <button onclick="showCookieClicker()">Show Cookie Clicker</button>
    <br><br>
    <iframe id="cookieClickerFrame" src="https://orteil.dashnet.org/cookieclicker/" width="800" height="600" style="display: none;"></iframe>

    <script>
        function showCookieClicker() {
            var iframe = document.getElementById("cookieClickerFrame");
            iframe.style.display = "block";
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showCookieClicker();
            }
        });
    </script>
</body>
</html>
