# Tömbkezelő függvények

## 1. Feladat: Számok négyzete

Készíts egy függvényt, amely a megadott számok mindegyikének négyzetét kiszámolja!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok négyzete</title>
</head>
<body>
  <h2>Számok négyzete</h2>
  <input type="text" id="squareNumbers" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="calculateSquare()">Négyzet</button>
  <p id="squareResult"></p>

  <script>
    function calculateSquare() {
      const numbers = document.getElementById('squareNumbers').value.split(',').map(Number);
      const result = numbers.map(num => num * num);
      document.getElementById('squareResult').innerText = `Négyzetek: ${result}`;
    }
  </script>
</body>
</html>
```

## 2. Feladat: Páros számok kiválasztása

Készíts egy függvényt, amely kiválasztja a megadott számok közül a páros számokat!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Páros számok kiválasztása</title>
</head>
<body>
  <h2>Páros számok kiválasztása</h2>
  <input type="text" id="evenNumbersInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="selectEvenNumbers()">Párosok</button>
  <p id="evenNumbersResult"></p>

  <script>
    function selectEvenNumbers() {
      const numbers = document.getElementById('evenNumbersInput').value.split(',').map(Number);
      const result = numbers.filter(num => num % 2 === 0);
      document.getElementById('evenNumbersResult').innerText = `Páros számok: ${result}`;
    }
  </script>
</body>
</html>
```

## 3. Feladat: Számok összegzése

Készíts egy függvényt, amely összegzi a megadott számokat!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok összegzése</title>
</head>
<body>
  <h2>Számok összegzése</h2>
  <input type="text" id="sumInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="sumNumbers()">Összeg</button>
  <p id="sumResult"></p>

  <script>
    function sumNumbers() {
      const numbers = document.getElementById('sumInput').value.split(',').map(Number);
      const result = numbers.reduce((acc, curr) => acc + curr, 0);
      document.getElementById('sumResult').innerText = `Összeg: ${result}`;
    }
  </script>
</body>
</html>
```

## 4. Feladat: Számok duplázása

Készíts egy függvényt, amely minden megadott számot megdupláz!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok duplázása</title>
</head>
<body>
  <h2>Számok duplázása</h2>
  <input type="text" id="doubleInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="doubleNumbers()">Duplázás</button>
  <p id="doubleResult"></p>

  <script>
    function doubleNumbers() {
      const numbers = document.getElementById('doubleInput').value.split(',').map(Number);
      const result = numbers.map(num => num * 2);
      document.getElementById('doubleResult').innerText = `Duplázott számok: ${result}`;
    }
  </script>
</body>
</html>
```

## 5. Feladat: Nagyobb számok kiválasztása

Készíts egy függvényt, amely kiválasztja azokat a számokat, amelyek nagyobbak, mint egy adott érték!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Nagyobb számok kiválasztása</title>
</head>
<body>
  <h2>Nagyobb számok kiválasztása</h2>
  <input type="number" id="threshold" placeholder="Küszöbérték">
  <input type="text" id="greaterInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="selectGreaterNumbers()">Kiválasztás</button>
  <p id="greaterResult"></p>

  <script>
    function selectGreaterNumbers() {
      const threshold = Number(document.getElementById('threshold').value);
      const numbers = document.getElementById('greaterInput').value.split(',').map(Number);
      const result = numbers.filter(num => num > threshold);
      document.getElementById('greaterResult').innerText = `Nagyobb számok: ${result}`;
    }
  </script>
</body>
</html>
```

## 6. Feladat: Szavak hossza

Készíts egy függvényt, amely minden szónak visszaadja a hosszát!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Szavak hossza</title>
</head>
<body>
  <h2>Szavak hossza</h2>
  <input type="text" id="wordInput" placeholder="Írj szavakat, vesszővel elválasztva">
  <button onclick="getWordLengths()">Hossz</button>
  <p id="wordLengthResult"></p>

  <script>
    function getWordLengths() {
      const words = document.getElementById('wordInput').value.split(',');
      const result = words.map(word => `${word.trim()}: ${word.trim().length}`);
      document.getElementById('wordLengthResult').innerHTML = result.join('<br>');
    }
  </script>
</body>
</html>
```

## 7. Feladat: Számok szorzása

Készíts egy függvényt, amely összeszorozza a megadott számokat!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok szorzása</title>
</head>
<body>
  <h2>Számok szorzása</h2>
  <input type="text" id="productInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="multiplyNumbers()">Szorzat</button>
  <p id="productResult"></p>

  <script>
    function multiplyNumbers() {
      const numbers = document.getElementById('productInput').value.split(',').map(Number);
      const result = numbers.reduce((acc, curr) => acc * curr, 1);
      document.getElementById('productResult').innerText = `Szorzat: ${result}`;
    }
  </script>
</body>
</html>
```

## 8. Feladat: Minden szó első betűje nagybetűs

Készíts egy függvényt, amely minden szót nagybetűvel kezd!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Szavak első betűje nagybetűs</title>
</head>
<body>
  <h2>Szavak első betűje nagybetűs</h2>
  <input type="text" id="capitalizeInput" placeholder="Írj szavakat, vesszővel elválasztva">
  <button onclick="capitalizeWords()">Nagybetűs</button>
  <p id="capitalizeResult"></p>

  <script>
    function capitalizeWords() {
      const words = document.getElementById('capitalizeInput').value.split(',');
      const result = words.map(word => word.trim().charAt(0).toUpperCase() + word.trim().slice(1));
      document.getElementById('capitalizeResult').innerText = `Nagybetűs szavak: ${result}`;
    }
  </script>
</body>
</html>
```

## 9. Feladat: Számok abszolút értéke

Készíts egy függvényt, amely minden számnak az abszolút értékét adja vissza!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok abszolút értéke</title>
</head>
<body>
  <h2>Számok abszolút értéke</h2>
  <input type="text" id="absInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="calculateAbs()">Abszolút érték</button>
  <p id="absResult"></p>

  <script>
    function calculateAbs() {
      const numbers = document.getElementById('absInput').value.split(',').map(Number);
      const result = numbers.map(num => Math.abs(num));
      document.getElementById('absResult').innerText = `Abszolút értékek: ${result}`;
    }
  </script>
</body>
</html>
```

## 10. Feladat: Számok átlagának kiszámítása

Készíts egy függvényt, amely kiszámolja a számok átlagát, de ha a tömb üres, visszaad nullát!

```html
<!DOCTYPE html>
<html>
<head>
  <title>Számok átlagának kiszámítása</title>
</head>
<body>
  <h2>Számok átlagának kiszámítása</h2>
  <input type="text" id="averageInput" placeholder="Írj számokat, vesszővel elválasztva">
  <button onclick="calculateAverage()">Átlag</button>
  <p id="averageResult"></p>

  <script>
    function calculateAverage() {
      const numbers = document.getElementById('averageInput').value.split(',').map(Number);
      if (numbers.length === 0) {
        document.getElementById('averageResult').innerText = `Átlag: 0`;
      } else {
        const total = numbers.reduce((acc, curr) => acc + curr, 0);
        const avg = total / numbers.length;
        document.getElementById('averageResult').innerText = `Átlag: ${avg}`;
      }
    }
  </script>
</body>
</html>
```

## Összefoglalás: Melyik tömbkezelő függvényt gyakoroltatja

- **Számok négyzete** - `map()`
- **Páros számok kiválasztása** - `filter()`
- **Számok összegzése** - `reduce()`
- **Számok duplázása** - `map()`
- **Nagyobb számok kiválasztása** - `filter()`
- **Szavak hossza** - `map()`
- **Számok szorzása** - `reduce()`
- **Minden szó első betűje nagybetűs** - `map()`
- **Számok abszolút értéke** - `map()`
- **Számok átlagának kiszámítása** - `reduce()`

