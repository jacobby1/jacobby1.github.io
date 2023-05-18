# jacobby1.github.io
<html>
<head>
    <title>Go to 2048</title>
</head>
<body>
    <button onclick="goTo2048()">2048</button>

    <script>
        function goTo2048() {
            window.location.href = "https://play2048.co/";
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                goTo2048();
            }
        });
    </script>
</body>
</html>
