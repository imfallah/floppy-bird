# ＦｌｏｐｐｙＢｉｒｄ⚡⭐



<p align="center">
<img src="https://github.com/jokernets/x/blob/main/flopy.jpg"><br><br>
</p>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>


## Translation 🎄🎀

### 🌏 Readme in [Farsi](README_fa.md)
  

ᴛᴀʙʟᴇ ᴏғ ᴄᴏɴᴛᴇɴᴛs ✅✔
=================

<!--ts-->
   * [Installation](#installation)
   * [ρуgαмє🐍❄](#pygame)
   * [Analiys Code](#analiys-code-)
      * [PART 1](#part-1)
      * [PART 2](#part-2)
      * [PART 3](#part-3)
      * [PART 4](#part-4-)   

*[Project Video🎃](#project-video-)
*[Project picture🎁](#project-video-)
   * [`CONNECT ME🌐👻`](#connect-me)
<!--te-->



# Installation

## Install the module with pip:

```python
pip install pygame
```

Update existing installation:`pip3 install (YOUR LIBRARY) --upgrade`
(update as often as possible because this library is under active development)


## ρуgαмє🐍❄
<p align="center">
<img src="https://github.com/jokernets/x/blob/main/pygame_lofi.png" width='400'>
</p>

### The Python PyGame library is used to create video games. This library contains several modules for playing sound, drawing graphics, managing mouse inputs, etc. It is also used to create client-side applications that can be wrapped in standalone executables.

### This PyGame Python tutorial helps to learn Pygame from beginner to advanced with the help of good and clear examples.

## 👀What is PYGame?❔❔

#### Pygame is a special tool that helps people make fun and exciting video games using Python. In PyGame, you can create your own computer game world using a set of tools. It includes computer graphics and audio libraries designed for use with the Python programming language.


# Analiys Code :

## `PART 1`:
1. **import libraries**:
    - `pygame': for making games and graphics programs.
    - `sys`: to access some functions and variables related to Python management.
    - `time`: to work with time.
    - `random': to generate random numbers.

2. **Initialization of `pygame'**:
    - `pygame.init()`: to initialize all modules required by `pygame`.
    - `clock = pygame.time.Clock()`: to control the frame rate in the game.

3. **`draw_floor' function**:
    - This function is used to draw the game floor.
    - `screen.blit`: to place the `floor_img` image at specified positions on the screen.

4. **function `create_pipes'**:
    - To create pipes in the game that the bird must pass through.
    - `pipe_y`: choose a random height from the `pipe_height` list.
    - `top_pipe` and `bottom_pipe`: define rectangles for top and bottom pipes using `pipe_img.get_rect` and specified positions.

This code is part of a game loop where `draw_floor` and `create_pipes` functions are used to draw the game environment and create obstacles. For the game to continue, you need to define more variables such as `screen`, `floor_img`, `pipe_img`, and `pipe_height`, and you also need to define the main game loop where you check for user input and make the necessary updates. .
```python
# Importing the libraries
import pygame
import sys
import time
import random
# Initializing the pygame
pygame.init()
# Frames per second
clock = pygame.time.Clock()

# Function to draw
def draw_floor():
    screen.blit(floor_img, (floor_x, 520))
    screen.blit(floor_img, (floor_x + 448, 520))

# Function to create pipes
def create_pipes():
    pipe_y = random.choice(pipe_height)
    top_pipe = pipe_img.get_rect(midbottom=(467, pipe_y - 300))
    bottom_pipe = pipe_img.get_rect(midtop=(467, pipe_y))
    return top_pipe, bottom_pipe
```
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## `PART 2`:
1. **pipe_animation function**:
      - Move pipes across the screen.
      - Checking the collision between the bird and the pipes.
      - If a collision occurs, it sets the "game_end" flag to "true".

2. **Draw_score** function:
      - Displays the current score on the screen when the game is in progress.
      - Displays the final score and high score on the screen after the end of the game.

3. **`score_update** function:
      - Increases the score when the bird successfully passes through the pipes.
      - Resets the "score_time" flag to get the next score.
      - Update the high score if the current score is more than that.

Please note that the actual functionality of the code may vary depending on the rest of the game code and how these functions are called and used in the game loop.

```python
# Function for animation
def pipe_animation():
    global game_over, score_time
    for pipe in pipes:
        if pipe.top < 0:
            flipped_pipe = pygame.transform.flip(pipe_img, False, True)
            screen.blit(flipped_pipe, pipe)
        else:
            screen.blit(pipe_img, pipe)

        pipe.centerx -= 3
        if pipe.right < 0:
            pipes.remove(pipe)

        if bird_rect.colliderect(pipe):
            game_over = True


# Function to draw score
def draw_score(game_state):
    if game_state == "game_on":
        score_text = score_font.render(str(score), True, (255, 255, 255))
        score_rect = score_text.get_rect(center=(width // 2, 66))
        screen.blit(score_text, score_rect)
    elif game_state == "game_over":
        score_text = score_font.render(f" Score: {score}", True, (255, 255, 255))
        score_rect = score_text.get_rect(center=(width // 2, 66))
        screen.blit(score_text, score_rect)

        high_score_text = score_font.render(f"High Score: {high_score}", True, (255, 255, 255))
        high_score_rect = high_score_text.get_rect(center=(width // 2, 506))
        screen.blit(high_score_text, high_score_rect)


# Function to update the score
def score_update():
    global score, score_time, high_score
    if pipes:
        for pipe in pipes:
            if 65 < pipe.centerx < 69 and score_time:
                score += 1
                score_time = False
            if pipe.left <= 0:
                score_time = True

    if score > high_score:
        high_score = score
```
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## `PART 3`:
1. **Setting the game window**:
     - The dimensions of the game window are set to **350 pixels wide** and **622 pixels high**.
     - A Pygame clock has been created to manage the game's frame rate.
     - The game board is initialized with the specified dimensions.
     - Window title set to "Flappy Bird".

2. **Background and base images**:
     - The background image (`back_img`) and the floor image (`floor_img`) are loaded.
     - The variable "floor_x" is initialized (although its purpose is not clear from this snippet).

3. **bird animation**:
     - Three different bird images ("bird_up", "bird_mid" and "bird_down") are loaded to create an animation effect.
     - A timer event ("bird_flap") is set to change the bird image every **200ms** to simulate flapping.
     - The initial bird image ("bird_img") is set to the middle stage ("bird_mid").
     - The bird rectangle ("bird_rect") is defined with an initial position in the center of the screen.

4. **Physics of birds**:
     - The `bird_movement` variable is initialized to **0**.
     - Gravity value **0.17** is set to simulate downward motion.
     - Bird position is updated based on gravity and user input.

5. **pipe mechanics**:
     - The pipe image (`pipe_img`) is loaded.
     - An array ('pipe_height') contains predefined heights for pipes.
     - A timer event ("create_pipe") is set to create new pipes every **1200ms**.
     - The "pipes" list is used to manage the position of the pipes.

6. **Game Over Mechanics**:
     - The "game_complete" flag is initialized to **false**.
     - The image is loaded over the game (`over_img`).
     - The game is over the rectangle ("over_rect") in the center of the screen.

7. **scoring system**:
     - The variables "score" and "high_score" are initialized to **0**.
     - A font (`score_font`) is loaded to display the score.
     - The "score_time" flag is initially set to **True**.

Please note that this code snippet is part of a larger Flappy Bird game, and the main game loop and event handling are not included here. Additionally, the image file paths must be valid for the game to work properly.

```python
# Game window
width, height = 350, 622
clock = pygame.time.Clock()
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Flappy Bird")

# setting background and base image
back_img = pygame.image.load("image/img_46.png")
floor_img = pygame.image.load("image/img_50.png")
floor_x = 0

# different stages of bird
bird_up = pygame.image.load("image/img_47.png")
bird_down = pygame.image.load("image/img_48.png")
bird_mid = pygame.image.load("image/img_49.png")
birds = [bird_up, bird_mid, bird_down]
bird_index = 0
bird_flap = pygame.USEREVENT
pygame.time.set_timer(bird_flap, 200)
bird_img = birds[bird_index]
bird_rect = bird_img.get_rect(center=(67, 622 // 2))
bird_movement = 0
gravity = 0.17
# Loading pipe image
pipe_img = pygame.image.load("image/greenpipe.png")
pipe_height = [400, 350, 533, 490]
# for the pipes to appear
pipes = []
create_pipe = pygame.USEREVENT + 1
pygame.time.set_timer(create_pipe, 1200)
# Displaying game over image
game_over = False
over_img = pygame.image.load("image/img_45.png").convert_alpha ()
over_rect = over_img.get_rect(center=(width // 2, height // 2))
# setting variables and font for score
score = 0
high_score = 0
score_time = True
score_font = pygame.font.Font("freesansbold.ttf", 27)
```

<img src="https://github.com/jokernets/x/blob/main/Flappy%20Bird%202024-04-22%2016_03_20.png" width="200" height="300">
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## `PART 4 `:
- The game runs at **120 frames per second** (FPS).
- Controls user inputs, such as quitting the game or pressing the space bar to flap the bird.
- By pressing the spacebar:
     - Resets the upward movement of the bird if the game is not over.
     - If the game is over, it resets the game to the original state.
- Bird image is updated to simulate flapping.
- Pipes are spawned at regular intervals to challenge the player.
- The floor image moves to create a scrolling effect.
- The bird's position is updated with gravity and rotates based on its movement.
- The game checks for hitting the top or bottom of the screen to end the game.
- The score is updated and displayed on the screen.
- If the game is over, the game image will be displayed over and the final score will be shown.
- The floor position is reset if it moves off-screen to maintain the scrolling effect.
- The display will update with all changes to show the current state of the game.

This loop continues until the user exits the game, at which point Pygame and the system exit. The actual implementation of functions like ``create_pipes'', ``pipe_animation'', ``score_update'', ``draw_score'' and ``draw_floor'' are not provided in the snippet, but they are necessary for the game to function fully.
```python
# Game loop
running = True
while running:
    clock.tick(120)
    # for checking the events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:  # QUIT event
            running = False
            sys.exit()

        if event.type == pygame.KEYDOWN:  # Key pressed event
            if event.key == pygame.K_SPACE and not game_over:  # If space key is pressed
                bird_movement = 0
                bird_movement = -7

            if event.key == pygame.K_SPACE and game_over:
                game_over = False
                pipes = []
                bird_movement = 0
                bird_rect = bird_img.get_rect(center=(67, 622 // 2))
                score_time = True
                score = 0

        # To load different stages
        if event.type == bird_flap:
            bird_index += 1

            if bird_index > 2:
                bird_index = 0

            bird_img = birds[bird_index]
            bird_rect = bird_up.get_rect(center=bird_rect.center)

        # To add pipes in the list
        if event.type == create_pipe:
            pipes.extend(create_pipes())

    screen.blit(floor_img, (floor_x, 550))
    screen.blit(back_img, (0, 0))

    # Game over conditions
    if not game_over:
        bird_movement += gravity
        bird_rect.centery += bird_movement
        rotated_bird = pygame.transform.rotozoom(bird_img, bird_movement * -6, 1)

        if bird_rect.top < 5 or bird_rect.bottom >= 550:
            game_over = True

        screen.blit(rotated_bird, bird_rect)
        pipe_animation()
        score_update()
        draw_score("game_on")
    elif game_over:
        screen.blit(over_img, over_rect)
        draw_score("game_over")

    # To move the base
    floor_x -= 1
    if floor_x < -448:
        floor_x = 0

    draw_floor()

    # Update the game window
    pygame.display.update()

# quiting the pygame and sys
pygame.quit()
sys.exit()
```
## Project Video 🧨🎁
<img src="https://github.com/jokernets/x/blob/main/Flappy%20Bird%202024-04-22%2013_29_50.png" width="200" height="300"> <img src="https://github.com/jokernets/x/blob/main/floppy.gif" width="300" height="300">

# `𝐂𝐎𝐍𝐍𝐄𝐂𝐓 𝐌𝐄`🎈

<a herf="https://www.buymeacoffee.com/jokernets"><img src="https://cdn.buymeacoffee.com/buttons/v2/arial-yellow.png" alt="Buy Me A Coffee" width="180px">
<a href="mailto:joker.until33@gmail.com"><img align="center" width="60px" src="https://github.com/edent/SuperTinyIcons/raw/master/images/svg/gmail.svg" style="max-width: 100%;"></a><a href="https://www.linkedin.com/in/mohammadfallahnejad/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/mohammadfallahnejad/" height="40" width="60" /></a>






