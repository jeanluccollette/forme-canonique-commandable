# Réglage d'un retour d'état avec la forme canonique commandable

## Formulation du retour d'état

Le système initial est associé à l'équation d'évolution ci-dessous, avec une commande scalaire $u$.

$$\dfrac{dx}{dt} = Ax + Bu$$

Le retour d'état consiste à générer une commande $u$ de la forme $u = e-Kx$ où $e$ est une nouvelle entrée et $K$ un vecteur ligne, de sorte
que le système respecte une certaine dynamique.
