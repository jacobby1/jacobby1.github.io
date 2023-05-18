# jacobby1.github.io
<html>
<head>
    <title>Show Games</title>
    <style>
        .gameFrame {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <button onclick="showGame('2048')">2048</button>
    <button onclick="showGame('Doodle Jump')">Doodle Jump</button>
    <br><br>
    <div id="container">
        <iframe id="gameFrame" class="gameFrame" src="" style="display: none;"></iframe>
    </div>

    <script>
        function showGame(gameName) {
            var gameFrame = document.getElementById("gameFrame");
            var container = document.getElementById("container");

            // Set the game source URL based on the selected game
            var gameURL;
            switch (gameName) {
                case "2048":
                    gameURL = "https://github.com/gabrielecirulli/2048.git";
                    break;
                case "Doodle Jump":
                    gameURL = "https://github.com/photonstorm/phaser3-doodle-jump.git";
                    break;
                default:
                    console.log("Invalid game name.");
                    return;
            }

            // Clone the game repository and load the game in the iframe
            var clonedGameURL = "cloned_games/" + gameName;
            cloneGameRepository(gameURL, clonedGameURL, function(success) {
                if (success) {
                    gameFrame.src = clonedGameURL;
                    gameFrame.style.display = "block";
                    container.requestFullscreen().catch((error) => {
                        console.log("Fullscreen mode failed to activate: " + error.message);
                    });
                } else {
                    console.log("Failed to clone the game repository.");
                }
            });
        }

        function cloneGameRepository(repoURL, destinationPath, callback) {
            var xhr = new XMLHttpRequest();
            xhr.open("GET", repoURL + "/archive/refs/heads/main.zip", true);
            xhr.responseType = "blob";
            xhr.onload = function() {
                if (xhr.status === 200) {
                    var blob = new Blob([xhr.response], { type: "application/zip" });
                    saveAs(blob, "game.zip");

                    var unzipper = new JSZip();
                    unzipper.loadAsync(blob).then(function(zip) {
                        zip.forEach(function(relativePath, zipEntry) {
                            if (relativePath.startsWith("game/")) {
                                var newRelativePath = relativePath.replace("game/", "");
                                if (zipEntry.dir) {
                                    unzipper.folder(destinationPath + "/" + newRelativePath);
                                } else {
                                    zipEntry.async("blob").then(function(content) {
                                        unzipper.file(destinationPath + "/" + newRelativePath, content);
                                    });
                                }
                            }
                        });

                        unzipper.generateAsync({ type: "blob" }).then(function(content) {
                            saveAs(content, "game.zip");
                            callback(true);
                        });
                    });
                } else {
                    callback(false);
                }
            };
            xhr.send();
        }

        document.addEventListener("keydown", function(event) {
            if (event.code === "Space") {
                showGame('2048');
            }
        });
    </script>
</body>
</html>
