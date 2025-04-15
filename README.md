# Custom-style
Custom styles
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Custom Style Maker</title>
  <style>
    body {
      background-color: #0a0a0a;
      color: white;
      font-family: 'Courier New', Courier, monospace;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 1000px;
      margin: auto;
    }
    h1 {
      font-size: 32px;
      text-align: center;
      margin-bottom: 20px;
    }
    .tabs {
      display: flex;
      justify-content: space-around;
      margin-bottom: 20px;
    }
    .tabs button {
      background: none;
      color: white;
      border: none;
      font-size: 16px;
      cursor: pointer;
    }
    .settings {
      background-color: #1a1a1a;
      padding: 20px;
      border-radius: 10px;
    }
    .setting {
      margin-bottom: 15px;
    }
    label {
      display: block;
      margin-bottom: 5px;
    }
    input[type="range"] {
      width: 100%;
    }
    .output {
      margin-top: 30px;
      background-color: #111;
      padding: 20px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Custom Style Maker</h1>
    <p>This script was made by Executive | Version: 1</p>
    <div class="tabs">
      <button>Tutorial</button>
      <button>Style Settings</button>
      <button>Style Functions</button>
      <button>Pre-Made Functions</button>
      <button>Create - Finish</button>
    </div><div class="settings">
  <div class="setting">
    <label for="shootingPower">Shooting Power</label>
    <input type="range" id="shootingPower" min="0" max="100" value="0">
  </div>
  <div class="setting">
    <label for="airPower">Air Power (Ball goes up)</label>
    <input type="range" id="airPower" min="0" max="100" value="0">
  </div>
  <div class="setting">
    <label for="curveRight">Curve Right Power</label>
    <input type="range" id="curveRight" min="0" max="100" value="0">
  </div>
  <div class="setting">
    <label for="curveLeft">Curve Left Power</label>
    <input type="range" id="curveLeft" min="0" max="100" value="0">
  </div>
</div>

<div class="output">
  <p><strong>Script Gerado:</strong></p>
  <pre id="scriptOutput">-- O script aparecerá aqui...</pre>
</div>

  </div>  <script>
    const inputs = document.querySelectorAll('input[type="range"]');
    const output = document.getElementById('scriptOutput');

    inputs.forEach(input => {
      input.addEventListener('input', generateScript);
    });

    function generateScript() {
      const shooting = document.getElementById('shootingPower').value;
      const air = document.getElementById('airPower').value;
      const right = document.getElementById('curveRight').value;
      const left = document.getElementById('curveLeft').value;

      const script = `-- Custom Kick Script\nlocal shootingPower = ${shooting}\nlocal airPower = ${air}\nlocal curveRight = ${right}\nlocal curveLeft = ${left}\n\nfunction executeKick()\n  print("Kick Settings:", shootingPower, airPower, curveRight, curveLeft)\nend`;

      output.textContent = script;
    }
  </script></body>
</html>
