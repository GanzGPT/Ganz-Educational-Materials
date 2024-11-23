# JavaScript - Rest Operátor Bevezetése

## Célkitűzés:

A mai óra során megismerkedünk a JavaScript "rest" operátorával (`...`). Megtanuljuk, hogyan gyűjthetünk több argumentumot egyetlen paraméterbe, mely hasznos lehet, ha egy függvény tetszőleges számú értéket fogad. Megnézzük, hogyan működik a rest operátor, milyen előnyei és hátrányai vannak, és hogyan tehetjük átláthatóbbá és rugalmasabbá a kódunkat ennek segítségével. Kiemelten figyelünk arra, hogy a tanulók megértsék, hogyan használhatják ezt az eszközt a valós programozási problémák megoldására.

## 1. Bevezetés (5-10 perc)

**Előző ismeretek felidézése:** Kezdjük azzal, hogy visszaemlékezünk a korábban tanult JavaScript alapokra. Beszéljük át, hogyan lehet argumentumokat átadni függvényeknek, és miért hasznos, ha egy függvény képes több, akár tetszőleges számú bemeneti értéket is kezelni. Példaként hozzuk fel a hagyományos függvényeket, amelyek fix számú paraméterrel dolgoznak. Kérdezzük meg a diákokat, milyen problémákkal találkozhatunk, ha a függvények fix paramétereket igényelnek.

**Célok ismertetése:** Ma megismerkedünk a "rest" operátorral, amely lehetővé teszi, hogy egy függvény több argumentumot is kezeljen anélkül, hogy előre meg kellene határozni a paraméterek számát. Ezáltal a kódunk rugalmasabbá válik, és sokkal könnyebben olvasható lesz. A célunk az, hogy a tanulók képesek legyenek felismerni, mikor és hogyan érdemes használni a rest operátort a kódolás során.

## 2. Elméleti Alapok (15-20 perc)

**Fogalom bemutatása:** A rest operátor segítségével tetszőleges számú paramétert egyetlen tömbbe gyűjthetünk, így a függvényünk sokkal rugalmasabb lesz. Gondoljunk például arra, hogy egy számok összegét kiszámító függvény esetén nem mindig tudjuk előre, hány számot szeretnénk összeadni. Ekkor jön jól a rest operátor, amely segítségével a függvény képes lesz minden átadott értéket kezelni.

**Példák bemutatása:** Nézzük meg, hogyan működik a rest operátor egy egyszerű függvényben.

```javascript
function osszeg(...szamok) {
  // A "szamok" egy tömb lesz, amely az összes argumentumot tartalmazza.
  let eredmeny = 0;
  for (let szam of szamok) {
    eredmeny += szam; // Összeadjuk az összes elemet.
  }
  return eredmeny;
}

console.log(osszeg(1, 2, 3, 4)); // Eredmény: 10
```

Ebben a példában a `...szamok` operátor lehetővé teszi, hogy tetszőleges számú paramétert adjunk át a `osszeg` függvénynek. Minden átadott érték bekerül a `szamok` tömbbe, amelyen végighaladunk, hogy kiszámoljuk az összeget. Ez sokkal egyszerűbbé teszi a függvény használatát, mintha előre meghatározott számú paraméterrel dolgoznánk.

## 3. Interaktív Gyakorlat (10-15 perc)

**Együtt kódolás:** Most készítsünk el egy olyan függvényt közösen, amely a kapott értékeket összeszorozza. Kezdjük azzal, hogy meghatározzuk a függvény nevét, például `szorzas`, majd adjunk neki egy paramétert a rest operátorral, `...ertekek` néven.

```javascript
function szorzas(...ertekek) {
  let eredmeny = 1;
  for (let ertek of ertekek) {
    eredmeny *= ertek;
  }
  return eredmeny;
}
console.log(szorzas(2, 3, 4)); // Eredmény: 24
```

Magyárazzuk el a diákoknak, hogy ebben a példában a rest operátorral egyetlen paraméterbe gyűjtjük a bemeneteket, majd egy `for...of` ciklus segítségével végigmegyünk rajtuk, és megszorozzuk az összes elemet. Ezáltal a függvényünk képes lesz bármennyi bemeneti értékkel dolgozni, ami sokkal rugalmasabb megoldást kínál, mint ha előre megadnánk a paraméterek számát.

## 4. Önálló Gyakorlat (15-20 perc)

**Feladat kiadása:** Készítsetek egy függvényt, amely szétválasztja a szövegeket és a számokat. A függvény neve legyen `tipusSzerintRendez`, és használjatok rest operátort, hogy tetszőleges számú bemenetet adhassatok át neki.

```javascript
function tipusSzerintRendez(...elemek) {
  let szovegek = [];
  let szamok = [];
  for (let elem of elemek) {
    if (typeof elem === "string") {
      szovegek.push(elem);
    } else if (typeof elem === "number") {
      szamok.push(elem);
    }
  }
  return { szovegek, szamok };
}

console.log(tipusSzerintRendez("hello", 42, "világ", 15));
// Eredmény: { szovegek: ["hello", "világ"], szamok: [42, 15] }
```

A feladat célja, hogy a diákok megtanulják, hogyan lehet különböző típusú adatokat kezelni a rest operátor segítségével. Magyárazzuk el, hogy a függvény végighalad az összes elemen, és külön tömbbe gyűjti a szövegeket és a számokat. Ez egy egyszerű példa arra, hogyan használhatjuk a rest operátort különféle típusú adatok kezelésére.

## 5. Összegzés és Kérdések (5-10 perc)

**Óra áttekintése:** Ma megtanultuk, hogyan használhatjuk a rest operátort a JavaScriptben, és láttuk, hogyan teszi ez a kódunkat rugalmasabbá és könnyebben kezelhetővé. Beszéltük arról is, hogy milyen helyzetekben lehet különösen hasznos a rest operátor, például ha nem tudjuk előre, hogy hány paramétert fogunk kapni.

**Kérdések feltevése:** Van-e valakinek kérdése a rest operátor használatával kapcsolatban? Beszéljük meg közösen, ha valaki nem értett valamit, és próbáljunk meg példákon keresztül válaszolni. Bátorítsuk a diákokat, hogy kérdezzenek bátran, mert a programozás során nagyon fontos a kérdezés, hogy mindenki megértse az anyagot.

## 6. Házi Feladat vagy Projekt (5 perc)

**Feladat kiadása:** A házi feladat az lesz, hogy készítsetek egy olyan függvényt, amely egy tömb összes elemének a minimumát és maximumát adja vissza. Használjatok rest operátort a bemenet kezelésére, és használjátok a `Math.min()` és `Math.max()` függvényeket a megoldáshoz.

```javascript
function minimumMaximum(...elemek) {
  return {
    minimum: Math.min(...elemek),
    maximum: Math.max(...elemek)
  };
}
console.log(minimumMaximum(1, 5, 9, -3, 7));
// Eredmény: { minimum: -3, maximum: 9 }
```

Magyárazzuk el, hogy miért hasznos a rest operátor ebben az esetben: lehetővé teszi, hogy a függvény tetszőleges számú bemenettel dolgozzon. A `Math.min()` és `Math.max()` függvényekkel könnyedén megkaphatjuk a legkisebb és legnagyobb értékeket.

**Tipp: Kommentelj Mindent!**

**Kódrészletek magyarázata:** Mindig részletesen kommenteljük a kódot, hogy mindenki értse, mi történik benne. Magyarázd el, hogy miért használunk `for...of` ciklust, és hogyan működik az adott operátor. A részletes kommentek segítenek abban, hogy a diákok jobban megértsék a kódot, és könnyebben el tudják sajátítani az új fogalmakat.

**Ismeretlen fogalmak magyarázata:** Ha bármilyen új fogalom kerül elő, mindig magyarázd el, és hozz példákat. Például: "A `Math.min()` egy beépített JavaScript függvény, amely visszaadja a legkisebb értéket a paraméterei közül. A rest operátorral kombinálva lehetővé teszi, hogy egy tetszőleges számú bemeneti értékből megtaláljuk a legkisebbet."

**Vizualizáció használata:** Ha szükséges, használj ábrákat vagy diagramokat a bonyolultabb folyamatok bemutatására, hogy a diákok könnyebben megértsék a rest operátor működését.

## Óravégi Konklúzió

Az óra során megismerkedtünk a rest operátorral, amely segít abban, hogy a JavaScript függvényeink rugalmasabbak legyenek, és képesek legyenek tetszőleges számú paraméter kezelésére. Az együtt és önállóan végzett gyakorlatok révén a diákok megtanulhatták, hogyan alkalmazhatják ezt a technikát a gyakorlatban. Fontos volt rávilágítani, hogy a rest operátor milyen módon egyszerűsíti a kódot, és hogyan segít az olvashatóságban, amikor tetszőleges számú bemeneti értékkel dolgozunk. Az óravégi összegzés és a házi feladat segíteni fog abban, hogy a tanulók tovább gyakorolják és elmélyítsék az újonnan megszerzett tudást.
