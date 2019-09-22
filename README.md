# Kompass

## ~avatar avatar

Willkommen! Dieses geführte Tutorial zeigt dir, wie du ein Skript programmierst das anzeigt, in welche Himmelsrichtung dein @boardname@ zeigt. Fangen wir an!

## Schritt 1

Erstelle eine Schleife, die kontinuierlich den Messwert des Kompasses auswertet.

```blocks
basic.forever(() => {

})
```

## Schritt 2 @fullscreen

Speichere den ausgelesenen Wert des @boardname@ in einer Variablen mit dem Namen `gradzahl`.

```blocks
basic.forever(() => {
    let gradzahl = input.compassHeading()
})
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

