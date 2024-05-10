
![notaus.jpg]([/programmcode/notfallsperrknopf/notaus.jpg](https://github.com/binarybear-de/the-button/blob/main/171538301180408253.png))

In einem Notaus-Schaltergehäuse wird ein Arduino Pro Micro verbaut, welcher über USB an den PC angeschlossen wird.
Ziel des Projektes ist ein Knopf zum schnellen Windows sperren (oder sonstigen Programmierbaren Tastenkombinationen für das Betriebssystem.

Das Script wartet auf einen Tastendruck (der Schalter hat ein NC((normally closed))-Schalter, welcher an PIN 9 und GND angeschlossen ist.
```c++
#include <Keyboard.h>
int PIN_BTN = 9;
void setup() {
    pinMode(PIN_BTN, INPUT_PULLUP);
}

void loop() {

  if (digitalRead(PIN_BTN) == 1) {
    Keyboard.press(KEY_LEFT_GUI);
    Keyboard.press('l');
    Keyboard.releaseAll();
    delay(2900);
  }
  delay(100);
}
```
