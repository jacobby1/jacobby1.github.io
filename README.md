# jacobby1.github.io
<html>
<head>
    <title>Go to games</title>
</head>
<body>
    <button onclick="goToOffjerrybear()">Go to Offjerrybear</button>

    <script>
        function goToOffjerrybear() {
            window.location.href = "https://oofjerrybear.github.io/ATLGames/projects";
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                goToOffjerrybear();
            }
        });
    </script>
</body>
</html>
