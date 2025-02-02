# Bluetooth

## How To Use

```cpp
#include "BluetoothSerial.h"

String device_name = "SIGUSA";

const char *pin = "1234";

BluetoothSerial SerialBT;

void setup(){
    Serial.begin(115200);
    // connect device
    SerialBT.begin(device_name);

    #ifdef USE_PIN
        SerialBT.setPin(pin);
        Serial.println("use pin");
    #endif
}

void loop() {
    // esp to phone
    if (Serial.available()) {
        SerialBT.write(Serial.read());
    }
    // phone to esp
    if (SerialBT.available()) {
        // return Type is int read() function.
        Serial.write(SerialBT.read());
    }
}
```
