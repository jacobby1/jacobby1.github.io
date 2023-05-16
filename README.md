# jacobby1.github.io
<html>
<head>
    <title>Show Picture</title>
    <script>
        function showPicture() {
            document.getElementById("picture").style.display = "block";
        }
    </script>
</head>
<body>
    <button onclick="showPicture()">Show Picture</button>
    <br><br>
    <img id="picture" src="path/to/your/image.jpg" style="display: none;">
</body>
</html>
