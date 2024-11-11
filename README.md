import pygame

# Inicializuojame pygame
pygame.init()

# Ekrano dydis
screen = pygame.display.set_mode((800, 600))

# Spalvos
WHITE = (255, 255, 255)
GREEN = (0, 255, 0)

# Kvadrato pozicija
x, y = 400, 300
speed = 5

# Pagrindinis žaidimo ciklas
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Kvadrato judėjimas
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        x -= speed
    if keys[pygame.K_RIGHT]:
        x += speed
    if keys[pygame.K_UP]:
        y -= speed
    if keys[pygame.K_DOWN]:
        y += speed

    # Užpildome ekraną balta spalva
    screen.fill(WHITE)

    # Nupiešiame kvadratą
    pygame.draw.rect(screen, GREEN, (x, y, 50, 50))

    # Atvaizduojame
    pygame.display.flip()

# Baigiame pygame
pygame.quit()
