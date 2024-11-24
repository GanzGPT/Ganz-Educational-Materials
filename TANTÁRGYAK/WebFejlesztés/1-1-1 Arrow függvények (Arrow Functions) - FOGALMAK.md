# Arrow függvények (Arrow Functions) - FOGALMAK

## Arrow függvény szintaxis
```javascript
const add = (a, b) => a + b;
```

## Rövid szintaxis egy kifejezés visszaadására
```javascript
const square = x => x * x;
```

## Arrow függvények és a “this” kontextus
```javascript
function Person() {
  this.age = 0;
  setInterval(() => {
    this.age++; // Az arrow függvény megőrzi a 'this' kontextust
  }, 1000);
}
const p = new Person();
```

## Funkcionális programozásban való használat
```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
```

## Paraméterek kezelése (egyetlen és több paraméter)
```javascript
const greet = name => `Hello, ${name}!`;
const add = (a, b) => a + b;
```

## Korlátozások és különbségek a hagyományos függvényekhez képest
```javascript
// Arrow függvények nem használhatók konstruktorokként
const Func = () => {};
const obj = new Func(); // Hibát okoz
```

## Implicit return (visszatérés egy kifejezéssel)
```javascript
const multiply = (a, b) => a * b; // Nincs szükség 'return' kulcsszóra
```

## Arrow függvények és az “arguments” objektum
```javascript
function traditionalFunction() {
  console.log(arguments); // Az 'arguments' objektum elérhető
}
const arrowFunction = () => {
  console.log(arguments); // Hibát okoz, az 'arguments' nem elérhető
};
```

## Arrow függvények használata callback-ekben
```javascript
setTimeout(() => {
  console.log('Ez egy callback arrow függvényben.');
}, 1000);
```

## Lexikális “this” kötés
```javascript
class Counter {
  constructor() {
    this.count = 0;
    setInterval(() => {
      this.count++;
      console.log(this.count);
    }, 1000);
  }
}
const counter = new Counter();
```

## Default paraméterek kezelése arrow függvényekkel
```javascript
const greet = (name = 'Világ') => `Hello, ${name}!`;
```

## Arrow függvények használata objektumokban
```javascript
const obj = {
  value: 42,
  getValue: () => this.value // 'this' lexikális, nem az obj-ra mutat
};
console.log(obj.getValue()); // undefined
```

## Arrow függvények és az explicit `return` használata
```javascript
const add = (a, b) => {
  return a + b; // Itt explicit használjuk a 'return' kulcsszót
};
```

## Összehasonlítás hagyományos függvényekkel teljesítmény szempontjából
```javascript
// Arrow függvények gyorsabbak lehetnek, de nem mindig. Ezt inkább az adott használati eset határozza meg.
const traditionalFunction = function(a, b) {
  return a + b;
};
const arrowFunction = (a, b) => a + b;
```

## Arrow függvények komponensként való használata JavaScript frameworkökben, mint a React
```javascript
const Button = () => (
  <button>Kattints rám!</button>
);
```

