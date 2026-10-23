from math import comb

# Paramètres de la loi binomiale
n = 10       # nombre d'ampoules
p = 0.05     # probabilité qu'une ampoule soit défectueuse


def probabilite_exacte(k: int) -> float:
    """Calcule P(X = k) pour X suivant une loi binomiale B(n, p)."""
    if k < 0 or k > n:
        return 0.0

    return comb(n, k) * (p ** k) * ((1 - p) ** (n - k))


# 1. X suit une loi binomiale B(10, 0.05)

# 2. Probabilité d'avoir exactement 2 ampoules défectueuses
p_exactement_2 = probabilite_exacte(2)

# 3. Probabilité de n'avoir aucune ampoule défectueuse
p_aucune = probabilite_exacte(0)

# 4. Probabilité d'avoir au moins une ampoule défectueuse
p_au_moins_une = 1 - p_aucune

print("X suit une loi binomiale B(10, 0.05).")
print(f"P(X = 2) = {p_exactement_2:.4%}")
print(f"P(X = 0) = {p_aucune:.4%}")
print(f"P(X >= 1) = {p_au_moins_une:.4%}")
