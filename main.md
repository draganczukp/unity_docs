- [Matematyka](#matematyka)
  - [Koordynaty](#koordynaty)
    - [Kartezjańskie](#kartezja%c5%84skie)
    - [Biegunowe (2D)](#biegunowe-2d)
    - [Sferyczne (3D)](#sferyczne-3d)
  - [Operacje na punktach](#operacje-na-punktach)
    - [Skalowanie](#skalowanie)
    - [Obroty](#obroty)
      - [Wokół X](#wok%c3%b3%c5%82-x)
      - [Wokół Y](#wok%c3%b3%c5%82-y)
      - [Wokół Z](#wok%c3%b3%c5%82-z)
- [Atrybuty](#atrybuty)
  - [Na klasę](#na-klas%c4%99)
  - [Na pole](#na-pole)
  
# Matematyka
- skalar $\alpha$ - liczba
- punk $\bar{p}$ - pozycja
- wektor $\vec{v}$ - kierunek i długość

## Koordynaty
### Kartezjańskie
$$P(x, y, z)$$

### Biegunowe (2D)
$$P(r, \alpha)\\
P(x,y) = P(r * \cos\alpha, r * \sin\alpha)$$
### Sferyczne (3D)
$$P(r, \alpha, \beta)\\
P(x, y, z) = P(r*\cos\alpha*\cos\beta, r*\sin\alpha, r*\cos\alpha\sin\beta)$$

## Operacje na punktach
### Skalowanie
$$
p = (x,y,z,1)\ \text{Punkt 3d}\\
s = [sx, sy, sz]\ \text{wektor skali}\\
p' = (x * sx, y * sy, z*sz)\ \text{Punkt przeskalowany}\\
$$
Macierze:
$$
[x', y', z', 1] = [x, y, z, 1]
\begin{bmatrix}
sx & 0 & 0 & 0\\
0 & sy & 0 & 0\\
0 & 0 & sz & 0\\
0 & 0 & 0 & 1
\end{bmatrix}
$$

### Obroty
#### Wokół X
Obrót o kąt $\alpha$
$$
p' = (x,\\
 y* \cos\alpha - z * \sin\alpha,\\
 y*\sin\alpha - z\cos\alpha)
$$
Macierz: 
$$
[x', y', z', 1] = [x,y,z,1]
\begin{bmatrix}
    1 &0&0&0\\
    0&\cos\alpha&\sin\alpha&0\\
    0&-\sin\alpha&cos\alpha&0\\
    0&0&0&1
\end{bmatrix}
$$

#### Wokół Y
$$
p' = (z\sin\alpha + x\cos\alpha\\
y\\
z\cos\alpha - x\sin\alpha)
$$
Macierz
$$
[x', y', z', 1] = [x,y,z,1]
\begin{bmatrix}
    \cos\alpha&0&-\sin\alpha&0\\
    0&1&0&0\\
    \sin\alpha&0&\cos\alpha&0\\
    0&0&0&1
\end{bmatrix}
$$

#### Wokół Z
$$
p' = (x\cos\alpha - y\sin\alpha,\\
x\sin\alpha + y\cos\alpha,\\
z)
$$
Macierz
$$
[x', y', z', 1] = [x,y,z,1]
\begin{bmatrix}
    \cos\alpha&\sin\alpha &0&0\\
    -\sin\alpha & \cos\alpha &1 &0\\
    0&0&1&0\\
    0&0&0&1
\end{bmatrix}
$$

# Atrybuty
```c#
[Attribute(Params)]
public class Class {}
```
## Na klasę
- `AddComponentMenu("menu/name")`
## Na pole
- `Range(float from, float to)`
