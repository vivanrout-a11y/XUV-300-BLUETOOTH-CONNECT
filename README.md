# XUV-300-BLUETOOTH-CONNECT
Web-based Bluetooth Car Control Application
<!DOCTYPE html>
<html>
<head>
  <title>XUV-300 Bluetooth Connect</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f4;
      padding-top: 40px;
    }
    button {
      padding: 15px 25px;
      margin: 10px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>

<body>

  <h1>XUV-300-BLUETOOTH-CONNECT</h1>
  <p>Web-based Bluetooth Car Control Application</p>

  <button onclick="connectBluetooth()">Connect to Car</button>
  <br><br>
  <button onclick="sendCommand('AC_ON')">AC ON</button>
  <button onclick="sendCommand('AC_OFF')">AC OFF</button>

  <p id="status">Status: Not Connected</p>

  <script>
    let device;
    let characteristic;

    async function connectBluetooth() {
      try {
        device = await navigator.bluetooth.requestDevice({
          acceptAllDevices: true
        });
        document.getElementById("status").innerText =
          "Status: Connected to " + device.name;
      } catch (error) {
        alert("Bluetooth connection failed");
      }
    }

    function sendCommand(cmd) {
      alert("Command sent: " + cmd);
    }
  </script>

</body>
</html>
