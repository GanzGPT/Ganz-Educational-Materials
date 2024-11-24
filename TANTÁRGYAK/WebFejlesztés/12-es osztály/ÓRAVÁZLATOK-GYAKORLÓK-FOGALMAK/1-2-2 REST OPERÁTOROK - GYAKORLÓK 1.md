# A rest operátor kapcsán a legfontosabb függvények a következők

## Függvények, amelyek tetszőleges számú argumentumot kezelnek

Az ilyen függvényekkel demonstrálható a rest operátor használata, amely lehetővé teszi, hogy a függvény különböző számú paramétert kapjon.

Példa: `function sum(...numbers) { ... }`

## Tömbkezelő függvények

A rest operátort gyakran használják tömbökkel kapcsolatban, például amikor több elem tömbbe történő csoportosítására van szükség.

Gyakori metódusok: `map()`, `reduce()`, `forEach()`. Ezekkel a metódusokkal tömböket lehet kezelni, melyekhez a rest operátor segítségével könnyen juttathatunk el egy tetszőleges számú paramétert tartalmazó tömböt.

Példa függvények, ahol a rest operátor segít az argumentumok kezelésében:

`Math.max()` vagy `Math.min()` esetében, ha egy függvényt szeretnénk készíteni, amely ezen beépített függvényekhez hasonló módon működik, a rest operátor segítségével fogadhatunk bármennyi argumentumot.

## Függvények, amelyek tetszőleges számú argumentumot kezelnek

### 1. Feladat: Összegző függvény

```html
<!DOCTYPE html>
<html>
<head>
  <title>Összegző függvény</title>
</head>
<body>
  <h2>Összegző függvény</h2>
  <input type="text" id="numbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="sum()">Számol</button>
  <p id="sumResult"></p>

  <script>
    function sum() {
      const numbersInput = document.getElementById('numbers').value.split(',').map(Number);
      const result = numbersInput.reduce((acc, curr) => acc + curr, 0);
      document.getElementById('sumResult').innerText = `Összeg: ${result}`;
    }
  </script>
</body>
</html>
```

### 2. Feladat: Köszönés több névvel

```html
<!DOCTYPE html>
<html>
<head>
  <title>Köszönés több névvel</title>
</head>
<body>
  <h2>Köszönés több névvel</h2>
  <input type="text" id="names" placeholder="Írj neveket, vesszővel elválasztva">
  <button onclick="greetAll()">Köszön</button>
  <p id="greetResult"></p>

  <script>
    function greetAll() {
      const names = document.getElementById('names').value.split(',');
      const result = names.map(name => `Hello, ${name.trim()}!`).join('<br>');
      document.getElementById('greetResult').innerHTML = result;
    }
  </script>
</body>
</html>
```

### 3. Feladat: Többszörözés

```html
<!DOCTYPE html>
<html>
<head>
  <title>Többszörözés</title>
</head>
<body>
  <h2>Többszörözés</h2>
  <input type="text" id="multiplyNumbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="multiply()">Számol</button>
  <p id="multiplyResult"></p>

  <script>
    function multiply() {
      const numbers = document.getElementById('multiplyNumbers').value.split(',').map(Number);
      const result = numbers.reduce((acc, curr) => acc * curr, 1);
      document.getElementById('multiplyResult').innerText = `Szorzat: ${result}`;
    }
  </script>
</body>
</html>
```

### 4. Feladat: Legnagyobb szám megtalálása

```html
<!DOCTYPE html>
<html>
<head>
  <title>Legnagyobb szám megtalálása</title>
</head>
<body>
  <h2>Legnagyobb szám megtalálása</h2>
  <input type="text" id="maxNumbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="findMax()">Legnagyobb</button>
  <p id="maxResult"></p>

  <script>
    function findMax() {
      const numbers = document.getElementById('maxNumbers').value.split(',').map(Number);
      const result = Math.max(...numbers);
      document.getElementById('maxResult').innerText = `Legnagyobb szám: ${result}`;
    }
  </script>
</body>
</html>
```

### 5. Feladat: Tömbök összefűzése

```html
<!DOCTYPE html>
<html>
<head>
  <title>Tömbök összefűzése</title>
</head>
<body>
  <h2>Tömbök összefűzése</h2>
  <input type="text" id="arrays" placeholder="Írj tömböket, például [1,2],[3,4]">
  <button onclick="mergeArrays()">Összefűz</button>
  <p id="mergeResult"></p>

  <script>
    function mergeArrays() {
      const arrays = JSON.parse(`[${document.getElementById('arrays').value}]`);
      const result = arrays.flat();
      document.getElementById('mergeResult').innerText = `Összefűzött tömb: [${result}]`;
    }
  </script>
</body>
</html>
```

### 6. Feladat: Szavak listázása

```html
<!DOCTYPE html>
<html>
<head>
  <title>Szavak listázása</title>
</head>
<body>
  <h2>Szavak listázása</h2>
  <input type="text" id="words" placeholder="Írj szavakat, vesszővel elválasztva">
  <button onclick="listWords()">Listáz</button>
  <p id="wordsResult"></p>

  <script>
    function listWords() {
      const words = document.getElementById('words').value.split(',');
      document.getElementById('wordsResult').innerText = `Szavak: ${words.join(', ')}`;
    }
  </script>
</body>
</html>
```

### 7. Feladat: Páros számok megszámolása

```html
<!DOCTYPE html>
<html>
<head>
  <title>Páros számok megszámolása</title>
</head>
<body>
  <h2>Páros számok megszámolása</h2>
  <input type="text" id="evenNumbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="countEvenNumbers()">Számol</button>
  <p id="evenResult"></p>

  <script>
    function countEvenNumbers() {
      const numbers = document.getElementById('evenNumbers').value.split(',').map(Number);
      const count = numbers.filter(num => num % 2 === 0).length;
      document.getElementById('evenResult').innerText = `Páros számok száma: ${count}`;
    }
  </script>
</body>
</html>
```

### 8. Feladat: Elemek szorzása egy alapértelmezett számmal

```html
<!DOCTYPE html>
<html>
<head>
  <title>Elemek szorzása egy számmal</title>
</head>
<body>
  <h2>Elemek szorzása egy számmal</h2>
  <input type="number" id="factor" placeholder="Szorzó értéke">
  <input type="text" id="numbersToMultiply" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="multiplyBy()">Számol</button>
  <p id="multiplyByResult"></p>

  <script>
    function multiplyBy() {
      const factor = Number(document.getElementById('factor').value);
      const numbers = document.getElementById('numbersToMultiply').value.split(',').map(Number);
      const result = numbers.map(num => num * factor);
      document.getElementById('multiplyByResult').innerText = `Eredmény: ${result}`;
    }
  </script>
</body>
</html>
```

### 9. Feladat: Különböző argumentumok szűrése

```html
<!DOCTYPE html>
<html>
<head>
  <title>Argumentumok szűrése</title>
</head>
<body>
  <h2>Argumentumok szűrése</h2>
  <input type="text" id="args" placeholder="Írj különböző típusú értékeket, vesszővel elválasztva">
  <button onclick="filterStrings()">Szűrés</button>
  <p id="filterResult"></p>

  <script>
    function filterStrings() {
      const args = document.getElementById('args').value.split(',');
      const strings = args.filter(arg => isNaN(arg));
      document.getElementById('filterResult').innerText = `String típusú elemek: ${strings}`;
    }
  </script>
</body>
</html>
```

### 10. Feladat: Számok átlagának kiszámítása

```html
<!DOCTYPE html>
<html>
<head>
  <title>Átlag számítása</title>
</head>
<body>
  <h2>Átlag számítása</h2>
  <input type="text" id="avgNumbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="average()">Számol</button>
  <p id="averageResult"></p>

  <script>
    function average() {
      const numbers = document.getElementById('avgNumbers').value.split(',').map(Number);
      const total = numbers.reduce((acc, curr) => acc + curr, 0);
      const avg = total / numbers.length;
      document.getElementById('averageResult').innerText = `Átlag: ${avg}`;
    }
  </script>
</body>
</html>
```

## Összefoglalás

- **Összegző függvény** – A `sum()` függvény tetszőleges számú számot fogad, és összeadja azokat.
- **Köszönés több névvel** – A `greetAll()` függvény tetszőleges számú nevet fogad, és mindegyikre külön üdvözlő szöveget ír ki.
- **Többszörözés** – A `multiply()` függvény több számot fogad be, és mindegyik szám szorzatát adja vissza.
- **Legnagyobb szám megtalálása** – A `findMax()` függvény bármennyi szám közül kiválasztja a legnagyobbat.
- **Tömbök összefűzése** – A `mergeArrays()` függvény tetszőleges számú tömböt fogad, és egyetlen tömbbé egyesíti őket.
- **Szavak listázása** – A `listWords()` függvény tetszőleges számú szót fogad, és ezeket egy sorban listázza.
- **Páros számok megszámolása** – A `countEvenNumbers()` függvény bármennyi számot fogad, és megszámolja a páros értékeket.
- **Elemek szorzása egy alapértelmezett számmal** – A `multiplyBy()` függvény egy alapértelmezett értékkel szorozza meg az összes többi argumentumot.
- **Különböző argumentumok szűrése** – A `filterStrings()` függvény tetszőleges számú argumentumot fogad, és csak a stringeket választja ki közülük.
- **Számok átlagának kiszámítása** – Az `average()` függvény bármennyi számot fogad, és kiszámolja ezek átlagát.

