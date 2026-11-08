# Home Automation over Wi-Fi

ESP8266 sketch that turns two GPIO pins into a tiny Wi-Fi-controlled switch panel. The board joins a Wi-Fi network, runs a bare `WiFiServer` on port 80, and toggles the pins based on the path in the incoming HTTP request.

## How it works
- `GPIO 0` and `GPIO 2` are set as outputs on boot.
- The board connects to the configured SSID and prints its IP address over serial.
- A request to `/gpio1/0` or `/gpio1/1` drives one pin; `/gpio2/0` or `/gpio2/1` drives the other.
- The response is a minimal HTML page confirming the new pin states.

## Hardware
- ESP8266 (NodeMCU or similar)
- Relays/LEDs wired to GPIO 0 and GPIO 2

## Use
1. Set `ssid` and `password` in the sketch.
2. Flash it to the ESP8266 with the Arduino IDE.
3. Open the IP address printed on serial, and hit the `/gpio1/..` and `/gpio2/..` paths from a browser.

College project, 2019–2021.
