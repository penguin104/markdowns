# Bluetooth

header file

```cpp
#include "BluetoothSerial.h"
```

## How To Use

```cpp

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
        Serial.write(SerialBT.read());
    }
}
```
