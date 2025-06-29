<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Flor Animada Completa</title>
  <style>
    body { margin: 0; background-color: black; }
    canvas { display: block; margin: auto; background-color: black; }
  </style>
</head>
<body>
  <canvas id="canvas" width="600" height="600"></canvas>
  <script>
    const canvas = document.getElementById("canvas");
    const ctx = canvas.getContext("2d");
    let centerX = canvas.width / 2;
    let centerY = canvas.height / 2;
    let frame = 0;

    function drawPetal(angleOffset) {
      ctx.save();
      ctx.translate(centerX, centerY);
      ctx.rotate((angleOffset + frame) * Math.PI / 180);
      ctx.beginPath();
      ctx.moveTo(0, 0);
      ctx.bezierCurveTo(20, -40, 80, -40, 80, 0);
      ctx.bezierCurveTo(80, 40, 20, 40, 0, 0);
      ctx.fillStyle = "yellow";
      ctx.strokeStyle = "red";
      ctx.lineWidth = 2;
      ctx.fill();
      ctx.stroke();
      ctx.restore();
    }

    function drawCenter() {
      ctx.beginPath();
      ctx.arc(centerX, centerY, 40, 0, Math.PI * 2);
      ctx.fillStyle = "#A0522D";
      ctx.fill();
    }

    function drawStem() {
      ctx.beginPath();
      ctx.moveTo(centerX, centerY + 40);
      ctx.lineTo(centerX, centerY + 180);
      ctx.strokeStyle = "#006400";
      ctx.lineWidth = 6;
      ctx.stroke();
    }

    function drawLeaf() {
      ctx.save();
      ctx.translate(centerX, centerY + 100);
      ctx.rotate(-0.7);
      ctx.beginPath();
      ctx.moveTo(0, 0);
      ctx.quadraticCurveTo(40, -20, 60, 0);
      ctx.quadraticCurveTo(40, 20, 0, 0);
      ctx.fillStyle = "#9ACD32";
      ctx.fill();
      ctx.restore();
    }

    function drawFrame() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      let totalPetals = 10;
      for (let i = 0; i < frame / 10 && i < totalPetals; i++) {
        drawPetal(i * (360 / totalPetals));
      }

      if (frame >= totalPetals * 10) {
        drawCenter();
      }

      if (frame >= totalPetals * 10 + 10) {
        drawStem();
      }

      if (frame >= totalPetals * 10 + 30) {
        drawLeaf();
      }

      frame++;
      if (frame < totalPetals * 10 + 100) {
        requestAnimationFrame(drawFrame);
      }
    }

    drawFrame();
  </script>
 <style>
        body {
            background-color: #f0f0f0;
            font-family: 'Georgia', serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        .text-container {
            background-color: #fff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.15);
            max-width: 600px;
            text-align: center;
        }
        h1 {
            color: #b14b4b;
        }
        p {
            font-size: 18px;
            margin-bottom: 30px;
        }
        .buttons a {
            text-decoration: none;
            padding: 10px 20px;
            margin: 10px;
            font-size: 16px;
            color: white;
            background-color: #b14b4b;
            border-radius: 8px;
            transition: 0.3s;
        }
        .buttons a:hover {
            background-color: #E0FFFF;
        }
    </style>

  <div class="text-container">
      <center><p><h1 bgcolor="#000080">Para los ojitos bonitos(❁´◡`❁)
</body>
</html>
