# Game Development Log

### Game Core

#### 22 Jul 2018

Game core has two main functions, start() and update().
Start will be executed once, and update will be executed... forever as the game runs.

How many times? Depends to FPS, frame per second. The game loop, which is the "update()" function, will be executed once at each frame. Thus, the typical computer with 60 fps will execute update() 60 times per second.
