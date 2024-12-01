---

## Sziasztok!

Az év második felében izgalmas és hasznos dolgokat fogunk tanulni a JavaScript programozás terén. Olyan témákat érintünk majd, amelyek nem csak elméletben érdekesek, hanem a gyakorlatban is hasznosak lesznek számotokra a webfejlesztésben.

### 1. **Új eszközök objektumokhoz és tömbökhöz**

- **Spread operátor (`...`):** Egyszerű másolás és kombinálás tömbök és objektumok esetén.

  **Példa előtte és utána:**

  *Előtte (tömbök egyesítése ciklusokkal):*

  ```javascript
  const arr1 = [1, 2, 3];
  const arr2 = [4, 5, 6];
  const combined = [];

  for (let i = 0; i < arr1.length; i++) {
    combined.push(arr1[i]);
  }

  for (let i = 0; i < arr2.length; i++) {
    combined.push(arr2[i]);
  }

  console.log(combined); // [1, 2, 3, 4, 5, 6]
  ```

  *Utána (spread operátor használatával):*

  ```javascript
  const arr1 = [1, 2, 3];
  const arr2 = [4, 5, 6];
  const combined = [...arr1, ...arr2];

  console.log(combined); // [1, 2, 3, 4, 5, 6]
  ```

- **Destrukturálás:** Könnyű adatkinyerés objektumokból és tömbökből.

  **Példa előtte és utána:**

  *Előtte (adatok kinyerése hagyományos módon):*

  ```javascript
  const person = {
    name: 'Anna',
    age: 25,
    city: 'Budapest'
  };

  const name = person.name;
  const age = person.age;

  console.log(name); // 'Anna'
  console.log(age); // 25
  ```

  *Utána (destrukturálással):*

  ```javascript
  const person = {
    name: 'Anna',
    age: 25,
    city: 'Budapest'
  };

  const { name, age } = person;

  console.log(name); // 'Anna'
  console.log(age); // 25
  ```

- **Beépített függvények:** `map()`, `filter()`, `reduce()` használata tömbökön.

  - **`map()`**: Minden elemre művelet alkalmazása.

    **Példa előtte és utána:**

    *Előtte (for ciklussal):*

    ```javascript
    const numbers = [1, 2, 3, 4];
    const doubled = [];

    for (let i = 0; i < numbers.length; i++) {
      doubled.push(numbers[i] * 2);
    }

    console.log(doubled); // [2, 4, 6, 8]
    ```

    *Utána (`map()` használatával):*

    ```javascript
    const numbers = [1, 2, 3, 4];
    const doubled = numbers.map(num => num * 2);

    console.log(doubled); // [2, 4, 6, 8]
    ```

  - **`filter()`**: Elemek szűrése bizonyos feltétel alapján.

    **Példa előtte és utána:**

    *Előtte (for ciklussal és feltétellel):*

    ```javascript
    const numbers = [1, 2, 3, 4, 5, 6];
    const evenNumbers = [];

    for (let i = 0; i < numbers.length; i++) {
      if (numbers[i] % 2 === 0) {
        evenNumbers.push(numbers[i]);
      }
    }

    console.log(evenNumbers); // [2, 4, 6]
    ```

    *Utána (`filter()` használatával):*

    ```javascript
    const numbers = [1, 2, 3, 4, 5, 6];
    const evenNumbers = numbers.filter(num => num % 2 === 0);

    console.log(evenNumbers); // [2, 4, 6]
    ```

  - **`reduce()`**: Tömb elemeinek egyetlen értékké alakítása.

    **Példa előtte és utána:**

    *Előtte (for ciklussal összeadás):*

    ```javascript
    const numbers = [1, 2, 3, 4];
    let sum = 0;

    for (let i = 0; i < numbers.length; i++) {
      sum += numbers[i];
    }

    console.log(sum); // 10
    ```

    *Utána (`reduce()` használatával):*

    ```javascript
    const numbers = [1, 2, 3, 4];
    const sum = numbers.reduce((total, num) => total + num, 0);

    console.log(sum); // 10
    ```

### 2. **Aszinkron programozás és callback-ek**

- **Callback függvények:** Függvények meghívása esemény bekövetkeztekor.

  **Példa előtte és utána:**

  *Előtte (szinkron kód):*

  ```javascript
  function getData() {
    // Feltételezzük, hogy ez egy hosszú művelet
    const data = /* adatok lekérése */;
    return data;
  }

  const result = getData();
  console.log(result);
  ```

  *Utána (aszinkron kód callback-kel):*

  ```javascript
  function getData(callback) {
    setTimeout(() => {
      const data = 'Adatok megérkeztek';
      callback(data);
    }, 2000);
  }

  getData(function(result) {
    console.log(result); // 'Adatok megérkeztek' két másodperc múlva jelenik meg
  });
  ```

- **`setTimeout`:** Művelet végrehajtása időzítéssel.

  **Példa előtte és utána:**

  *Előtte (késleltetés nélkül):*

  ```javascript
  console.log('Ez az üzenet azonnal megjelenik.');
  ```

  *Utána (`setTimeout` használatával):*

  ```javascript
  setTimeout(() => {
    console.log('Ez az üzenet 5 másodperc múlva jelenik meg.');
  }, 5000);
  ```

- **Eseménykezelők (event listeners):** Reakció felhasználói interakciókra.

  **Példa előtte és utána:**

  *Előtte (eseménykezelő nélkül):*

  ```html
  <button id="myButton">Kattints rám!</button>
  <script>
    // Nincs interakció a gombbal
  </script>
  ```

  *Utána (eseménykezelő hozzáadása):*

  ```html
  <button id="myButton">Kattints rám!</button>
  <script>
    const button = document.getElementById('myButton');
    button.addEventListener('click', () => {
      alert('A gombra kattintottál!');
    });
  </script>
  ```

### 3. **Promise-ok és az `async/await` varázsa**

- **Promise-ok:** Aszinkron műveletek eredményének kezelése.

  **Példa előtte és utána:**

  *Előtte (callback hell):*

  ```javascript
  doSomething(function(result) {
    doSomethingElse(result, function(newResult) {
      doThirdThing(newResult, function(finalResult) {
        console.log('Végeredmény: ' + finalResult);
      });
    });
  });
  ```

  *Utána (Promise-ok használatával):*

  ```javascript
  doSomething()
    .then(result => doSomethingElse(result))
    .then(newResult => doThirdThing(newResult))
    .then(finalResult => {
      console.log('Végeredmény: ' + finalResult);
    })
    .catch(error => {
      console.error(error);
    });
  ```

- **`async/await`:** Aszinkron kód írása szinkron módon.

  **Példa előtte és utána:**

  *Előtte (Promise láncolással):*

  ```javascript
  fetchData()
    .then(data => {
      return processData(data);
    })
    .then(result => {
      console.log(result);
    })
    .catch(error => {
      console.error(error);
    });
  ```

  *Utána (`async/await` használatával):*

  ```javascript
  async function getData() {
    try {
      const data = await fetchData();
      const result = await processData(data);
      console.log(result);
    } catch (error) {
      console.error(error);
    }
  }

  getData();
  ```

### 4. **JSON – az adatok csomagolása és kibontása**

- **`JSON.stringify()`:** Objektumok JSON formátumú szöveggé alakítása.

  **Példa előtte és utána:**

  *Előtte (objektum egyszerű szöveggé alakítása):*

  ```javascript
  const data = { name: 'Peter', age: 28 };
  const stringData = 'name=' + data.name + '&age=' + data.age;

  console.log(stringData); // 'name=Peter&age=28'
  ```

  *Utána (`JSON.stringify()` használatával):*

  ```javascript
  const data = { name: 'Peter', age: 28 };
  const jsonData = JSON.stringify(data);

  console.log(jsonData); // '{"name":"Peter","age":28}'
  ```

- **`JSON.parse()`:** JSON szöveg visszaalakítása objektummá.

  **Példa előtte és utána:**

  *Előtte (szöveg manuális feldolgozása):*

  ```javascript
  const jsonData = '{"name":"Peter","age":28}';
  const parts = jsonData.replace(/[\{\}"]/g, '').split(',');

  const data = {};
  parts.forEach(part => {
    const [key, value] = part.split(':');
    data[key] = value;
  });

  console.log(data); // { name: 'Peter', age: '28' }
  ```

  *Utána (`JSON.parse()` használatával):*

  ```javascript
  const jsonData = '{"name":"Peter","age":28}';
  const data = JSON.parse(jsonData);

  console.log(data); // { name: 'Peter', age: 28 }
  ```

### 5. **REST API-k – Híd az alkalmazások között**

- **HTTP kérések:** GET, POST, PUT, DELETE használata.

  **Példa előtte és utána:**

  *Előtte (adatok lekérése böngészőben):*

  - A felhasználó megnyit egy URL-t, és az adatokat a szerver visszaküldi.

  *Utána (`fetch()` használatával egy GET kérés):*

  ```javascript
  fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
      console.log(data);
    })
    .catch(error => {
      console.error('Hiba történt:', error);
    });
  ```

- **API végpontok használata:** Nyilvános API-k integrálása.

  **Példa előtte és utána:**

  *Előtte (statikus adatok használata):*

  ```javascript
  const weather = {
    city: 'Budapest',
    temperature: 20
  };

  console.log(`Az aktuális hőmérséklet ${weather.city}-ben ${weather.temperature}°C.`);
  ```

  *Utána (időjárás adatok lekérése API-ból):*

  ```javascript
  fetch('https://api.weatherapi.com/v1/current.json?key=API_KULCS&q=Budapest')
    .then(response => response.json())
    .then(data => {
      console.log(`Az aktuális hőmérséklet ${data.location.name}-ben ${data.current.temp_c}°C.`);
    })
    .catch(error => {
      console.error('Hiba történt:', error);
    });
  ```

### 6. **AJAX és a `fetch()` – Adatkommunikáció a háttérben**

- **`fetch()` függvény:** Adatok lekérése és küldése egyszerűen.

  **Példa előtte és utána:**

  *Előtte (XMLHttpRequest használatával):*

  ```javascript
  const xhr = new XMLHttpRequest();
  xhr.open('GET', 'https://api.example.com/data', true);
  xhr.onload = function() {
    if (xhr.status === 200) {
      const data = JSON.parse(xhr.responseText);
      console.log(data);
    }
  };
  xhr.send();
  ```

  *Utána (`fetch()` használatával):*

  ```javascript
  fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
      console.log(data);
    })
    .catch(error => {
      console.error('Hiba történt:', error);
    });
  ```

- **Adatkezelés a háttérben:** Dinamikus oldalak készítése.

  **Példa előtte és utána:**

  *Előtte (oldal újratöltése adatok frissítéséhez):*

  - A felhasználónak frissítenie kell az oldalt, hogy lássa a legújabb adatokat.

  *Utána (dinamikus frissítés `fetch()`-kel):*

  ```javascript
  function updateData() {
    fetch('https://api.example.com/latest')
      .then(response => response.json())
      .then(data => {
        document.getElementById('dataContainer').innerText = data.value;
      })
      .catch(error => {
        console.error('Hiba történt:', error);
      });
  }

  // Adatok frissítése 5 másodpercenként
  setInterval(updateData, 5000);
  ```

---

Találkozunk az órán!