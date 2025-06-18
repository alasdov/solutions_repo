# Linear Algebra
<audio id="voicePlayer" controls>
  <source src="https://drive.google.com/uc?export=download&id=1KIjhwaA5nWiDFDr84e1arqzoIcdJbJ6e" type="audio/mp4">
  Your browser does not support audio playback.
</audio>
<br>

<button onclick="document.getElementById('voicePlayer').play()">▶️ Play</button>
<button onclick="document.getElementById('voicePlayer').pause()">⏸️ Pause</button>
<button onclick="document.getElementById('voicePlayer').currentTime -= 5">⏪ Back 5s</button>
<button onclick="document.getElementById('voicePlayer').currentTime += 5">⏩ Forward 5s</button>
<br><br>
<label>
  🔊 Volume:
  <input type="range" min="0" max="1" step="0.05" value="1" 
         onchange="document.getElementById('voicePlayer').volume = this.value">
</label>
