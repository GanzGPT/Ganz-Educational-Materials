```javascript
// Egyszerű arrow függvény, amely egy számot növel 1-el
const addOne = (x) => x + 1;

// Két szám összegét visszaadó arrow függvény
const add = (a, b) => a + b;

// Egyetlen paraméter esetén a zárójel elhagyható
const square = x => x * x;

// Üres paraméter lista esetén üres zárójelek szükségesek
const sayHello = () => console.log('Hello!');

// Több utasítás esetén a függvénytörzsben blokk használata szükséges
const multiplyAndLog = (a, b) => {
  const result = a * b;
  console.log(result);
  return result;
};

// Visszatérési objektum esetén a zárójelek szükségesek
const createUser = (name, age) => ({ name, age });

// Tömb minden elemének megduplázása arrow függvénnyel és map() metódussal
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);

// Arrow függvények a callback-ekben
setTimeout(() => console.log('Time is up!'), 1000);

// Arrow függvények használata filter()-rel
const evenNumbers = numbers.filter(num => num % 2 === 0);

// Arrow függvény beágyazott objektum metódusban - fontos figyelni a 'this' kontextusra
const person = {
  name: 'Alice',
  hobbies: ['reading', 'cycling', 'swimming'],
  printHobbies: function() {
    this.hobbies.forEach(hobby => {
      console.log(`${this.name} likes ${hobby}`);
    });
  }
};

// Arrow függvény használata Promise-ban
const asyncOperation = () => new Promise((resolve, reject) => {
  const success = true;
  if (success) {
    resolve('Operation successful');
  } else {
    reject('Operation failed');
  }
});

// Tömb elemeinek összegzése reduce() metódussal arrow függvénnyel
const sum = numbers.reduce((total, num) => total + num, 0);

// Arrow függvény használata sort() metódussal
const sortedNumbers = numbers.sort((a, b) => a - b);

// Arrow függvény használata find() metódussal
const firstEven = numbers.find(num => num % 2 === 0);

// Arrow függvény használata some() metódussal
const hasNegative = numbers.some(num => num < 0);

// Arrow függvény használata every() metódussal
const allPositive = numbers.every(num => num > 0);

// Arrow függvény használata forEach() metódussal
numbers.forEach(num => console.log(num));
```
