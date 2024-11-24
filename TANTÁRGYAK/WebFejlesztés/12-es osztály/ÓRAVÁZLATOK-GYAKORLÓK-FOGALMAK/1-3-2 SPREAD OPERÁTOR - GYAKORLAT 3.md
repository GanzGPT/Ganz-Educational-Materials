# Spread operátorral kombinálható függvények

Íme 10 példakód, amelyek bemutatják a spread operátor kombinálását különböző függvényekkel JavaScript-ben. Ezeket a példákat bármelyik JavaScript környezetben (például böngésző konzoljában vagy Node.js-ben) kipróbálhatod.

### 1. Math.max() tömb elemeivel

A `Math.max()` függvénnyel kombinálva a spread operátorral átadhatjuk a tömb elemeit argumentumként.

```javascript
const numbers = [10, 5, 8, 20, 3];
const maxNumber = Math.max(...numbers);
console.log(maxNumber); // 20
```

### 2. Math.min() tömb elemeivel

A `Math.min()` függvénnyel kombinálva a spread operátorral átadhatjuk a tömb elemeit argumentumként.

```javascript
const numbers = [10, 5, 8, 20, 3];
const minNumber = Math.min(...numbers);
console.log(minNumber); // 3
```

### 3. Function.apply() alternatívája spread operátorral

A `Function.apply()` helyett használhatjuk a spread operátort a függvényhívás argumentumainak átadására.

```javascript
function greet(greeting, name) {
  console.log(`${greeting}, ${name}!`);
}

const args = ['Hello', 'John'];
greet(...args); // Hello, John!
```

### 4. Array.prototype.push() több elem hozzáadásához

A `push()` függvénnyel kombinálva a spread operátorral több elem is hozzáadható egyszerre.

```javascript
const array = [1, 2, 3];
const newElements = [4, 5, 6];
array.push(...newElements);
console.log(array); // [1, 2, 3, 4, 5, 6]
```

### 5. console.log() tömb elemeinek kiíratása különálló argumentumokként

A spread operátorral egy tömb elemei különálló argumentumokként adhatók át a `console.log()` függvénynek.

```javascript
const array = ['apple', 'banana', 'cherry'];
console.log(...array); // apple banana cherry
```

### 6. Math.pow() tömb elemeinek hatványozása `map()`-pel

A spread operátorral egy tömböt másolhatunk, majd a `map()` függvénnyel alkalmazhatunk rá műveletet.

```javascript
const baseNumbers = [2, 3, 4];
const poweredNumbers = [...baseNumbers].map(num => Math.pow(num, 2));
console.log(poweredNumbers); // [4, 9, 16]
```

### 7. Több tömb egyesítése és Math.max() meghívása

A spread operátorral több tömböt egyesíthetünk, majd `Math.max()`-szal meghatározhatjuk a legnagyobb értéket.

```javascript
const arr1 = [1, 5, 9];
const arr2 = [3, 7, 8];
const combinedArray = [...arr1, ...arr2];
const maxValue = Math.max(...combinedArray);
console.log(maxValue); // 9
```

### 8. Array.prototype.unshift() több elem hozzáadásához a tömb elejére

A `unshift()` függvénnyel a spread operátor segítségével több elem is hozzáadható egy tömb elejére.

```javascript
const array = [4, 5, 6];
const newElements = [1, 2, 3];
array.unshift(...newElements);
console.log(array); // [1, 2, 3, 4, 5, 6]
```

### 9. Array.prototype.concat() helyett spread operátor több tömb egyesítésére

A `concat()` függvény helyett a spread operátorral több tömb egyesíthető.

```javascript
const array1 = [1, 2];
const array2 = [3, 4];
const array3 = [5, 6];
const combinedArray = [...array1, ...array2, ...array3];
console.log(combinedArray); // [1, 2, 3, 4, 5, 6]
```

### 10. Math.max() és Math.min() kombinálása tömb elemeivel

A spread operátorral meghatározhatjuk egy tömb elemeinek maximumát és minimumát is.

```javascript
const values = [15, 7, 22, 1, 13];
const maxValue = Math.max(...values);
const minValue = Math.min(...values);
console.log(`Max: ${maxValue}, Min: ${minValue}`); // Max: 22, Min: 1
```

Ezek a példák bemutatják, hogyan lehet a spread operátort kombinálni különböző JavaScript függvényekkel, hogy hatékonyabb, tisztább és egyszerűbb kódot érjünk el a tömbműveletek során. A spread operátor különösen jól működik függvényekkel, amelyek több argumentumot várnak, és tömbök kezelésében is nagyon hasznos.

## Gyakorolt koncepciók

1. **Math.max() tömb elemeivel**: Spread operátor használata tömb elemeinek átadására egy függvényhez, amely több argumentumot vár (maximum érték meghatározása).
2. **Math.min() tömb elemeivel**: Spread operátor használata tömb elemeinek átadására egy függvényhez, amely több argumentumot vár (minimum érték meghatározása).
3. **Function.apply() alternatívája spread operátorral**: `Function.apply()` helyettesítése spread operátorral, hogy tömb elemeit függvény argumentumokként átadhassuk.
4. **Array.prototype.push() több elem hozzáadásához**: Spread operátor használata több elem egyszerre történő hozzáadásához egy tömbhöz a `push()` függvénnyel.
5. **console.log() tömb elemeinek kiíratása különálló argumentumokként**: Spread operátor használata tömb elemeinek különálló argumentumokként való kiíratására.
6. **Math.pow() tömb elemeinek hatványozása `map()`-pel**: Spread operátor használata tömb másolására, majd `map()` függvénnyel történő elemművelet végrehajtása.
7. **Több tömb egyesítése és Math.max() meghívása**: Több tömb egyesítése spread operátorral, majd a maximum érték meghatározása `Math.max()` segítségével.
8. **Array.prototype.unshift() több elem hozzáadásához a tömb elejére**: Spread operátor használata több elem hozzáadására a tömb elejére a `unshift()` függvénnyel.
9. **Array.prototype.concat() helyett spread operátor több tömb egyesítésére**: Több tömb egyesítése `concat()` helyett spread operátorral.
10. **Math.max() és Math.min() kombinálása tömb elemeivel**: Spread operátor használata egy tömb elemeinek átadására két különböző függvénynek (`Math.max()` és `Math.min()`) a maximum és minimum érték meghatározása érdekében.

Ezek a feladatok a spread operátor különböző felhasználási módjait gyakoroltatják, például függvényhívások argumentumainak átadására, tömbök egyesítésére és módosítására. Mindegyik feladat különféle gyakorlati koncepciókra fókuszál, amelyek segítenek a spread operátor rugalmas alkalmazásában JavaScript környezetben.
