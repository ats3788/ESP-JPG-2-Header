# ESP-JPG-2-Header
I wrote this for the ESP-WROVER-KIT with Pascal Lazarus

ESP32 Arduino Code

WROVER_KIT_LCD tft;
bool Switch = true;

void setup() {
	Serial.begin(115200);
  pinMode(BUTTON, INPUT_PULLUP);
  tft.begin();
  tft.setRotation(1);
  tft.drawJpg(BETTYBOO, BETTYBOO_len);
}

void loop() {
	Switch = !Switch;
  if  (Switch)
  {
    tft.drawJpg(BUNNY, BUNNY_len);
	Serial.print("JPG1");
  } else {
    tft.drawJpg(BETTYBOO, BETTYBOO_len);
	Serial.print("JPG2");
  }
  delay(2000);
}

