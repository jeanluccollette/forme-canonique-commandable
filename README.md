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

Le polynôme caractérisque du système initial est la seule donnée dont on a besoin.

$$|pI-A| = p^n + \sum_{k=0}^{n-1}a_kp^k$$

Ses coefficients permettent la construction de la matrice $V_G$.

$$Q_G=[B \quad AB  \quad A^2B  \quad \dots \quad A^{n-1}B]$$

$$V_G =
\pmatrix{
1&a_{n-1}&\dots&a_2&a_1\\
0&1&\dots&a_3&a_2\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&\dots&1&a_{n-1}\\
0&0&\dots&0&1
}$$

Ces matrices $Q_G$ et $V_G$ permettent de réaliser le changement de base approprié.

$$\overline{\overline A} = V_G^{-1}Q_G^{-1}AQ_G V_G$$

$$\overline{\overline B} = V_G^{-1}Q_G^{-1}B$$

Dans cette nouvelle base, la matrice $\overline{\overline A}$ et le vecteur $\overline{\overline B}$
prennent une forme qui facilite l'expression du retour d'état. En effet, les coefficients du polynôme caractéristique
apparaissent explicitement dans la première ligne de la matrice $\overline{\overline A}$.

$$\overline{\overline A} =
\pmatrix{
-a_{n-1}&-a_{n-2}&\dots&-a_1&-a_0\\
1&0&\dots&0&0\\
0&1&\vdots&0&0\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&\dots&1&0
}$$

$$\overline{\overline B} =
\pmatrix{
1\\
0\\
0\\
\vdots\\
0
}$$

En effet

$$\overline{\overline A} - \overline{\overline B}\overline{\overline K}=
\pmatrix{
-a_{n-1}-\overline{\overline k}_{n-1}&-a_{n-2}-\overline{\overline k}_{n-2}&\dots&-a_1-\overline{\overline k}_{1}&-a_0-\overline{\overline k}_{0}\\
1&0&\dots&0&0\\
0&1&\vdots&0&0\\
\vdots&\vdots&\vdots&\vdots&\vdots\\
0&0&\dots&1&0
}$$

Le système avec retour d'état reste sous forme canonique, avec l'expression directe des coefficients
du nouveau polynôme caractéristique.

$$\left|pI-(\overline{\overline A}-\overline{\overline B}\overline{\overline K})\right| = p^n + \sum_{k=0}^{n-1}\alpha_kp^k$$

Ainsi, $\overline{\overline k}_{m} = \alpha_m - a_m$ pour $0 \leq m \leq n-1$

Le retour à la base initiale donne les coefficients $k_m$ recherchés.

$$K=\overline{\overline K}V_G^{-1}Q_G^{-1}$$

## Notebook avec un exemple

C'est [ici](forme_cano_comm.ipynb).
