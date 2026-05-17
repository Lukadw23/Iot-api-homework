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



რა განსხვავებაა HTTP, API და JSON-ს შორის?
HTTP (HyperText Transfer Protocol) არის წესი/პროტოკოლი, რომლის საშუალებითაც browser-ი და server-ი ერთმანეთთან ურთიერთობენ ინტერნეტში.
API (Application Programming Interface) არის საშუალება, რომლითაც ორი პროგრამა ერთმანეთთან ცვლის მონაცემებს.
JSON (JavaScript Object Notation) არის მონაცემების ფორმატი, რომლითაც ინფორმაცია იგზავნება და ინახება.

მაგალითად:
App → HTTP request → API → JSON response

რატომ არის საჭირო API რეალურ სისტემებში?
API საჭიროა, რადგან სხვადასხვა პროგრამამ და სერვისმა ერთმანეთთან შეძლონ კომუნიკაცია.
მაგალითად:
მობილური აპი იღებს ამინდის ინფორმაციას weather API-დან
ონლაინ მაღაზია უკავშირდება გადახდის სისტემას API-ის საშუალებით
Google Maps API გამოიყენება რუკების საჩვენებლად
რა განსხვავებაა GET და POST REQUEST-ს შორის?
GET გამოიყენება მონაცემების მისაღებად
POST გამოიყენება მონაცემების გასაგზავნად ან დასამატებლად

მაგალითი:

GET → მომხმარებლის ინფორმაციის ნახვა
POST → ახალი მომხმარებლის რეგისტრაცია
რას ნიშნავს Request და Response?
Request არის მოთხოვნა, რომელსაც client-ი უგზავნის server-ს
Response არის პასუხი, რომელსაც server-ი აბრუნებს

მაგალითად:
User ითხოვს ამინდის მონაცემებს → Request
Server აბრუნებს ტემპერატურას → Response

რატომ არის JSON მოსახერხებელი format?
JSON მოსახერხებელია, რადგან:
ადვილად იკითხება ადამიანისთვის
მარტივად მუშავდება პროგრამებში
არის სწრაფი და მსუბუქი
გამოიყენება თითქმის ყველა თანამედროვე API-ში

JSON მაგალითი:

{
  "name": "Nika",
  "age": 20
}
რა არის API Endpoint?
API endpoint არის კონკრეტული URL მისამართი, სადაც იგზავნება request.

მაგალითი:

https://api.weather.com/current

ეს endpoint აბრუნებს მიმდინარე ამინდს.

რა არის API Key და რატომ არის მნიშვნელოვანი უსაფრთხოებისთვის?
API Key არის უნიკალური გასაღები/კოდი, რომელიც ამოწმებს ვინ იყენებს API-ს.

ის მნიშვნელოვანია, რადგან:

იცავს API-ს არასანქცირებული გამოყენებისგან
აკონტროლებს მომხმარებლებს
ზღუდავს ზედმეტ request-ებს
რა მოხდება თუ app ვერ უკავშირდება server-ს?
თუ app server-ს ვერ დაუკავშირდა:
მონაცემები ვერ ჩაიტვირთება
მომხმარებელი მიიღებს error message-ს
ზოგი ფუნქცია აღარ იმუშავებს
შესაძლებელია timeout ან connection error
მოიფიქრე რეალური მაგალითი სადაც გამოიყენება API
მაგალითი:
Bolt აპლიკაცია იყენებს:
Maps API-ს მდებარეობისთვის
Payment API-ს გადახდისთვის
Notification API-ს შეტყობინებებისთვის
მოიფიქრე 3 განსხვავებული IoT მოწყობილობა და აღწერეთ რა data აგროვებენ
Smart Watch
აგროვებს:
გულისცემას
ნაბიჯების რაოდენობას
ძილის მონაცემებს
Smart Thermostat
აგროვებს:
ოთახის ტემპერატურას
ტენიანობას
ენერგიის მოხმარებას
Smart Security Camera
აგროვებს:
ვიდეო ჩანაწერებს
მოძრაობის დეტექციას
დროისა და თარიღის ინფორმაციას
