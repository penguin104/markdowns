# Bluetooth

header file

```cpp
#include "BluetoothSerial.h"
```

## How To Use

```cpp

String device_name = 

BluetoothSerial SerialBT;

void setup(){
    // connect device
    SerialBT.begin(String device_name);

}
```
