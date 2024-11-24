# Spread operátor fogalomtára (középiskolás szinten)

### Spread operátor (...):
Egy JavaScript-eszköz, amely lehetővé teszi, hogy egy tömb vagy objektum elemeit könnyen szétoszthassuk vagy éppen egyesítsük más elemekkel.

### Tömbök másolása:
A spread operátor segítségével könnyen lehet másolni egy tömb elemeit új tömbökként anélkül, hogy megváltoztatnánk az eredeti tömböt.

### Tömbök kombinálása:
A spread operátor lehetővé teszi több tömb elemeinek összeolvasztását egy új tömbbé.

### Objektumok másolása:
Az operátor segítségével másolhatunk egy objektumot, így anélkül hozhatunk létre új objektumokat, hogy megváltoztatnánk az eredetit.

### Objektumok kombinálása:
Segítségével könnyen össze lehet vonni több objektumot egy új objektumba, megőrizve az eredeti objektumok tulajdonságait.

### Shallow copy (sekély másolat):
A spread operátor csak sekély másolatot készít, vagyis az objektumok vagy tömbök összetettebb (pl. beágyazott) elemeit nem másolja újra, hanem azokra hivatkozásokat tartalmaz.

### Elemek szétosztása:
A spread operátor lehetővé teszi, hogy egy tömb vagy objektum összes elemét közvetlenül felhasználjuk, például egy új tömb vagy objektum létrehozásakor.

### Immutable (változtathatatlan) műveletek:
A spread operátor hasznos olyan esetekben, amikor nem akarjuk megváltoztatni az eredeti tömböt vagy objektumot, hanem új változatokat akarunk létrehozni.

### Function arguments (függvényargumentumok):
A spread operátort használhatjuk arra is, hogy egy tömb elemeit közvetlenül egy függvény paramétereként adjuk át.

### Iterables (iterálható elemek):
A spread operátor működik minden olyan adattípussal, amely iterálható, mint például tömbök vagy sztringek.

### Spread operátor használata objektum inicializálásában:
Hasznos lehet új objektum létrehozásánál, amely tartalmazza egy másik objektum összes tulajdonságát, esetleg néhány további tulajdonsággal bővítve.

### Array.prototype.concat() vs. spread:
A spread operátor egyszerűbb módja tömbök összevonásának, mint a hagyományos `concat()` metódus.

### Referenciák kezelése:
A spread operátor segítségével elkerülhető, hogy a másolt tömb vagy objektum referenciaként viselkedjen, így könnyebben tudunk dolgozni változtathatatlan adatstruktúrákkal.
