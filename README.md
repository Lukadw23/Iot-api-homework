# Iot-api-homework

თემა: Smart Home System

ეს არის სისტემა, რომელიც აკონტროლებს სახლს (ტემპერატურა, განათება, უსაფრთხოება და ენერგია).

📡 1) Sensors (სენსორები)

Smart Home-ში გამოიყენება:

🌡️ Temperature Sensor (ტემპერატურა)
💡 Light Sensor (განათება)
🚪 Door Sensor (კარი ღიაა თუ დახურული)
🕵️ Motion Sensor (მოძრაობა)
🔌 Power Sensor (ელექტროენერგიის მოხმარება)

📱 2) Devices (მოწყობილობები)
Smart Thermostat
Smart Lights
Smart Door Lock
Security Camera
Smart Plug (ელექტრო შტეფსელი)

📊 3) რა data იგზავნება server-ზე?
temperature (ტემპერატურა)
motionDetected (მოძრაობა დაფიქსირდა თუ არა)
doorStatus (open/close)
lightLevel (განათების დონე)
powerUsage (ენერგიის მოხმარება)
deviceStatus (ON/OFF)
🌐 4) API Endpoints

/devices → ყველა მოწყობილობა
/status → სისტემის სტატუსი
/temperature → ტემპერატურის მონაცემი
/security → უსაფრთხოების ინფორმაცია
/energy → ენერგიის მონაცემები

📥 5) GET vs POST
GET requests:
მონაცემების მიღება
მაგალითად: ტემპერატურის ნახვა, მოწყობილობების სია
POST requests:
ახალი მონაცემის გაგზავნა
მაგალითად: light ჩართვა/გამორთვა, device update

📩 6) Request მაგალითები
✅ Request 1 (GET - devices)
GET /devices
✅ Request 2 (GET - temperature)
GET /temperature
✅ Request 3 (POST - light control)
POST /lights
Content-Type: application/json

{
  "deviceId": "light_1",
  "state": "ON"
}

📤 7) Response მაგალითები (JSON)
📌 Response 1 - devices list
{
  "devices": [
    "Smart Light",
    "Smart Thermostat",
    "Security Camera"
  ]
}
📌 Response 2 - temperature
{
  "temperature": 22,
  "unit": "Celsius",
  "room": "Living Room"
}
📌 Response 3 - security status
{
  "motionDetected": false,
  "doorStatus": "closed",
  "alarmActive": true
}

❌ 8) Error Response მაგალითი
{
  "error": "Device not found",
  "code": 404,
  "message": "The requested device ID does not exist"
}

📌 მოკლე შეჯამება
ეს Smart Home სისტემა:

აგროვებს სენსორებიდან მონაცემებს
აგზავნის server-ზე API-ით
პასუხებს აბრუნებს JSON ფორმატში
იყენებს GET (წაკითხვა) და POST (შეცვლა) request-ებს
