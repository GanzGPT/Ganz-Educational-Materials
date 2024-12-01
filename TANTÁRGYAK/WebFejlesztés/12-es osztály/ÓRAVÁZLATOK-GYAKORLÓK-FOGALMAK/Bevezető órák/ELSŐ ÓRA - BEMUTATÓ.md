**Hagyományos függvény használata az eseménykezelőben**

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hagyományos függvény példa</title>
</head>
<body>
    <h1>Hagyományos függvény példa</h1>
    <button id="myButton">Kattints rám!</button>
    <p id="message"></p>

    <script>
        // Hozzáférünk a gombhoz és a bekezdéshez
        var button = document.getElementById('myButton');
        var messageParagraph = document.getElementById('message');

        // Hagyományos függvény használata az eseménykezelőben
        button.addEventListener('click', function() {
            messageParagraph.textContent = 'A hagyományos függvény működik! 🎉';
        });
    </script>
</body>
</html>
```

**Arrow függvény használata az eseménykezelőben**

```html
<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arrow függvény példa</title>
</head>
<body>
    <h1>Arrow függvény példa</h1>
    <button id="myButton">Kattints rám!</button>
    <p id="message"></p>

    <script>
        // Hozzáférünk a gombhoz és a bekezdéshez
        const button = document.getElementById('myButton');
        const messageParagraph = document.getElementById('message');

        // Arrow függvény használata az eseménykezelőben
        button.addEventListener('click', () => {
            messageParagraph.textContent = 'Az arrow függvény működik! 🎉';
        });
    </script>
</body>
</html>
```


