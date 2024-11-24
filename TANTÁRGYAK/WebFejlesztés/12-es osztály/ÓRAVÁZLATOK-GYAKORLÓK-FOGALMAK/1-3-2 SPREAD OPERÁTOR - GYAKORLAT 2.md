# Objektumokkal kapcsolatos függvények a spread operátor használatához

### Objektumok másolása spread operátorral:

```javascript
const originalObject = { name: 'John', age: 30 };
const copiedObject = { ...originalObject };
console.log(copiedObject); // { name: 'John', age: 30 }
```

### Objektumok kombinálása (két objektum egyesítése):

```javascript
const obj1 = { firstName: 'John' };
const obj2 = { lastName: 'Doe' };
const combinedObject = { ...obj1, ...obj2 };
console.log(combinedObject); // { firstName: 'John', lastName: 'Doe' }
```

### Objektum kiegészítése új tulajdonságokkal:

```javascript
const person = { name: 'Alice' };
const extendedPerson = { ...person, age: 25 };
console.log(extendedPerson); // { name: 'Alice', age: 25 }
```

### Objektumok összeolvasztása prioritásos tulajdonságokkal:

```javascript
const defaultSettings = { theme: 'light', notifications: true };
const userSettings = { theme: 'dark' };
const finalSettings = { ...defaultSettings, ...userSettings };
console.log(finalSettings); // { theme: 'dark', notifications: true }
```

### Több objektum összevonása egy objektummá:

```javascript
const objA = { a: 1 };
const objB = { b: 2 };
const objC = { c: 3 };
const mergedObject = { ...objA, ...objB, ...objC };
console.log(mergedObject); // { a: 1, b: 2, c: 3 }
```

### Létező objektum másolása és egy tulajdonság megváltoztatása:

```javascript
const book = { title: 'JavaScript Basics', pages: 200 };
const updatedBook = { ...book, pages: 250 };
console.log(updatedBook); // { title: 'JavaScript Basics', pages: 250 }
```

### Objektum másolása és új tulajdonság hozzáadása feltételesen:

```javascript
const user = { username: 'john_doe' };
const isAdmin = true;
const userWithRole = { ...user, ...(isAdmin ? { role: 'admin' } : {}) };
console.log(userWithRole); // { username: 'john_doe', role: 'admin' }
```

### Objektumok kombinálása, ha egy tulajdonság hiányzik:

```javascript
const defaultUser = { username: 'guest', active: true };
const actualUser = { username: 'real_user' };
const mergedUser = { ...defaultUser, ...actualUser };
console.log(mergedUser); // { username: 'real_user', active: true }
```

### Beágyazott objektumok másolása spread operátorral:

```javascript
const userProfile = { name: 'Jane', details: { age: 28, city: 'New York' } };
const copiedProfile = { ...userProfile, details: { ...userProfile.details } };
console.log(copiedProfile); // { name: 'Jane', details: { age: 28, city: 'New York' } }
```

### Objektumok összevonása egy alapértelmezett és egyedi konfigurációból:

```javascript
const defaultConfig = { language: 'en', debug: false };
const userConfig = { debug: true };
const finalConfig = { ...defaultConfig, ...userConfig };
console.log(finalConfig); // { language: 'en', debug: true }
```

## Függvények alternatívája a spread operátor használatával

- **Objektumok másolása spread operátorral**: `Object.assign({}, originalObject)` helyett használható a spread operátor.
- **Objektumok kombinálása (két objektum egyesítése)**: `Object.assign({}, obj1, obj2)` helyett használható a spread operátor.
- **Objektum kiegészítése új tulajdonságokkal**: `Object.assign({}, person, { age: 25 })` helyett használható a spread operátor.
- **Objektumok összeolvasztása prioritásos tulajdonságokkal**: `Object.assign({}, defaultSettings, userSettings)` helyett használható a spread operátor.
- **Több objektum összevonása egy objektummá**: `Object.assign({}, objA, objB, objC)` helyett használható a spread operátor.
- **Létező objektum másolása és egy tulajdonság megváltoztatása**: `Object.assign({}, book, { pages: 250 })` helyett használható a spread operátor.
- **Objektum másolása és új tulajdonság hozzáadása feltételesen**: A spread operátor segítségével a feltételes tulajdonságot egyszerűen hozzáadhatjuk, míg `Object.assign` esetén külön műveletek kellenek.
- **Objektumok kombinálása, ha egy tulajdonság hiányzik**: `Object.assign({}, defaultUser, actualUser)` helyett használható a spread operátor.
- **Beágyazott objektumok másolása spread operátorral**: A beágyazott objektumok másolása során használható a spread operátor az objektum mélységi másolatához, ami egy alternatív megoldás az `Object.assign` helyett.
- **Objektumok összevonása egy alapértelmezett és egyedi konfigurációból**: `Object.assign({}, defaultConfig, userConfig)` helyett használható a spread operátor.

Ezek a példák azt mutatják, hogyan lehet az `Object.assign()` függvényt vagy a bonyolultabb összevonási műveleteket egyszerűsíteni és helyettesíteni a spread operátorral JavaScript-ben. A spread operátor tisztább és olvashatóbb kódot eredményez, különösen akkor, ha objektumokat szeretnénk kombinálni vagy módosítani.
