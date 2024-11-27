**let vs const: Mi a különbség a let és const között?**

Az ES6 verzióval a JavaScript két új változódefiníciós módot vezetett be: a `let` és `const` kulcsszavakat, amelyek blokkszintű hatókört biztosítanak. A `let` és `const` közötti különbségek megértése elengedhetetlen a modern JavaScript használatához.

### Egyszerű hasonlat a különbségek megértéséhez

Képzeljük el, hogy egy dobozt szeretnél létrehozni, amelybe beteszel egy tárgyat (változót). Most különböző dobozokat használunk a `var`, `let` és `const` változók képviseletére.

1. **`var` - Egy régi doboz, amelyet bárhová magaddal vihetsz a házon belül**
   - Bárhová viszed a házban (függvényen belül), ezt a dobozt nyitva tarthatod és kicserélheted, amit benne tartasz. Bármikor megnyithatod és megváltoztathatod a tartalmát.
   
2. **`let` - Egy modern doboz, amelyet csak egy adott helyen használhatsz a szobán belül**
   - Ez a doboz csak abban a helyiségben (blokkban) nyitható meg, ahol létrehoztad. Ha kilépsz a helyiségből, többé nem tudod kinyitni vagy módosítani.

3. **`const` - Egy lezárt doboz, amelybe csak egyszer tehetsz valamit, és utána nem nyithatod ki újra**
   - Ebbe a dobozba egyszer beraksz egy tárgyat, és utána többé nem változtathatod meg, hogy mi van benne. Az egyetlen kivétel az, hogy ha a dobozban egy összetett dolog van (például egy több darabból álló puzzle), akkor a puzzle darabjait átrendezheted, de új puzzle-t nem tehetsz bele.

### Egyszerű példák `var`, `let` és `const` használatára

#### **1. var - Régi változók**

```html
<!DOCTYPE html>
<html lang="hu">
<head>
  <meta charset="UTF-8">
  <title>Var Példa</title>
</head>
<body>
  <script>
    var z = 5;
    if (true) {
      var z = 10; // Az értéket felülírhatjuk, és az egész függvényre hatással van
      console.log(z); // Kiírja: 10
    }
    console.log(z); // Kiírja: 10 (a változó az egész függvényen belül érvényes)
  </script>
</body>
</html>
```

Ebben a példában a `var` kulcsszóval létrehozott `z` változó értéke megváltozik, és a `console.log()` mind a blokkban, mind azon kívül 10-et ír ki. Ez a viselkedés könnyen hibákhoz vezethet, ha nem figyelünk.

#### **2. let - Változtatható, blokkszintű változók**

```html
<!DOCTYPE html>
<html lang="hu">
<head>
  <meta charset="UTF-8">
  <title>Let Példa</title>
</head>
<body>
  <script>
    let x = 10;
    if (true) {
      let x = 20; // Ez a változó csak ebben a blokkban érvényes
      console.log(x); // Kiírja: 20
    }
    console.log(x); // Kiírja: 10 (az eredeti érték, mivel a blokk hatókörén kívül vagyunk)
  </script>
</body>
</html>
```

Ebben a példában az `x` értéke a blokkban 20, de a blokkon kívül az eredeti `x` változó értéke megmarad 10-nek. Ez a viselkedés segít elkerülni a véletlen felülírásokat.

#### **3. const - Állandó értékek**

```html
<!DOCTYPE html>
<html lang="hu">
<head>
  <meta charset="UTF-8">
  <title>Const Példa</title>
</head>
<body>
  <script>
    const y = 30;
    console.log(y); // Kiírja: 30
    // y = 40; // Hibát okozna, mert a const értékét nem lehet megváltoztatni

    const car = {
      brand: "Toyota",
      model: "Corolla"
    };
    console.log(car); // Kiírja: { brand: "Toyota", model: "Corolla" }
    
    // Az objektum tulajdonságait módosíthatjuk
    car.model = "Yaris";
    console.log(car); // Kiírja: { brand: "Toyota", model: "Yaris" }
  </script>
</body>
</html>
```

Ebben a példában látható, hogy a `const`-tal deklarált `car` objektumot nem lehet teljesen új objektumra lecserélni, viszont a tulajdonságait módosíthatjuk, például a `model` értékét megváltoztathatjuk.

### **Összefoglalva a `let` és `const` használatát**

- **`let`**: Olyan változók létrehozására használjuk, amelyek értéke később megváltozhat, blokkszintű hatókörrel rendelkeznek, így csak abban a blokkban érvényesek, ahol létrehoztuk őket.
- **`const`**: Olyan változók létrehozására használjuk, amelyek értékét nem kívánjuk megváltoztatni, és blokkszintű hatókörrel rendelkeznek. Fontos megjegyezni, hogy objektumok és tömbök esetében a tartalom módosítható, de maga a referencia nem.

Mindhárom kulcsszó különböző esetekre való, és megfelelő használatuk segít a változók biztonságosabb és kiszámíthatóbb kezelésében.

