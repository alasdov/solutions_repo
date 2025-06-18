<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Voice Playback</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background: #f9f9f9;
      color: #333;
    }

    .player-container {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      max-width: 400px;
      margin: auto;
      text-align: center;
    }

    .controls button {
      margin: 5px;
      padding: 10px 15px;
      font-size: 14px;
      border: none;
      border-radius: 6px;
      background-color: #007bff;
      color: white;
      cursor: pointer;
    }

    .controls button:hover {
      background-color: #0056b3;
    }

    input[type="range"] {
      width: 100%;
      margin-top: 15px;
    }

    label {
      display: block;
      margin-top: 10px;
    }
  </style>
</head>
<body>

<div class="player-container">
  <h2>🔊 Voice Playback</h2>

  <audio id="voicePlayer">
    <source src="https://files.catbox.moe/kcg4ws.mp3" type="audio/mp3">
    Your browser does not support the audio element.
  </audio>

  <div class="controls">
    <button onclick="document.getElementById('voicePlayer').play()">▶️ Play</button>
    <button onclick="document.getElementById('voicePlayer').pause()">⏸️ Pause</button>
    <button onclick="document.getElementById('voicePlayer').currentTime -= 5">⏪ Back 5s</button>
    <button onclick="document.getElementById('voicePlayer').currentTime += 5">⏩ Forward 5s</button>
  </div>

  <label for="volume">Volume:</label>
  <input type="range" id="volume" min="0" max="1" step="0.05" value="1"
         onchange="document.getElementById('voicePlayer').volume = this.value">
</div>

</body>
</html>
