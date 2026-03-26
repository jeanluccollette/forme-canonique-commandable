# Réglage d'un retour d'état avec la forme canonique commandable

## Formulation du retour d'état

Le système initial est associé à l'équation d'évolution ci-dessous, avec une commande scalaire $u$.

$$\dfrac{dx}{dt} = Ax + Bu$$

Le retour d'état consiste à générer une commande $u$ de la forme $u = e-Kx$ où $e$ est une nouvelle entrée et $K$ un vecteur ligne, de sorte
que le système respecte une certaine dynamique.

Sous réserve que la matrice ci-dessous soit de rang $n$ où n est l'ordre du système, il est en effet 
possible de modifier tous les pôles du système qui sont aussi les racines du polynôme caractéristique $|pI-A|$.

$$Q_G=[B \quad AB  \quad A^2B  \quad ...  \quad A^{n-1}B]$$
