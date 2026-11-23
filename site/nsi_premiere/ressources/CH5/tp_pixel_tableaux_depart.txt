# TP Pixel (version tableaux) — fichier de départ
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
    pass


# ----- Étape 2 : une image en mode texte -----
def afficher(image):
    pass


# ----- Étape 4 : dessiner avec Turtle -----
def pixel(image):
    pass


# ----- Étape 5 : en couleur -----
def pixel_couleur(image):
    pass


# ----- Tests : enlève le # devant la ligne que tu veux essayer -----
# print(ligne_texte([1, 3, 1]))
# afficher(A)
afficher(TASSE)
# pixel(TASSE)
# pixel_couleur(TASSE_COULEUR)
# exitonclick()
