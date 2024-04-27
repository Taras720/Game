from pygame import *
win_width = 700
win_height = 500
window = display.set_mode((700,500))
display.set_caption("Touch Coin")
background = transform.scale(image.load("fon.png"), (700, 500))
figgers = 0


class GameSprite(sprite.Sprite):
    def __init__(self, player_image, player_x, player_y, size_x, size_y):
        sprite.Sprite.__init__(self)
        self.image = transform.scale(image.load(player_image), (size_x, size_y))
        
 
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
    def collidepoint(self, x,y):
        return self.rect.collidepoint(x,y)
    def draw(self):
        window.blit(self.image, (self.rect.x, self.rect.y))

class Coin(GameSprite):
    def __init__(self, player_image, player_x, player_y, size_x, size_y):
        sprite.Sprite.__init__(self)
        self.image = transform.scale(image.load(player_image), (size_x, size_y))
        
 
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
        
    


class Figure():
    def __init__(self, player_image, player_x, player_y, size_x, size_y, speed):
        self.image = transform.scale(image.load(player_image), (size_x, size_y))
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
        self.speed = speed

    

    def draw(self):
        window.blit(self.image, (self.rect.x, self.rect.y))
def draw_text(surface, text, size, x, y, color):
    fonts = font.SysFont('verdana', size)
    text_surface = fonts.render(text, True, color)
    text_rect = text_surface.get_rect()
    text_rect.topleft = (x, y)
    surface.blit(text_surface, text_rect)
run = True
Coins = GameSprite("coin.png",200,100,300,300)

while run:


    window.blit(background, (0, 0))
    Coins.draw()

    for e in event.get():
        if e.type == QUIT:
            run = False
        if e.type == MOUSEBUTTONDOWN:
            x,y = e.pos
            figgers +=1
            print(figgers)
            if Coins.collidepoint(x,y) :
                figure = Figure("figure.png",x,y,50,100,0)
                figure.draw()

            draw_text(window, f"Кількість натисків: {figgers}", 30, 10, 10, (255, 255, 255))
    



    display.update()
    time.delay(17)





