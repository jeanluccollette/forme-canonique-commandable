# Réglage d'un retour d'état avec la forme canonique commandable

## Formulation du retour d'état

Le système initial est associé à l'équation d'évolution ci-dessous, avec une commande scalaire $u$.

$$\dfrac{dx}{dt} = Ax + Bu$$

Le retour d'état consiste à générer une commande $u$ de la forme $u = e-Kx$ où $e$ est une nouvelle entrée et $K$ un vecteur ligne, de sorte
que le système respecte une certaine dynamique.

Sous réserve que la matrice ci-dessous soit de rang $n$ qui est l'ordre du système, il est en effet 
possible de modifier tous les pôles du système qui sont pour le système intial les racines du polynôme caractéristique $|pI-A|$.

$$Q_G=[B \quad AB  \quad A^2B  \quad ...  \quad A^{n-1}B]$$

Avec le retour d'état, le polynôme caractéristique devient $|pI-(A-BK)|$.

## Changement de base

$$|pI-A| = p^n + \sum_{k=0}^{n-1}a_kp^k$$

$$Q_G=[B \quad AB  \quad A^2B  \quad \dots \quad A^{n-1}B]$$

$$V_G =
\pmatrix{
1&a_{n-1}&\dots&a_2&a_1\\
0&1&\dots&a_3&a_2\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&\dots&1&a_{n-1}\\
0&0&\dots&0&1
}$$

$$\overline{\overline A} = V_G^{-1}Q_G^{-1}AQ_G V_G$$

## Notebook avec un exemple

C'est [ici](forme_cano_comm.ipynb).
