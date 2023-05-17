# jacobby1.github.io
<html>
<head>
    <title>Clone Cookie Clicker</title>
</head>
<body>
    <button onclick="cloneCookieClicker()">Cookie Clicker</button>

    <script>
        function cloneCookieClicker() {
            window.location.href = "https://github.com/orteil/cookieclicker.git";
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                cloneCookieClicker();
            }
        });
    </script>
</body>
</html>
