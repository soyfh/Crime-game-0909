# Crime-game-0909
This game is best game in the world 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crime Escape Game</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #f0f0f0;
        }
        canvas {
            display: block;
            margin: 0 auto;
            background-color: #e5e5e5;
        }
    </style>
</head>
<body>
    <script>
        let canvas = document.createElement("canvas");
        let ctx = canvas.getContext("2d");
        canvas.width = 800;
        canvas.height = 600;
        document.body.appendChild(canvas);

        let player = { x: 50, y: 50, size: 20, speed: 5 };
        let police = { x: 700, y: 500, size: 20, speed: 2 };
        let crimeZone = { x: 400, y: 300, size: 30, robbed: false };

        function drawRect(obj, color) {
            ctx.fillStyle = color;
            ctx.fillRect(obj.x, obj.y, obj.size, obj.size);
        }

        function updatePolice() {
            if (crimeZone.robbed) {
                let dx = player
