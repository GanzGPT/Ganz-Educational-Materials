# JavaScript Változók: `var`, `let`, és `const` az ES6-ban

## Célkitűzések
- Megértetni a diákokkal a `var`, `let`, és `const` kulcsszavak közötti különbségeket.
- Megvizsgálni, miért vezették be a `let` és `const` kulcsszavakat.
- Megismertetni az új fogalmakat, mint a „scope” (hatókör).
- Bemutatni, hogyan használjuk ezeket a kulcsszavakat különböző programozási helyzetekben.
- Segíteni a diákoknak megérteni, hogyan kerülhetik el a változók deklarációjából származó hibákat.
- Megismerni a JavaScript változókezelési sajátosságait, különösen a scope és hoisting fogalmát.

## 1. Bevezetés (5-10 perc)
Kezdjük azzal, hogy megfogalmazzuk az óra célját.

> "Ma a JavaScript változóiról fogunk tanulni, és azt is megtudjuk, hogyan változtak ezek az ES6 verzióban. Megnézzük, hogy a `var` hogyan működött régen, és miért vezették be a `let` és `const` kulcsszavakat."

Kérdezzük meg a diákokat, hogy ki hallott már JavaScript-ről, és mi az a változó. Ez segít abban, hogy megértsük, milyen szinten vannak, és aktiváljuk a meglévő tudásukat. Beszéljük meg, miért fontosak a változók, és hogyan használhatók különböző problémák megoldására a programozásban. Rámutathatunk arra is, hogy a JavaScriptben történő változókezelés hogyan változott az idők során, különösen az ES6 bevezetésével.

## 2. Elérés (Scope) és Deklarációs Kulcsszavak (`var`, `let`, `const`) (15-20 perc)

### Elérés és Hatókör („scope”)
Először érdemes tisztázni a „scope” fogalmát. A scope jelenti, hogy egy változó honnan érhető el a kódban, és milyen életciklusa van. A JavaScriptben három fő típusú scope létezik: globális, függvényszintű, és blokkszintű hatókör.

- **Globális scope**: A változók bárhol elérhetők a kódban, tehát ha egy változót a program tetején deklarálunk (a függvényeken kívül), akkor az minden funkcióban és blokkban használható. Ezeket nevezzük globális változóknak.
- **Függvényszintű scope**: A függvényen belül deklarált változók csak a függvényen belül elérhetők. Ez azt jelenti, hogy ha egy `var` változót egy függvényen belül deklarálunk, akkor az csak azon a függvényen belül lesz elérhető.
- **Blokkszintű scope**: A blokkon belül (`{}`-eken belül, például if, for, while) deklarált változók csak azon a blokkon belül léteznek. Ez a hatókör segít abban, hogy a változók ne legyenek elérhetők a kód más részein, ahol nincs rájuk szükség.

### `var` Kulcsszó
- A **`var`** a legelső kulcsszó, amit JavaScriptben használtak változó deklarálására.
- A `var` kulcsszóval létrehozott változók „függvényszintű” hatókörrel rendelkeznek, ami azt jelenti, hogy ha egy függvényen belül deklarálunk egy `var` változót, az az egész függvényen belül elérhető, még akkor is, ha egy blokkon belül hoztuk létre. Ez a sajátosság gyakran vezethetett váratlan hibákhoz, mert a változók a vártnál szélesebb körben voltak elérhetők.
- **Hoisting**: A `var` változók deklarációja a JavaScript futtatása során a kód tetejére kerül, ami azt jelenti, hogy a változó létezik, de nem feltétlenül van értéke, mielőtt a tényleges deklaráció sorra kerülne. Ez a jelenség az úgynevezett „hoisting”. A hoisting azt eredményezi, hogy a `var` változók akár a deklarációjuk előtt is használhatók, de az értékük ekkor „undefined” lesz.

### Példa a `var` Használatára (HTML Környezetben)

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript var példa</title>
</head>
<body>
    <h1>JavaScript var példa</h1>
    <script>
        function example() {
            if (true) {
                var message = "Hello World!"; // A 'var' változó függvény szintű hatókörrel rendelkezik
            }
            console.log(message); // "Hello World!" - A 'message' változó elérhető a függvényen belül
        }
        example();
    </script>
</body>
</html>
```
Ebben a példában a „message” változó a teljes `example` függvényen belül elérhető, még akkor is, ha az `if` blokkon belül hoztuk létre. Ez jól mutatja, hogyan működik a `var` hatóköre, és miért lehet ez problémás nagyobb kódok esetében.

### `let` és `const` Kulcsszavak
Az **ES6** hozta be a `let` és `const` kulcsszavakat, hogy a változók blokkszintű hatókörűek lehessenek, azaz csak abban a blokkon belül legyenek elérhetőek, ahol deklaráltuk őket. Ez nagyobb kontrollt biztosít a változók felett, és segít elkerülni a `var` által okozott hibákat.
- A **`let`** és **`const`** változók nem hoisting-olódnak ugyanolyan módon, mint a `var`. Ez azt jelenti, hogy ezek a változók nem érhetők el a deklarációjuk előtt, így kevesebb hibalehetőséget okoznak.

### `let` Példa (HTML Környezetben)

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript let példa</title>
</head>
<body>
    <h1>JavaScript let példa</h1>
    <script>
        function example() {
            if (true) {
                let message = "Hello World!"; // A 'let' változó blokkszintű hatókörrel rendelkezik
                console.log(message); // "Hello World!" - A 'message' változó elérhető ebben a blokkon belül
            }
            // console.log(message); // Hiba: message nincs definiálva - A 'message' változó kívül van a hatóköréből
        }
        example();
    </script>
</body>
</html>
```
A `let` kulcsszóval deklarált „message” változó csak az adott blokkon belül létezik, így a diákok könnyen megérthetik, hogyan korlátozza a `let` a hatókört. Ez segít abban, hogy elkerüljük a `var` használatával járó hatókörproblémákat.

### `const` Példa (HTML Környezetben)

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript const példa</title>
</head>
<body>
    <h1>JavaScript const példa</h1>
    <script>
        function example() {
            const pi = 3.14; // A 'const' változó értéke nem módosítható
            console.log(pi); // "3.14" - A 'pi' értéke állandó marad
        }
        example();
    </script>
</body>
</html>
```
A `const` változóval deklarált értékek nem módosíthatók. Ez egy egyszerű példa arra, hogy a `const` hogyan használható állandók deklarálására. A `const` kulcsszóval deklarált változók szintén blokkszintű hatókörrel rendelkeznek, mint a `let`.

## Összehasonlítás a `var` és a `let`/`const` Hatóköre Között
- A `var` kulcsszóval létrehozott változók függvényszintű hatókörrel rendelkeznek, ami azt jelenti, hogy ha egy függvényen belül használjuk őket, akkor az egész függvényen belül elérhetők lesznek, függetlenül attól, hogy melyik blokkon belül hoztuk őket létre.
- A `let` és `const` változók ezzel szemben blokkszintű hatókörrel rendelkeznek, ami azt jelenti, hogy csak azon a blokkon belül léteznek, ahol deklaráltuk őket. Ez segít abban, hogy a változók ne legyenek elérhetők a kódban olyan helyeken, ahol nem szükségesek, ezáltal csökkentve a hibák lehetőségét.

## 3. Interaktív Gyakorlat (10-15 perc)
### Együtt Kódolás
Készítsünk egy példát, amely megmutatja, hogyan használjuk a `let` és `const` kulcsszavakat helyesen. Mutassuk be, hogyan kerülhetjük el a `var`-ral kapcsolatos problémákat a `let` és `const` használatával.

Magyarázzuk el a diákoknak, hogy mikor érdemes `let`-et használni (ha az érték változhat), és mikor érdemes `const`-ot használni (ha nem változhat). Ez segít a diákoknak megérteni, hogyan válasszanak megfelelő kulcsszót a programozási feladatok során.

### Példa (HTML Környezetben)

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript let és const példa</title>
</head>
<body>
    <h1>JavaScript let és const példa</h1>
    <script>
        let age = 18; // 'let' használata, mert az életkor változhat
        age = 19; // Az életkor értéke megváltozik

        const birthYear = 2005; // 'const' használata, mert a születési év nem változik
        console.log(`Életkor: ${age}, Születési év: ${birthYear}`); // Kiírja az életkort és a születési évet
    </script>
</body>
</html>
```
Hangsúlyozzuk, hogy a `const` használata segít a kód olvashatóságának növelésében és a hibák elkerülésében, mivel a többi fejlesztő azonnal látja, hogy az adott változó értéke nem módosulhat.

## 4. Önálló Gyakorlat (15-20 perc)
Adjunk feladatot, ahol a diákoknak ki kell választaniuk, hogy mikor használjanak `let`, `var`, vagy `const` kulcsszavakat.
- **Példafeladat**: "Deklaráljatok egy változót, amely a hőmérsékletet jelzi, és egy másikat, amely a Föld gravitációs állandóját."
- Magyarázzuk el, hogy miért fontos a megfelelő kulcsszó kiválasztása, és hogyan segíthet ez a kód karbantarthatóságában és stabilitásában. A feladatok során járjunk körbe a teremben, és segítsük a diákokat, ha elakadnak.

## 5. Összegzés és Kérdések (5-10 perc)
- Foglaljuk össze a tanultakat: `var` – globális vagy függvény szintű scope, `let` – blokkszintű scope, `const` – módosíthatatlan változó.
- Kérjük a diákokat, hogy tegyenek fel kérdéseket, ha valami nem volt egyértelmű. Beszéljük meg, hogy milyen előnyökkel jár a `let` és `const` használata a `var`-hoz képest, és hogyan segítik ezek a kód hibamentességének fenntartását.

## 6. Házi Feladat vagy Projekt (5 perc)
- Adjunk ki egy házi feladatot: "Készíts egy kódot, amely számolja, hányszor lett egy gomb megnyomva egy weboldalon, és biztosítsd, hogy a gombnyomás számlálása helyesen működjön blokkszintű változóval."
- Kérjük a diákokat, hogy használják a `let` és `const` kulcsszavakat, és próbálják meg alkalmazni az órán tanult elveket. A feladat során figyeljenek arra, hogy a megfelelő kulcsszót válasszák az adott helyzetnek megfelelően, ezzel elkerülve a változók felesleges újradefiniálását és a hibákat.

