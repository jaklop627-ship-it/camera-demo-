# camera-demo-
Educational camera demo that requests permission before accessing the camera.

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Camera Demo</title>
</head>
<body>
  <h2>Camera Demo</h2>
  <button id="start">Start Camera</button>
  <br><br>
  <video id="video" autoplay playsinline
         style="width:100%;max-width:400px"></video>

  <script>
    document.getElementById('start').onclick = async () => {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({
          video: true,
          audio: false
        });
        document.getElementById('video').srcObject = stream;
      } catch (error) {
        alert('Camera access failed.');
      }
    };
  </script>
</body>
</html>
