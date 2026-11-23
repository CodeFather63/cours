# TP Listes — fichier de départ
from math import sqrt
from random import randint


def test(nom, obtenu, attendu):
    """Compare le résultat de ta fonction avec le résultat attendu."""
    if obtenu == attendu:
        print("✔", nom)
    else:
        print("✘", nom, "→ obtenu", obtenu, "au lieu de", attendu)


# ===== PARTIE 1 : échauffement =====
def somme(tab):
    pass


def maximum(tab):
    pass


def indice_max(tab):
    pass


def compter(tab, x):
    pass


def pairs(tab):
    pass


def a_lenvers(tab):
    pass


def sans_doublon(tab):
    pass


# ===== PARTIE 2 : exercices de concours =====
def recherche(tab, n):
    pass


def moyenne(tab):
    pass


def distance(point1, point2):
    """Calcule la distance entre deux points."""
    pass


def plus_courte_distance(tab, depart):
    """Renvoie le point du tableau tab se trouvant à la plus courte distance du point depart."""
    pass


# ===== PARTIE 3 : Mastermind =====
def generecodesansdoublon():
    pass


def propositionsansdoublon(proposition):
    pass


def convertir(texte):
    pass


def proposition_valide(proposition):
    pass


def resultat(proposition, code):
    pass


def jouer():
    pass


# ===== TESTS : enlève le # devant l'appel de l'exercice que tu veux vérifier =====
def tests_partie1():
    test("somme", somme([5, 3, 8]), 16)
    test("somme vide", somme([]), 0)
    test("maximum", maximum([3, 9, 2, 9]), 9)
    test("maximum négatifs", maximum([-5, -2, -8]), -2)
    test("indice_max", indice_max([3, 9, 2, 9]), 1)
    test("compter", compter([1, 2, 1, 3, 1], 1), 3)
    test("pairs", pairs([1, 2, 3, 4, 6, 7]), [2, 4, 6])
    test("a_lenvers", a_lenvers([1, 2, 3, 4]), [4, 3, 2, 1])
    test("sans_doublon", sans_doublon([1, 2, 1, 3, 2]), [1, 2, 3])


def tests_partie2():
    test("recherche 1", recherche([5, 3], 1), 2)
    test("recherche 2", recherche([2, 4], 2), 0)
    test("recherche 3", recherche([2, 3, 5, 2, 4], 2), 3)
    test("moyenne 1", moyenne([5, 3, 8]), 5.333333333333333)
    test("moyenne 2", moyenne([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]), 5.5)
    test("moyenne vide", moyenne([]), "erreur")
    test("distance", distance((1, 0), (5, 3)), 5.0)
    test("plus_courte", plus_courte_distance([(7, 9), (2, 5), (5, 2)], (0, 0)), (2, 5))


def tests_mastermind():
    c = generecodesansdoublon()
    test("code : 4 chiffres", len(c), 4)
    test("code : sans doublon", propositionsansdoublon(c), True)
    test("sansdoublon non", propositionsansdoublon([1, 2, 1, 4]), False)
    test("convertir", convertir("3415"), [3, 4, 1, 5])
    test("valide", proposition_valide([3, 4, 1, 5]), True)
    test("valide 7", proposition_valide([3, 4, 1, 7]), False)
    test("valide 3 chiffres", proposition_valide([3, 4, 1]), False)
    test("résultat BB", resultat([3, 4, 1, 5], [6, 3, 2, 1]), "BB")
    test("résultat NBB", resultat([6, 1, 3, 4], [6, 3, 2, 1]), "NBB")
    test("résultat NNNN", resultat([6, 3, 2, 1], [6, 3, 2, 1]), "NNNN")


# tests_partie1()
# tests_partie2()
# tests_mastermind()
# jouer()
