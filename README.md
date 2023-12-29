<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ghastrium</title>
    <style>
        canvas {
            border: 1px solid #000;
        }
    </style>
</head>
<body>
   <canvas id="gameCanvas" width="800" height="600"></canvas>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');

        // Ghost Object
        const ghost = {
            x: 50,
            y: 50,
            radius: 20,
            color: '#00F'
        };
        
        function drawGhost() {
            ctx.beginPath();
            ctx.arc(ghost.x, ghost.y, ghost.radius, 0, 2 * Math.PI);
            ctx.fillStyle = ghost.color;
            ctx.fill();
            ctx.closePath();
        }
        
        function updateGameArea() {
            // Clear the canvas
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Draw the ghost
            drawGhost();
            
            // Move the ghost (for demo purposes)
            ghost.x +=1;
            
            //request the next animation frame
            requestAnimationFrame(updateGameArea);
        }
        
        // Start the game loop
        updateGameArea();
    </script>
</body>
</html>
