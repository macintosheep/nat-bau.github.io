<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AR Ausstellung</title>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: flex-start;
            align-items: center;
            flex-direction: column;
            height: 100vh;
            background-color: #DABFFF; /* Default to Pastelllila */
            color: #fff;
            font-family: 'Press Start 2P', cursive;
            overflow: hidden;
            position: relative;
        }
        .glitch {
            margin-top: 20px; /* Adjust this value to control the distance from the top */
            font-size: 3em;
        }
        .color-picker {
            position: absolute;
            bottom: 20px;
            right: 20px;
        }
        .color-picker select {
            font-family: 'Press Start 2P', cursive;
            font-size: 1em;
            padding: 5px;
            background-color: #fff;
            border: 1px solid #ccc;
            color: #333;
        }
        .checkerboard-pattern {
            background-image:
                repeating-linear-gradient(to bottom, #FFAB80, #FFAB80 40px, transparent 40px),
                repeating-linear-gradient(to right, #FFAB80, #FFAB80 40px, transparent 40px);
            background-size: 240px 240px; /* Größe des Hintergrundbilds, um 6 Rechtecke zu erstellen */
        }
        .ananas-special {
            background-color: #FFE600; /* Warmes Gelb für Ananas Spezial */
        }
    </style>
</head>
<body>
    <h1 class="glitch">AR Ausstellung</h1>
    <div class="color-picker">
        <select id="colorSelector">
            <option value="#DABFFF">Pastelllila</option>
            <option value="#FFAB80">Pastellorange</option>
            <option value="#B5EAD7">Pastellgrün</option>
            <option value="#C7CEEA">Pastellblau</option>
            <option value="ananas-special">Ananas Spezial</option>
        </select>
    </div>
    <script>
        document.getElementById('colorSelector').addEventListener('change', function(event) {
            if (event.target.value === 'checkerboard-pattern') {
                document.body.classList.add('checkerboard-pattern');
                document.body.classList.remove('ananas-special');
                document.body.style.backgroundColor = '';
            } else if (event.target.value === 'ananas-special') {
                document.body.classList.add('ananas-special');
                document.body.classList.remove('checkerboard-pattern');
                document.body.style.backgroundColor = '';
            } else {
                document.body.classList.remove('checkerboard-pattern');
                document.body.classList.remove('ananas-special');
                document.body.style.backgroundColor = event.target.value;
            }
        });
    </script>
</body>
</html>
