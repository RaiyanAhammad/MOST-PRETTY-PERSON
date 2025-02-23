[U<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>See the World's Most Beautiful Person</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>See the World's Most Beautiful Person</h1>
        <div id="step1">
            <label for="name">Enter the full name:</label>
            <input type="text" id="name" placeholder="Full Name">
            <button onclick="checkName()">Submit</button>
        </div>
        <div id="step2" style="display: none;">
            <button onclick="showCamera()">Tap to see the prettiest Human ever</button>
        </div>
        <div id="camera" style="display: none;">
            <video id="video" width="320" height="240" autoplay></video>
            <p id="beautifulText" style="display: none;">You are the most beautiful human on the planet ❤</p>
            <button onclick="goHome()">Go to Home</button>
        </div>
        <p id="noEntry" style="display: none; color: red;">No entry</p>
    </div>
    <script src="script.js"></script>
</body>
</html>
  body {
    font-family: 'Arial', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    color: #333;
}

.container {
    text-align: center;
    background: white;
    padding: 30px;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    max-width: 400px;
    width: 100%;
}

h1 {
    font-size: 24px;
    margin-bottom: 20px;
    color: #ff6f61;
}

label {
    font-size: 16px;
    display: block;
    margin-bottom: 10px;
}

input {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
}

button {
    background: #ff6f61;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s ease;
}

button:hover {
    background: #ff4a3d;
}

#camera {
    margin-top: 20px;
}

video {
    border-radius: 10px;
    border: 2px solid #ff6f61;
    margin-bottom: 20px;
}

#beautifulText {
    font-size: 20px;
    font-weight: bold;
    color: #ff6f61;
    margin-top: 10px;
}

#noEntry {
    font-size: 16px;
    font-weight: bold;
}ml>ploading mbp.html…]()
function checkName() {
    const name = document.getElementById('name').value.trim();
    const allowedNames = ["Anjum Afra", "Anjum Afra Nadia"];

    if (allowedNames.includes(name)) {
        document.getElementById('step1').style.display = 'none';
        document.getElementById('step2').style.display = 'block';
        document.getElementById('noEntry').style.display = 'none';
    } else {
        document.getElementById('noEntry').style.display = 'block';
    }
}

function showCamera() {
    document.getElementById('step2').style.display = 'none';
    document.getElementById('camera').style.display = 'block';

    navigator.mediaDevices.getUserMedia({ video: true })
        .then(function(stream) {
            const video = document.getElementById('video');
            video.srcObject = stream;
            video.onplaying = function() {
                document.getElementById('beautifulText').style.display = 'block';
            };
        })
        .catch(function(err) {
            console.error("Error accessing the camera: ", err);
        });
}

function goHome() {
    document.getElementById('camera').style.display = 'none';
    document.getElementById('step1').style.display = 'block';
    document.getElementById('beautifulText').style.display = 'none';
    const video = document.getElementById('video');
    if (video.srcObject) {
        video.srcObject.getTracks().forEach(track => track.stop());
    }
}oading mbp.js…]()


