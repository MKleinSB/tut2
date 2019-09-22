# Neopixel am @boardname@

## ~avatar

Willkommen! Dieses geführte Tutorial zeigt dir, wie du ein Skript programmierst mit dem Du RGB-LEDs (Neopixel) mit Deinem @boardname@ ansteuern kannst.

Fangen wir an!

## Neopixel anschließen @fullscreen
Neopixel lassen sich ganz leicht am @boardname@ anschließen:
Verbinde DIN mit P0, +5V mit dem + des @boardname@ und GND mit - des @boardname@
Gut geeignet sind RGB-Streifen die es sehr günstig gibt. Mehr als 8 LEDs sollten es ohne zusätzliche Stromversorgung nicht sein.
![Neopixelbild](https://github.com/MKleinSB/Tut1/blob/master/compass.png)

## Neopixelstreifen einer Variable zuweisen @fullscreen

Dieses Projekt verwendet die **neopixel** Erweiterung. Du musst sie zu deinem Projekt hinzufügen.
* klicke auf das Zahnrad-Menü und wähle **Erweiterungen**
* wähle die **neopixel** Erweiterung

Nun musst Du dem @boardname@ sagen wie dein Neopixelstreifen heißen soll und waus wie vielen LEDs er besteht.
Wir gehen mal von 8 LEDs aus die an P0 angeschlossen sind.
```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
```

## Helligkeit der LEDs festlegen @fullscreen

Dein @boardname@ kann die Helligkeit der LEDs mit dem Befehl <0>||strip.setBrightness||</0> festlegen.

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setBrightness(150)
```

## Schritt 3 @fullscreen

Wenn `gradzahl` kleiner als `45` oder größer als `315` ist, dann zeigt die Kompassrichtung hauptsächlich in Richtung **Norden**. Zeige ein `N` auf dem @boardname@ an.

```blocks
basic.forever(() => {
    let gradzahl = input.compassHeading();
    if (gradzahl < 45 || gradzahl > 315) {
        basic.showString("N");
    }
});
```

## Schritt 4

Wenn `gradzahl` kleiner als `135` ist, zeigt der @boardname@ hauptsächlich nach **Osten**. Zeige ein `O` auf dem @boardname@ an.

```blocks
basic.forever(() => {
    let gradzahl = input.compassHeading();
    if (gradzahl < 45 || gradzahl > 315) {
        basic.showString("N");
    }
    else if (gradzahl < 135) {
        basic.showString("O");
    }
});
```

## Schritt 5

Wenn `gradzahl` kleiner als `225` ist, zeigt der @boardname@ hauptsächlich nach **Süden**. Zeige ein `S` auf dem @boardname@ an.

```blocks
basic.forever(() => {
    let gradzahl = input.compassHeading();
    if (gradzahl < 45 || gradzahl > 315) {
        basic.showString("N");
    }
    else if (gradzahl < 135) {
        basic.showString("O");
    }
    else if (gradzahl < 225) {
        basic.showString("S");
    }
});
```

## Schritt 6

Wenn keine dieser Bedingungen true zurückgibt, muss der @boardname@ nach **Westen** zeigen. Zeige ein `W` auf dem @boardname@ an.

```blocks
basic.forever(() => {
    let gradzahl = input.compassHeading();
    if (gradzahl < 45 || gradzahl > 315) {
        basic.showString("N");
    }
    else if (gradzahl < 135) {
        basic.showString("O");
    }
    else if (gradzahl < 225) {
        basic.showString("S");
    }
    else {
        basic.showString("W");
    }
});
```

## Schritt 7 @tutorialCompleted

Lade jetzt das Programm auf deinen @boardname@ und teste ob es so funktioniert wie gewünscht!

```package
neopixel=github:microsoft/pxt-neopixel#v0.6.12
```
