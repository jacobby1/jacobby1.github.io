# jacobby1.github.io
<html>
<head>
    <title>Show Games</title>
</head>
<body>
    <button onclick="openGame('https://play2048.co')">2048</button>
    <button onclick="openGame('https://www.doodlejump.org')">Doodle Jump</button>
    <br><br>

    <script>
        function openGame(gameURL) {
            window.open(gameURL, '_blank');
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                openGame('https://play2048.co');
            }
        });
    </script>
</body>
</html>
