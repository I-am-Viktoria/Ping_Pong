# Ping_Pong
import pygame
pygame.init()

font20 = pygame.font.Font('freesansbold.ttf', 20)

BLACK = (0, 0, 0)
WHITE = (225, 255, 225)
RED = (255, 176, 103)
BLUE = (1, 88, 255)

WIDTH, HEIGHT = 900, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Pong")

clock = pygame.time.Clock()	
FPS = 30


class Striker:
	def __init__(self, posx, posy, width, height, speed, color):
		self.posx = posx
		self.posy = posy
		self.width = width
		self.height = height
		self.speed = speed
		self.color = color
		self.geekRect = pygame.Rect(posx, posy, width, height)
		self.geek = pygame.draw.rect(screen, self.color, self.geekRect)

	def display(self):
		self.geek = pygame.draw.rect(screen, self.color, self.geekRect)

	def update(self, yFac):
		self.posy = self.posy + self.speed*yFac

		if self.posy <= 0:
			self.posy = 0
		elif self.posy + self.height >= HEIGHT:
			self.posy = HEIGHT-self.height

		self.geekRect = (self.posx, self.posy, self.width, self.height)

	def displayScore(self, text, score, x, y, color):
		text = font20.render(text+str(score), True, color)
		textRect = text.get_rect()
		textRect.center = (x, y)

		screen.blit(text, textRect)

	def getRect(self):
		return self.geekRect
