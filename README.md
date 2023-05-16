# jacobby1.github.io
<html>
<head>
    <title>Go to Offjerrybear</title>
</head>
<body>
    <button onclick="goToOffjerrybear()">Go to Offjerrybear</button>

    <script>
        function goToOffjerrybear() {
            window.location.href = "https://www.atlgames.com/offjerrybear/";
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                goToOffjerrybear();
            }
        });
    </script>
</body>
</html>
