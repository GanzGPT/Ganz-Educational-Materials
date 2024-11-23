# Az 5 legfontosabb művelet, amelyeket arrow függvényekkel végezhetsz

- **Matematikai műveletek** (összeadás, kivonás, szorzás, osztás)
- **Logikai műveletek** (feltételek kiértékelése, például `&&`, `||`)
- **Tömbműveletek** (például `map()`, `filter()`, `reduce()`)
- **Eseménykezelés** (például click eseményekhez való függvény hozzárendelés)
- **Objektum tulajdonságainak elérése és manipulálása**

## Matematikai Műveletek Arrow Függvényekkel - Példafeladatok

### Összeadás
```javascript
const add = (a, b) => a + b;
console.log(add(5, 3)); // Eredmény: 8
```

### Kivonás
```javascript
const subtract = (a, b) => a - b;
console.log(subtract(10, 4)); // Eredmény: 6
```

### Szorzás
```javascript
const multiply = (a, b) => a * b;
console.log(multiply(6, 7)); // Eredmény: 42
```

### Osztás
```javascript
const divide = (a, b) => a / b;
console.log(divide(20, 5)); // Eredmény: 4
```

### Négyzetre emelés
```javascript
const square = a => a * a;
console.log(square(4)); // Eredmény: 16
```

### Maradékos osztás
```javascript
const modulus = (a, b) => a % b;
console.log(modulus(10, 3)); // Eredmény: 1
```

### Hatványozás
```javascript
const power = (a, b) => a ** b;
console.log(power(2, 3)); // Eredmény: 8
```

### Abszolút érték
```javascript
const absolute = a => Math.abs(a);
console.log(absolute(-7)); // Eredmény: 7
```

### Négyzetgyök
```javascript
const sqrt = a => Math.sqrt(a);
console.log(sqrt(25)); // Eredmény: 5
```

### Maximum két szám között
```javascript
const max = (a, b) => Math.max(a, b);
console.log(max(8, 15)); // Eredmény: 15
```

## Logikai Műveletek Arrow Függvényekkel - Példafeladatok

### Két szám összehasonlítása (nagyobb-e)
```javascript
const isGreater = (a, b) => a > b;
console.log(isGreater(10, 5)); // Eredmény: true
```

### Két szám egyenlősége
```javascript
const isEqual = (a, b) => a === b;
console.log(isEqual(4, 4)); // Eredmény: true
```

### Páros szám ellenőrzése
```javascript
const isEven = a => a % 2 === 0;
console.log(isEven(8)); // Eredmény: true
```

### Háromszög oldalainak ellenőrzése (érvényes háromszög-e)
```javascript
const isValidTriangle = (a, b, c) => a + b > c && a + c > b && b + c > a;
console.log(isValidTriangle(3, 4, 5)); // Eredmény: true
```

### Pozitív szám ellenőrzése
```javascript
const isPositive = a => a > 0;
console.log(isPositive(-3)); // Eredmény: false
```

## Tömbműveletek Arrow Függvényekkel - Példafeladatok

### Tömb elemeinek megduplázása
```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Eredmény: [2, 4, 6, 8]
```

### Páros számok kiszűrése
```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Eredmény: [2, 4, 6]
```

### Tömb elemeinek összeadása
```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Eredmény: 10
```

## Eseménykezelés Arrow Függvényekkel - Példafeladatok

### Gomb kattintás kezelése
```html
<button id="myButton">Kattints rám!</button>
<script>
document.getElementById('myButton').addEventListener('click', () => {
  console.log('Gomb megnyomva!');
});
</script>
```

### Billentyű lenyomás esemény kezelése
```html
<input type="text" placeholder="Írj valamit...">
<script>
document.addEventListener('keydown', (event) => {
  console.log(`Lenyomott billentyű: ${event.key}`);
});
</script>
```

## Objektum Tulajdonságainak Elérése és Manipulálása Arrow Függvényekkel - Példafeladatok

### Objektum tulajdonságának elérése
```javascript
const person = { name: 'Alice', age: 25 };
const getName = () => person.name;
console.log(getName()); // Eredmény: Alice
```

### Objektum tulajdonságának módosítása
```javascript
const person = { name: 'Alice', age: 25 };
const updateAge = (newAge) => person.age = newAge;
updateAge(30);
console.log(person.age); // Eredmény: 30
```

### Új tulajdonság hozzáadása az objektumhoz
```javascript
const person = { name: 'Alice', age: 25 };
const addProperty = (obj, key, value) => obj[key] = value;
addProperty(person, 'city', 'Budapest');
console.log(person.city); // Eredmény: Budapest
```

### Tulajdonság törlése az objektumból
```javascript
const person = { name: 'Alice', age: 25, city: 'Budapest' };
const deleteProperty = (obj, key) => delete obj[key];
deleteProperty(person, 'age');
console.log(person.age); // Eredmény: undefined
```

### Objektum tulajdonságainak listázása
```javascript
const person = { name: 'Alice', age: 25, city: 'Budapest' };
const listProperties = (obj) => Object.keys(obj);
console.log(listProperties(person)); // Eredmény: ['name', 'age', 'city']
