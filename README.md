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
