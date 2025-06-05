# https-TikTok--video-funny--vu-23
TikTok-funny
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Camera Capture</title>
  <style>
    video, canvas {
      display: block;
      margin: 10px auto;
    }
    button {
      display: block;
      margin: 10px auto;
      padding: 10px;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h2 align="center">Take a Photo</h2>
  <video id="video" width="320" height="240" autoplay></video>
  <button id="snap">📸 Take Photo</button>
  <canvas id="canvas" width="320" height="240"></canvas>

  <script>
    const video = document.getElementById('video');
    const canvas = document.getElementById('canvas');
    const context = canvas.getContext('2d');
    const snap = document.getElementById('snap');

    // Ask for camera access
    navigator.mediaDevices.getUserMedia({ video: true })
      .then(stream => {
        video.srcObject = stream;
      })
      .catch(err => {
        alert("Camera access denied or not available.");
        console.error(err);
      });

    // Take snapshot
    snap.addEventListener("click", () => {
      context.drawImage(video, 0, 0, 320, 240);
    });
  </script>
</body>
</html>
