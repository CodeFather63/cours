# TP Pixel (version tableaux) — corrigé
from turtle import *

# ----- les images : UN tableau par image -----
# Les nombres sont les longueurs des séries de pixels : blanc, noir, blanc, noir…
# Le nombre -1 marque la fin d'une ligne.   Ne pas modifier.
A = [1, 3, 1, -1,
     4, 1, -1,
     1, 4, -1,
     0, 1, 3, 1, -1,
     0, 1, 3, 1, -1,
     1, 4, -1]
TASSE = [4, 11, -1,
         4, 9, 2, 1, -1,
         4, 9, 2, 1, -1,
         4, 11, -1,
         4, 9, -1,
         4, 9, -1,
         5, 7, -1,
         0, 17, -1,
         1, 15, -1]
MYSTERE_2 = [6, 5, 2, 3, -1,
             4, 2, 5, 2, 3, 1, -1,
             3, 1, 9, 1, 2, 1, -1,
             3, 1, 9, 1, 1, 1, -1,
             2, 1, 11, 1, -1,
             2, 1, 10, 2, -1,
             2, 1, 9, 1, 1, 1, -1,
             2, 1, 8, 1, 2, 1, -1,
             2, 1, 7, 1, 3, 1, -1,
             1, 1, 1, 1, 4, 2, 3, 1, -1,
             0, 1, 2, 1, 2, 2, 5, 1, -1,
             0, 1, 3, 2, 5, 2, -1,
             1, 3, 2, 5, -1]
MYSTERE_3 = [6, 2, 2, 2, -1,
             5, 1, 2, 2, 2, 1, -1,
             6, 6, -1,
             4, 2, 6, 2, -1,
             3, 1, 10, 1, -1,
             2, 1, 12, 1, -1,
             2, 1, 3, 1, 4, 1, 3, 1, -1,
             1, 2, 12, 2, -1,
             0, 1, 16, 1, -1,
             0, 1, 6, 1, 2, 1, 6, 1, -1,
             0, 1, 7, 2, 7, 1, -1,
             1, 1, 14, 1, -1,
             2, 1, 12, 1, -1,
             2, 1, 5, 2, 5, 1, -1,
             3, 1, 10, 1, -1,
             4, 2, 6, 2, -1,
             6, 6, -1]

# Image en couleur : chaque longueur est suivie du numéro de sa couleur,
# et la fin d'une ligne s'écrit -1, -1.
# (tableau PALETTE plus bas : 0 blanc, 1 noir, 2 rouge, 3 vert, 4 bleu…)
TASSE_COULEUR = [4, 0, 11, 2, -1, -1,
                 4, 0, 9, 2, 2, 0, 1, 2, -1, -1,
                 4, 0, 9, 2, 2, 0, 1, 2, -1, -1,
                 4, 0, 11, 2, -1, -1,
                 4, 0, 9, 2, -1, -1,
                 4, 0, 9, 2, -1, -1,
                 5, 0, 7, 2, -1, -1,
                 0, 0, 17, 4, -1, -1,
                 1, 0, 15, 4, -1, -1]

# ----- constantes -----
NOIR = "██"        # un pixel noir en mode texte
BLANC = "  "       # un pixel blanc en mode texte (deux espaces)
TAILLE = 20        # taille d'un pixel à l'écran avec Turtle
PALETTE = ["white", "black", "red", "green", "blue", "yellow", "orange", "brown"]


# ----- Étape 1 : une ligne en mode texte -----
def ligne_texte(codes):
    texte = ""
    noir = False
    for n in codes:
        if noir:
            texte = texte + NOIR * n
        else:
            texte = texte + BLANC * n
        noir = not noir
    return texte


# ----- Étape 2 : une image en mode texte -----
def afficher(image):
    ligne = []
    for n in image:
        if n == -1:
            print(ligne_texte(ligne))
            ligne = []
        else:
            ligne.append(n)


# ----- Étape 4 : dessiner avec Turtle -----
def pixel(image):
    shape("square")
    shapesize(TAILLE / 20)
    penup()
    speed(0)
    tracer(0)
    x = -150
    y = 150
    noir = False
    for n in image:
        if n == -1:
            y = y - TAILLE
            x = -150
            noir = False
        else:
            for i in range(n):
                if noir:
                    goto(x, y)
                    stamp()
                x = x + TAILLE
            noir = not noir
    hideturtle()
    update()


# ----- Étape 5 : en couleur, avec un tableau de couleurs -----
def pixel_couleur(image):
    shape("square")
    shapesize(TAILLE / 20)
    penup()
    speed(0)
    tracer(0)
    x = -150
    y = 150
    for i in range(0, len(image), 2):
        n = image[i]
        if n == -1:
            y = y - TAILLE
            x = -150
        else:
            color(PALETTE[image[i + 1]])
            for k in range(n):
                goto(x, y)
                stamp()
                x = x + TAILLE
    hideturtle()
    update()


# ----- Défi ★★★★ : l'encodeur (l'inverse du décodeur) -----
def coder(pixels):
    """pixels : tableau de 0 (blanc) et de 1 (noir) ; retourne les codes de la ligne"""
    codes = []
    courant = 0
    longueur = 0
    for p in pixels:
        if p == courant:
            longueur = longueur + 1
        else:
            codes.append(longueur)
            courant = p
            longueur = 1
    codes.append(longueur)
    return codes


if __name__ == "__main__":
    afficher(TASSE)
    pixel(TASSE)
    exitonclick()
