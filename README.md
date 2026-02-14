# Plasma-Modulated-Infrared-Transceiver-PMIRT

#include <IRremote.h>

void setup() {
  // code here runs once:
  IrReceiver.begin(11, ENABLE_LED_FEEDBACK);
  Serial.begin(9600);
  Serial.print("Start now:");
}
 
void loop() {
  // code here runs repeatedly:
  if (IrReceiver.decode()) {
    unsigned long code = IrReceiver.decodedIRData.decodedRawData;
    Serial.println(code, HEX);
  }
  IrReceiver.resume(); 
  delay(500);
}





