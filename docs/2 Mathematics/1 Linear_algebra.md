<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Voice Playback</title>
</head>
<body>

<h3>Voice Playback</h3>

<audio id="voicePlayer" controls>
  <source src="https://files.catbox.moe/kcg4ws.mp3" type="audio/mp3">
  Your browser does not support the audio element.
</audio>

<br><br>

<button onclick="document.getElementById('voicePlayer').play()">Play</button>
<button onclick="document.getElementById('voicePlayer').pause()">Pause</button>
<button onclick="document.getElementById('voicePlayer').currentTime -= 5">Back 5s</button>
<button onclick="document.getElementById('voicePlayer').currentTime += 5">Forward 5s</button>

<br><br>

<label>
  Volume:
  <input type="range" min="0" max="1" step="0.05" value="1"
         onchange="document.getElementById('voicePlayer').volume = this.value">
</label>

</body>
</html>
