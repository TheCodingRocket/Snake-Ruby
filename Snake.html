# Snake-2D-
<!DOCTYPE html>
<html>
    <head>
        <title>Pancake - Snake</title>
    </head>
    <body>
        <script src="../build/pancake.js"></script>
        <canvas id="canvas" onclick="pancake.graphics.toggleFullscreen();"></canvas>
        <script>
            if (window.localStorage === undefined) {
                alert("Browser does not support offline localStorage,So online version will open");
                pancake.browser.open("https://rabios.github.io/Pancake/games/snake.html");
            }

            // Create context and set it external canvas with id "canvas"
            // Set created context index to 0
            // Set canvas index to 0,Since custom canvases can't have index
            pancake.context.use(document.getElementById("canvas"), 0);

            // Resize canvas to fit the window
            pancake.canvas.resize(pancake.canvas.compatible_width, pancake.canvas.compatible_height, 0);
            
            // Set background color
            pancake.graphics.setBackgroundColor("black");
            
            var grid_size = 32;
            var count = 0, score = 0, highscore = Number(pancake.storage.load("highscore")) || 0;
            
            var snake = {
                x: 0, y: 0,
                // Snake velocity. Moves one grid_size length every frame in either the x or y direction
                vx: grid_size, vy: 0,
  
                // Keep track of all grid_sizes the snake body occupies
                cells: [],
  
                // Length of the snake.Grows when eating an apple
                maxCells: 1
            };

            var apple = { x: 120, y: 120 };

            function game() {
                window.animate(game, 120);
                
                // Slow game loop to 30 fps instead of 120 (120 / 30 = 4)
                if (++count < 4) {
                    return;
                }
                
                count = 0;
                pancake.graphics.clear();

                // Update snake position
                snake.x += snake.vx;
                snake.y += snake.vy;
                
                // Wrap snake position horizontally on edge of screen
                if (snake.x < 0) snake.x = canvas.width - grid_size;
                else if (snake.x >= canvas.width) snake.x = 0;
                
                // Wrap snake position vertically on edge of screen
                if (snake.y < 0) snake.y = canvas.height - grid_size;
                else if (snake.y >= canvas.height) snake.y = 0;

                // Keep track of where snake has been. Front of the array is always the head
                snake.cells.unshift({ x: snake.x, y: snake.y });
                
                // Remove cells as we move away from them
                if (snake.cells.length > snake.maxCells) snake.cells.pop();

                pancake.graphics.mode = pancake.graphics.FILL;

                // Draw apple
                pancake.graphics.color("blue");
                pancake.graphics.square(apple.x, apple.y, grid_size);

                // Draw snake one cell at a time
                pancake.graphics.color("dodgerblue");
                snake.cells.forEach(function(cell, index) {
                    pancake.graphics.square(cell.x, cell.y, grid_size);  
                    
                    // Snake ate apple
                    if (pancake.physics.checkCollisionRect(cell.x, cell.y, 32, 32, apple.x, apple.y, 32, 32)) {
                        snake.maxCells++;
                        score = snake.maxCells - 1;
                        apple.x = pancake.util.random(Math.floor(pancake.canvas.compatible_width / 32)) * grid_size;
                        apple.y = pancake.util.random(Math.floor(pancake.canvas.compatible_height / 32)) * grid_size;    
                    }

                    // Check collision with all cells after this one (modified bubble sort)
                    for (var i = index + 1; i < snake.cells.length; i++) {

                        // Snake occupies same space as a body part. Reset game
                        if (cell.x === snake.cells[i].x && cell.y === snake.cells[i].y) {
                            snake.x = snake.y = 320;
                            snake.cells = [], snake.maxCells = 1;
                            snake.vx = grid_size, snake.vy = 0;

                            // Storage functionality to save highscore and reset score  
                            if (score > Number(pancake.storage.load("highscore"))) pancake.storage.save("highscore", Number(score));
                            score = 0;

                            apple.x = pancake.util.random(Math.floor(pancake.canvas.compatible_width / 32)) * grid_size;
                            apple.y = pancake.util.random(Math.floor(pancake.canvas.compatible_height / 32)) * grid_size;
                        
                        }
                    }
                });

                if (score == (pancake.graphics.context.canvas.width) * (pancake.graphics.context.canvas.height)) {
                    alert("Congrats! You won the game!!!");
                    pancake.game.restart();
                }

                // Draw score
                pancake.graphics.color("blue");
                pancake.graphics.setFont("Monospace", 64);
                pancake.graphics.text(score, 32, 64);
                
                // Get storage, Get canvas width
                // Draw highscore text
                pancake.graphics.text(Number(pancake.storage.load("highscore")), pancake.graphics.context.canvas.width - 156, 64);

                // Input
                if (pancake.input.keydown(pancake.input.key.UP) || pancake.input.keydown(pancake.input.key.W) || pancake.input.swipe("UP")) {
                    snake.vy = -grid_size, snake.vx = 0;
                }

                if (pancake.input.keydown(pancake.input.key.DOWN) || pancake.input.keydown(pancake.input.key.S) || pancake.input.swipe("DOWN")) {
                    snake.vy = grid_size, snake.vx = 0;
                }

                if (pancake.input.keydown(pancake.input.key.LEFT) || pancake.input.keydown(pancake.input.key.A) || pancake.input.swipe("LEFT")) {
                    snake.vx = -grid_size, snake.vy = 0;
                }

                if (pancake.input.keydown(pancake.input.key.RIGHT) || pancake.input.keydown(pancake.input.key.D) || pancake.input.swipe("RIGHT")) {
                    snake.vx = grid_size, snake.vy = 0;
                }

                // Check gamepad support and first gamepad connected
                if (pancake.browser.support.GAMEPAD() && pancake.input.gamepadConnected(0)) {
                    // Analog controls
                    if (pancake.input.gamepadAnalogMoved(0, pancake.input.GAMEPAD_MOVE_ANALOG, pancake.input.GAMEPAD_ANALOG_UP, "UP")) {
                        snake.vy = -grid_size, snake.vx = 0;
                    }

                    if (pancake.input.gamepadAnalogMoved(0, pancake.input.GAMEPAD_MOVE_ANALOG, pancake.input.GAMEPAD_ANALOG_DOWN, "DOWN")) {
                        snake.vy = grid_size, snake.vx = 0;
                    }

                    if (pancake.input.gamepadAnalogMoved(0, pancake.input.GAMEPAD_MOVE_ANALOG, pancake.input.GAMEPAD_ANALOG_LEFT, "LEFT")) {
                        snake.vx = -grid_size, snake.vy = 0;
                    }

                    if (pancake.input.gamepadAnalogMoved(0, pancake.input.GAMEPAD_MOVE_ANALOG, pancake.input.GAMEPAD_ANALOG_RIGHT, "RIGHT")) {
                        snake.vx = grid_size, snake.vy = 0;
                    }
                    
                    // DPAD Controls
                    if (pancake.input.gamepadButtonPressed(pancake.input.button.UP, 0)) {
                        snake.vy = -grid_size, snake.vx = 0;
                    }

                    if (pancake.input.gamepadButtonPressed(pancake.input.button.DOWN, 0)) {
                        snake.vy = grid_size, snake.vx = 0;
                    }

                    if (pancake.input.gamepadButtonPressed(pancake.input.button.LEFT, 0)) {
                        snake.vx = -grid_size, snake.vy = 0;
                    }

                    if (pancake.input.gamepadButtonPressed(pancake.input.button.RIGHT, 0)) {
                        snake.vx = grid_size, snake.vy = 0;
                    }
                }

                pancake.input.preventLoop();
            }
            
            window.animate(game, 120);
        </script>
    </body>
</html>
