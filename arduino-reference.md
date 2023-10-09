# Microcontroller reference

Initialise the `.ino` file (thought of as a C file
with additional arduino libraries):
```bash
arduino-cli config init
```

The `.ino` file created can be modified. For example,
to create a blinking LED programme:
```cpp
void setup() {
    pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
    digitalWrite(LED_BUILTIN, HIGH);
    delay(1000);
    digitalWrite(LED_BUILTIN, LOW);
    delay(1000);
}
```

The programme must be compiled, then uploaded to the 
microcontroller. 
First install the libraries for the 
microcontroller
```bash
sudo arduino-cli core install arduino:avr
```

For the freenova microcontroller, 
the `bash` commands are:
```bash
sudo arduino-cli compile --fqbn arduino:avr:uno MyFirstSketch
sudo arduino-cli core install arduino:avr
sudo arduino-cli upload -p /dev/ttyUSB0 --fqbn arduino:avr:uno MyFirstSketch
```
An excellent tutorial for programmes one could write for
the Arduino can be found on the 
[Freenova Github repository](https://github.com/Freenove/Freenove_RFID_Starter_Kit_V2.0/blob/master/Tutorial.pdf).
