#Go to the video and find the things that you need to add!!
#if you don't see the code in normal then To see the code in normal then go click the button raw or blame


import pgzrun
import random

#Window
WIDTH,HEIGHT=800,600
x,y=HEIGHT//2,WIDTH//2

#Title
TITLE='Eat The Circles'

#Variables
circles=0
health=100

#player
snake=Actor('snake.png')
#pos of player
snake.x=400
snake.y=300

#apple
apple=Actor('apple.png')

#yellow enemy apple
apple2=Actor('apple2.png')
#enemy apple pos
apple2.x=random.randint(40,WIDTH-40)
apple2.y=random.randint(40,HEIGHT-40)
#2 enemy apple
apple3=Actor('apple2_1.png')
#enemy apple2 pos
apple3.x=random.randint(40,WIDTH-40)
apple3.y=random.randint(40,HEIGHT-40)

#pos of apple
apple.x=random.randint(40,WIDTH-40)
apple.y=random.randint(40,HEIGHT-40)

#Text
def drawApples():
    screen.draw.text(str(circles),(100,30))
    screen.draw.text('Circles:',(30,30),width=180,lineheight=1.5)
def drawGame():
    screen.draw.text('GAME OVER',(350,300),width=180,lineheight=1.5)
def drawHealth():
    screen.draw.text(str(health),(750,30))
    screen.draw.text('Health:',(685,30),width=180,lineheight=1.5)
#draw
def draw():
    snake.draw()
    apple.draw()
    drawApples()

def update():
    screen.clear()
    #global variables
    global health
    global 
    #movement
    if keyboard.left:
        snake.x-=8
    elif keyboard.right:
        snake.x+=8
    elif keyboard.up:
        snake.y-=8
    elif keyboard.down:
        snake.y+=8
    if snake.colliderect(apple):
        circles+=1
        apple.x=random.randint(40,WIDTH-40)
        apple.y=random.randint(40,HEIGHT-40)
    if snake.x>800 or snake.x<0 or snake.y>600 or snake.y<0:
        drawGame()
        snake.x=10000000000000000000000000000000
        snake.y=1000000000000000000000000000000000
        health=0
    if circles>=1==True:
        apple2.draw()
    if snake.colliderect(apple2):
        circles+=1
        apple2.x=random.randint(40,WIDTH-40)
        apple.y=random.randint(40,HEIGHT-40)
        health-=25
    if circles>=5==True:
        apple3.draw()
    if apple3.colliderect(snake):
        circles+=1
        apple3.x=random.randint(40,WIDTH-40)
        apple.y=random.randint(40,HEIGHT-40)
        health-=25
    if health<=0:
        health=0
        snake.x=1000000000000000000000000000000000000000000000000000000000000
        snake.y=1000000000000000000000000000000000000000000000000000000000000
        apple.x=10000000000000000000000000000000000000000000000000000000000000000
        apple.y=10000000000000000000000000000000000000000000000000000000000000000
        apple2.x=10000000000000000000000000000000000000000000000000000000000000000
        apple2.y=10000000000000000000000000000000000000000000000000000000000000000
        apple3.x=10000000000000000000000000000000000000000000000000000000000000000
        apple3.y=10000000000000000000000000000000000000000000000000000000000000000
pgzrun.go()
