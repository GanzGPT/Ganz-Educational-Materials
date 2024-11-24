# Tömbökkel kapcsolatos függvények a spread operátor használatához

### Tömbök összefűzése spread operátorral:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const combinedArray = [...array1, ...array2];
console.log(combinedArray); // [1, 2, 3, 4, 5, 6]
```

### Tömb másolása spread operátorral:

```javascript
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];
console.log(copiedArray); // [1, 2, 3]
```

### Elemek hozzáadása egy tömb elejéhez:

```javascript
const numbers = [2, 3, 4];
const updatedNumbers = [1, ...numbers];
console.log(updatedNumbers); // [1, 2, 3, 4]
```

### Elemek hozzáadása egy tömb végéhez:

```javascript
const fruits = ['apple', 'banana'];
const moreFruits = [...fruits, 'orange'];
console.log(moreFruits); // ['apple', 'banana', 'orange']
```

### Több tömb egyesítése egybe:

```javascript
const arr1 = [1, 2];
const arr2 = [3, 4];
const arr3 = [5, 6];
const combined = [...arr1, ...arr2, ...arr3];
console.log(combined); // [1, 2, 3, 4, 5, 6]
```

### Tömb elemeinek használata függvény argumentumként:

```javascript
const values = [10, 20, 30];
const sum = (a, b, c) => a + b + c;
console.log(sum(...values)); // 60
```

### Tömb létrehozása egy meglévő tömbből, plusz új elemekkel:

```javascript
const baseArray = [4, 5, 6];
const extendedArray = [1, 2, 3, ...baseArray, 7, 8];
console.log(extendedArray); // [1, 2, 3, 4, 5, 6, 7, 8]
```

### Tömb duplikátumainak eltávolítása spread operátorral és Set-tel:

```javascript
const duplicateArray = [1, 2, 2, 3, 4, 4, 5];
const uniqueArray = [...new Set(duplicateArray)];
console.log(uniqueArray); // [1, 2, 3, 4, 5]
```

### Array concat() helyett spread operátor használata:

```javascript
const arrayA = ['a', 'b'];
const arrayB = ['c', 'd'];
const concatenated = [...arrayA, ...arrayB];
console.log(concatenated); // ['a', 'b', 'c', 'd']
```

### Spread operátor használata Array.from()-nal:

```javascript
const arrayLike = { 0: 'hello', 1: 'world', length: 2 };
const array = Array.from(arrayLike);
const spreadArray = [...array];
console.log(spreadArray); // ['hello', 'world']
```

## Függvények alternatívája a spread operátor használatával

- **Tömbök összefűzése spread operátorral**: `concat()` helyett spread operátor
- **Tömb másolása spread operátorral**: `slice()` helyett spread operátor
- **Elemek hozzáadása egy tömb elejéhez**: `unshift()` alternatívája
- **Elemek hozzáadása egy tömb végéhez**: `push()` alternatívája
- **Több tömb egyesítése egybe**: `concat()` helyett spread operátor
- **Tömb elemeinek használata függvény argumentumként**: `Function.apply()` helyett spread operátor
- **Tömb létrehozása egy meglévő tömbből, plusz új elemekkel**: `concat()` és `push()` kombinációja helyett spread operátor
- **Tömb duplikátumainak eltávolítása spread operátorral és Set-tel**: `Set()` használata spread operátorral
- **Array concat() helyett spread operátor használata**: `concat()`
- **Spread operátor használata Array.from()-nal**: `Array.from()` és spread operátor kombinálása
