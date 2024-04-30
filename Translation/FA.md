# فلاپی برد ⚡⭐

<p align="center">
<img src="https://github.com/jokernets/floppy-bird/blob/main/public/flopy.jpg"><br><br>
</p>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## ترجمه ✨🎈

### 🌏 مقاله به زبان [English](https://github.com/jokernets/floppy-bird/blob/main/README.md)
  

جدول فهرست مطالب ✅✔
=================

<!--ts-->
* [نصب کن!](#%D9%86%D8%B5%D8%A8-%DA%A9%D9%86)
* [پای گیم🐍❄](#%D9%BE%D8%A7%DB%8C-%DA%AF%DB%8C%D9%85)
* [آنالیز کد🛡](
#%D8%A2%D9%86%D8%A7%D9%84%DB%8C%D8%B2-%DA%A9%D8%AF-)
 * 🔹[پارت1✅](#%D9%BE%D8%A7%D8%B1%D8%AA-1)
 * 🔹[پارت2✅](#%D9%BE%D8%A7%D8%B1%D8%AA-2)
 * 🔹[پارت3✅](
#%D9%BE%D8%A7%D8%B1%D8%AA-3)
 * 🔹[پارت4✅](#%D9%BE%D8%A7%D8%B1%D8%AA-4)
* [ویدیو از نحوه کار پروژه🏆](#%D9%88%DB%8C%D8%AF%DB%8C%D9%88-%D8%A7%D8%B2-%D9%BE%D8%B1%D9%88%DA%98%D9%87-)

  

  
* [ارتباط با من 🌐🎃](#%D8%A7%D8%B1%D8%AA%D8%A8%D8%A7%D8%B7-%D8%A8%D8%A7-%D9%85%D9%86)
<!--te-->



# نصب کن!
### ماژول را با پیپ نصب کنید:
```python
pip install pygame
pip install time
pip install os-sys
pip install random2
```

#### نصب موجود را به روز کنید: pip3 install (کتابخانه شما) -- ارتقاء دهید (تا حد امکان به روز رسانی کنید زیرا این کتابخانه در حال توسعه فعال است)


## پای گیم🐍❄
<p align="center">
<img src="https://github.com/jokernets/floppy-bird/blob/main/public/pygame_logo.png" width='400'>
</p>
### کتابخانه Python PyGame برای ایجاد بازی های ویدئویی استفاده می شود. این کتابخانه شامل چندین ماژول برای پخش صدا، ترسیم گرافیک، مدیریت ورودی‌های ماوس و غیره است. همچنین برای ایجاد برنامه‌های سمت کلاینت که می‌توانند در فایل‌های اجرایی مستقل پیچیده شوند، استفاده می‌شود.

### این آموزش PyGame Python با کمک مثال های خوب و واضح به یادگیری Pygame از مبتدی تا پیشرفته کمک می کند.

## 👀پای گیم چیست؟❔❔

#### Pygame یک ابزار ویژه است که به مردم کمک می کند تا بازی های ویدیویی سرگرم کننده و هیجان انگیز را با استفاده از پایتون انجام دهند. در PyGame، می توانید با استفاده از مجموعه ای از ابزارها، دنیای بازی های رایانه ای خود را بسازید. این شامل گرافیک های کامپیوتری و کتابخانه های صوتی است که برای استفاده با زبان برنامه نویسی پایتون طراحی شده اند.

# آنالیز کد🎈 :

## `پارت 1`:
1. **وارد کردن کتابخانه ها**:
- 'pygame': برای ساخت بازی و برنامه های گرافیکی.
- `sys`: برای دسترسی به برخی از توابع و متغیرهای مرتبط با مدیریت پایتون.
- «زمان»: کار کردن با زمان.
- "تصادفی": برای تولید اعداد تصادفی.

2. **راه اندازی اولیه «pygame»**:
- `pygame.init()`: برای مقداردهی اولیه همه ماژول های مورد نیاز "pygame".
- `clock = pygame.time.Clock()`: برای کنترل نرخ فریم در بازی.

3. **عملکرد Draw_floor**:
- از این تابع برای ترسیم کف بازی استفاده می شود.
- `screen.blit`: برای قرار دادن تصویر "floor_img" در موقعیت های مشخص شده روی صفحه.

4. **عملکرد «create_pipes»**:
- برای ایجاد لوله هایی در بازی که پرنده باید از آنها عبور کند.
- "pipe_y": یک ارتفاع تصادفی از لیست "pipe_height" انتخاب کنید.
- "top_pipe" و "bottom_pipe": با استفاده از "pipe_img.get_rect" و موقعیت های مشخص، مستطیل هایی را برای لوله های بالا و پایین تعریف کنید.

این کد بخشی از یک حلقه بازی است که در آن از توابع "draw_floor" و "create_pipes" برای ترسیم محیط بازی و ایجاد موانع استفاده می شود. برای ادامه بازی، باید متغیرهای بیشتری مانند «screen»، «floor_img»، «pipe_img» و «pipe_height» تعریف کنید و همچنین باید حلقه اصلی بازی را که در آن ورودی کاربر را بررسی می‌کنید، تعریف کنید. به روز رسانی های لازم
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
<img src="https://github.com/jokernets/floppy-bird/blob/main/public/part%200.png">
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## `پارت 2`:
1. **عملکرد pipe_animation**:
- لوله ها را در سراسر صفحه حرکت دهید.
- بررسی برخورد پرنده و لوله ها.
       
2. تابع **Draw_score**:
- زمانی که بازی در حال انجام است امتیاز فعلی را روی صفحه نمایش می دهد.
- امتیاز نهایی و امتیاز بالا را پس از پایان بازی روی صفحه نمایش می دهد.

3. عملکرد **`score_update**:
- وقتی پرنده با موفقیت از لوله ها عبور می کند امتیاز را افزایش می دهد.
- پرچم "score_time" را برای گرفتن امتیاز بعدی بازنشانی می کند.
- اگر امتیاز فعلی بیشتر از آن است، امتیاز بالا را به روز کنید.

لطفاً توجه داشته باشید که عملکرد واقعی کد ممکن است بسته به بقیه کدهای بازی و نحوه فراخوانی و استفاده از این توابع در حلقه بازی متفاوت باشد.

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

## `پارت 3`:
1. **تنظیم پنجره بازی**:
- ابعاد پنجره بازی روی **350 پیکسل عرض** و **622 پیکسل ارتفاع** تنظیم شده است.
- یک ساعت Pygame برای مدیریت نرخ فریم بازی ایجاد شده است.
- صفحه بازی با ابعاد مشخص شده مقداردهی اولیه می شود.
- عنوان پنجره روی "Flappy Bird" تنظیم شده است.

2. **تصاویر پس زمینه و پایه**:
- تصویر پس زمینه (`back_img`) و تصویر طبقه (`floor_img`) بارگذاری می شوند.
- متغیر "floor_x" مقدار دهی اولیه شده است (البته هدف آن از این قطعه مشخص نیست).

3. **انیمیشن پرنده**:
- سه تصویر مختلف پرنده ("bird_up"، "bird_mid" و "bird_down") برای ایجاد یک افکت انیمیشن بارگذاری می شوند.
- یک رویداد تایمر ("bird_flap") تنظیم شده است تا تصویر پرنده را هر **200ms** تغییر دهد تا بال زدن را شبیه سازی کند.
- تصویر اولیه پرنده ("bird_img") روی مرحله میانی ("bird_mid") تنظیم شده است.
- مستطیل پرنده ("bird_rect") با موقعیت اولیه در مرکز صفحه تعریف می شود.

4. **فیزیک پرندگان**:
- متغیر `bird_movement` به **0** مقداردهی اولیه می شود.
- مقدار جاذبه **0.17** برای شبیه سازی حرکت رو به پایین تنظیم شده است.
- موقعیت پرنده بر اساس جاذبه و ورودی کاربر به روز می شود.

5. **مکانیک لوله**:
- تصویر لوله (`pipe_img`) بارگذاری شده است.
- یک آرایه ('pipe_height') حاوی ارتفاعات از پیش تعریف شده برای لوله ها است.
- یک رویداد تایمر ("create_pipe") برای ایجاد لوله های جدید در هر **1200ms** تنظیم شده است.
- لیست "لوله ها" برای مدیریت موقعیت لوله ها استفاده می شود.

6. **Game Over Mechanics**:
- پرچم "game_complete" به **false** مقداردهی اولیه می شود.
- تصویر روی بازی بارگذاری می شود (`over_img`).
- بازی روی مستطیل ("over_rect") در مرکز صفحه است.

7. **سیستم امتیازدهی**:
- متغیرهای "score" و "high_score" به **0** مقداردهی اولیه می شوند.
- یک فونت (`score_font`) برای نمایش امتیاز بارگذاری می شود.
- پرچم "score_time" در ابتدا روی **True** تنظیم شده است.

لطفاً توجه داشته باشید که این قطعه کد بخشی از یک بازی بزرگتر Flappy Bird است و حلقه اصلی بازی و مدیریت رویداد در اینجا گنجانده نشده است. علاوه بر این، مسیرهای فایل تصویری باید معتبر باشند تا بازی به درستی کار کند.

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

<img src="https://github.com/jokernets/floppy-bird/blob/main/public/Flappy%20Bird%202024-04-22%2016_03_20.png" width="200" height="300">
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>

## `پارت 4 `:
- بازی با **120 فریم در ثانیه ** (FPS) اجرا می شود.
- ورودی های کاربر را کنترل می کند، مانند ترک بازی یا فشار دادن کلید فاصله برای تکان دادن پرنده.
- با فشار دادن کلید فاصله:
    - اگر بازی تمام نشده باشد، حرکت پرنده به سمت بالا را بازنشانی می کند.
    - اگر بازی تمام شد، بازی را به حالت اولیه بازنشانی می کند.
- تصویر پرنده برای شبیه سازی بال زدن به روز می شود.
- لوله ها در فواصل منظم برای به چالش کشیدن بازیکن تولید می شوند.
- تصویر طبقه برای ایجاد یک افکت پیمایش حرکت می کند.
- موقعیت پرنده با جاذبه به روز می شود و بر اساس حرکت خود می چرخد.
- بازی بررسی می کند که برای پایان دادن به بازی به بالا یا پایین صفحه ضربه بزنید.
- امتیاز به روز شده و روی صفحه نمایش داده می شود.
- اگر بازی تمام شده باشد، تصویر بازی به نمایش در می آید و امتیاز نهایی نمایش داده می شود.
- اگر برای حفظ جلوه اسکرول از صفحه خارج شود، موقعیت کف بازنشانی می شود.
- نمایشگر با تمام تغییرات به روز می شود تا وضعیت فعلی بازی را نشان دهد.

این حلقه تا زمانی که کاربر از بازی خارج شود ادامه می یابد و در این مرحله Pygame و سیستم خارج می شوند. اجرای واقعی توابعی مانند "create_pipes"، "pipe_animation"، "score_update"، "draw_score" و "draw_floor" در قطعه ارائه نشده است، اما برای بازی ضروری است. به طور کامل عمل کند
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
## ویدیو از پروژه 🏆

<img src="https://github.com/jokernets/floppy-bird/assets/165279911/304fa37f-6bbc-4cc7-944e-2951cf1b1229" width="200" height="300"> <img src="https://github.com/jokernets/floppy-bird/blob/main/public/floppy.gif" width="300" height="300">



# `ارتباط با من🥇`

<a herf="https://www.buymeacoffee.com/jokernets"><img src="https://cdn.buymeacoffee.com/buttons/v2/arial-yellow.png" alt="Buy Me A Coffee" width="180px">
<a href="mailto:joker.until33@gmail.com"><img align="center" width="60px" src="https://github.com/edent/SuperTinyIcons/raw/master/images/svg/gmail.svg" style="max-width: 100%;"></a><a href="https://www.linkedin.com/in/mohammadfallahnejad/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/mohammadfallahnejad/" height="40" width="60" /></a>





