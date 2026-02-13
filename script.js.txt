function updateSensors() {
  let waterLevel = (5 + Math.random() * 2).toFixed(2); // meters
  let rainfall = Math.floor(20 + Math.random() * 40); // mm/day
  let vibration = Math.random() > 0.7 ? 1 : 0;

  document.getElementById("water").innerText = waterLevel;
  document.getElementById("rain").innerText = rainfall;
  document.getElementById("vibration").innerText =
    vibration === 1 ? "Detected" : "Normal";

  let alertBox = document.getElementById("alert");

  if (waterLevel > 6.0 || rainfall > 40 || vibration === 1) {
    alertBox.innerText = "⚠ High Risk: Flood / Encroachment Alert";
    alertBox.className = "status danger";
  } else {
    alertBox.innerText = "Status: Normal";
    alertBox.className = "status safe";
  }
}

setInterval(updateSensors, 5000);
updateSensors();
