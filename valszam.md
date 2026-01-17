# Valószínűségszámítás

Órai videók:
- [Negyedik előadás](https://youtu.be/o2uHHnHpi0c?si=Ulw4zSMNANNtUYGK)
- [Ötödik előadás](https://youtu.be/RT-_aTsoUiU?si=1voF8UZPWMwMgmcM)
- [Hatodik előadás](https://youtu.be/rxe9meZ_U_4?si=-lw57oZYsXkVmY-p)
- [Hetedik előadás](https://youtu.be/UxXO897rMFY?si=CTL90wsZ-2FZUjEZ)
- [Nyolcadik előadás](https://youtu.be/va36j0_Pvsc?si=2UVW7EzGmNYT4n85)

## I. Valószínűségi mezők, változók, alapvető objektumok. Eloszlások, sűrűségfüggvények, transzformációk spec esetei, Doob Lemma

### Valószínűségi mező

$(\Omega, \mathcal{A}, P)$ mértéktér, ahol
- $\Omega$ az (elemi) eseménytér, ez egy mérhető $\sigma$-algebra
- $\mathcal{A}$ a megfigyelhető események halmazrendszere 
- $P$ valószínűségi mérték, $P \in [0,1]$ és $P(\Omega) = 1$

### Valószínűségi változó

$x: \Omega \mapsto \R$ valamilyen eseménytérből $(\mathcal{X}, B)$ mérhető térbe képező mérhető függvény.

### Val. változó eloszlása

Egy mérték $Q_x(B) = P(X^{-1}(B))$ mértéktartó transzformáció x-szerinti ősképének valószínűsége, $B \in \mathcal{B}$.
- Mértéktartó az eloszlás, így $(\mathcal{X}, \mathcal{B}, Q_x)$ mértéktér lesz, sőt valószínűségi tér.
- $Q_x(X) = P(X^{-1}(\mathcal{X})) = P(\Omega) \mapsto$ a mértéktér inverze a valószínűségi tér 

#### Mértékterek szorzata és annak mérhetősége

Több változót összeszorozva is val. változót kapunk. Eloszlása mértékteret alkot, hiszen mértéktereket tudunk szorozni.

$(\Omega_i, \mathcal{A}_i, P_i)$ ahol $i \in I$-re $X_i: \Omega_i \mapsto (\mathcal{X}_i, B_i) \quad (\Omega, \mathcal{A}, P) = \prod_{i = I} (\Omega_i, \mathcal{A}_i, P_i)$

$(\mathcal{X}, B) = \prod_{i \in I} (\mathcal{X}_i, B_i) \mapsto$ csak a téglatér $X=(x_1 \times x_2 \times ...) \quad \Omega \mapsto X$

$X$ mérhető $\iff \forall i$-re $X_i$ mérhető. 

#### Margináns

$X: \Omega \mapsto \mathcal{X}$ val. változóból váltva, $X_i$ val. változó lesz $X$ marginálisa.

- Szorzattérbe képez ~ peremeloszlás

- Több változónál $x_i = \pi_i \cdot x$ függvény $x$ marginálisa, $Q_{x_i}$ marginális eloszlása. 

### Eloszlásfüggvények

$F_x$ meghatározza $Q_x$-et.

Valós eset: $x \in \R^n$

- $n=1$ esetén:
    - $Q_x$ meghatározásához elég $Q_x((-\infty, t)) = P(X \lt t) \coloneqq F_x(t) \mapsto$ eloszlásfüggvény a $t$ helyen
- $n \gt 1$ esetén:
    - $Q_x((-\infty, t_1) \times (-\infty, t_2) \times ... \times (-\infty, t_n)) = P(x_1 < t_1, ... , x_n < t_n) \coloneqq F_x(t_1, ..., t_n)$

**Tulajdonságok:**

Minden ilyen tulajdonságú függvény eloszlásfüggvény:

- $n=1$ esetén:
    - Monoton növő $\mapsto$ nagyobb halmaznak nagyobb vagy egyenlő a mértéke
    - $\lim\limits_{x \mapsto -\infty} F_x(x) = 0, \; \lim\limits_{x \mapsto \infty} F_x(x) = 1$
    - Balról folytonos

- $n \gt 1$ esetén:
    - Monoton növő mindegyik koordinátában (változóban)
    - $\lim\limits_{min(x_i) \mapsto -\infty} F_x(\underline x) = 0, \; \lim\limits_{min(x_i) \mapsto \infty} F_x(\underline x) = 1$
    - Balról folytonos mindegyik változójában
    - $\forall \underline a \lt \underline b \isin \R^n$-re (azaz minden koordinátában veszünk egyet, ami nagyobb, mint a másik):
        - $\sum_{\epsilon \isin \{ 0,1\}^n } (-1)^{1-\sum \epsilon_i} \cdot F_x(\epsilon \underline b + (1-\epsilon) \underline a) \ge 0$ = szita formula

### Sűrűségfüggvények

$x$ változó $x: \Omega \mapsto X$ $\mu$-re $x$ által indukált Q_x mérték absz. folytonos $x \ll \mu$, ($\mu \; \sigma$-véges és $(X,\mathcal{B}, \mu)$ mértéktér) ha $Q_x \ll \mu$, ekkor a sűrűségfüggvény a Radon-Nikodym derivált:

$f_x = \frac{dQ_x}{d\mu}$

Spec. visszatérő eset az euklideszi tér és Lebesque-mérték

**Tulajdonságok:**

- $f_x \ge 0$ m.m.
- $\int_x f_x d\mu = 1$
- Spec. átskálázó fv.
- Már olyan eloszlások is kezelhetőek, amik se nem folytonos, se nem diszkrétek

### Változók transzformációi

Összetett függvény külső függvényének sűrűségfüggvénye:

$(\Omega, \mathcal{A}, P) \xrightarrow{x} (\mathcal{X}, \mathcal{B}, \mu) \xrightarrow{h} (Y, \zeta)$, ekkor $h(x)$ val. változó $(Y, \zeta)$-ben.

T.f.h. $x$ absz. folytonos, $f_x$ sűrűségfüggvénnyel, ekkor $Q_{h(x)} = Q_x \circ h^{-1}$ és $Q_{h(x)} \ll \mu \circ h^{-1}$

### Doob Lemma

Azt szeretnénk, hogy $Q_x \circ h^{-1}(C) = \int_C g \; d(\mu \circ h^{-1}) = \int_{h^{-1}(C)} g \circ h \; d\mu$, viszont kellene $f_x$.

$\frac{dQ_x \circ h^{-1}}{d\mu \circ h^{-1}} \xlongequal{kb.} f_x \circ h^{-1}$, viszont nem biztos, hogy $h^{-1}$ egyértelmű, erre kell a Doob-lemma:

Legyne $h: \mathcal{X} \mapsto Y, \; g: \mathcal{X} \mapsto \R^n$ mérhető és $g$ mérhető a $h$ által generált $\sigma$-algebrára. Ekkor létezik: $l: Y \mapsto \R^n$ mérhető függvény úgy, hogy $g = l \circ h$.

- Ez az $l$ függvény összeköti a $g$-t és $h$-t, úgy megy tovább $Y$-ból $\R^{n}$-be, hogy megkapjuk $g$-t
- Felhasználása: $f_x^h = \frac{dQ_x \mid_{\sigma(h)}}{d\mu \mid_{\sigma(h)}} \mapsto$ vagyis megszorítjuk a mértéket az adott $\sigma$-algebrára.


### Sűrűségfüggvény spec. esetei

Legyen $X$ folytonos valószínűségi változó sűrűségfüggvénye $f_X(x)$:

- Eltolásparaméteres család
    - $Y = X + c, \quad c \in \R$
    - $f_Y(y) = f_X(y - c)$
    - Az eloszlás alakja nem változik
    - $\mathbb{E}[Y] = \mathbb{E}[X] + c$
    - $\mathrm{Var}(Y) = \mathrm{Var}(X)$
- Skálaparaméteres család
    - $Y = aX, \quad a \neq 0$
    - $f_Y(y) = \frac{1}{|a|} \, f_X\!\left(\frac{y}{a}\right)$
    - Az eloszlás alakja megmarad
    - $\mathbb{E}[Y] = a\,\mathbb{E}[X]$
    - $\mathrm{Var}(Y) = a^2\,\mathrm{Var}(X)$
- Lineáris transzformált
    - $Y = aX + b, \quad a \neq 0$
    - $X = \frac{Y - b}{a}$

    | Transzformáció | Sűrűségfüggvény |
    |---------------|----------------|
    | $Y = X + c$ | $f_Y(y) = f_X(y - c)$ |
    | $Y = aX$ | $f_Y(y) = \frac{1}{\mid a \mid } f_X(y/a)$ |
    | $Y = aX + b$ | $f_Y(y) = \frac{1}{\mid a \mid} f_X((y-b)/a)$ |


## II. Függetlenség, kapcsolat eloszlással, asszimptotikus állítások, Kolgomorov 1-0, Borell-Cantelli, Konvolúció

### Függetlenség

1. $A,B \isin \mathcal{A}$ események függetlenek, ha $P(A \cap B) = P(A) \cdot P(B)$

2. Több eseményre nézve:

    $P(A_{i_1} \cap ... \cap A_{i_k}) = \prod_{j=1}^k P(A_{i_j}), \quad \forall \{i_1, ..., i_k\} \sube \{1, ..., n\}$-re.

3. Eseményrendszerre nézve:

    $(R_{\tau}, \tau \isin \Gamma)$ független, ha: $\forall A_{\tau_1}, ..., A_{\tau_n}, \quad A_{\tau_i} \isin R_{\tau_i}, \; \{\tau_1, ... \tau_n \} \sube \Gamma$ független, ami egyenlő azzal, hogy $P(\cap_i A_{\tau_i}) = \prod_i P(A_{\tau_i})$

    Azaz minden különböző eseménypár a halmazban független.

Tehát a valószínűségi változók függetlenek, ha minden változó által generált $\sigma$-algebrák együttes eseményrendszere független.

**Ekvivalens állítások:**
Legyenek $x = (x_1, ... , x_n): \Omega \mapsto \R \;$ $n$ dimenziós val. változók, ekkor:

- $x_1, ..., x_n$ független val. változók
- $X$ eloszlásfüggvénye a marginális eloszlásfüggvények szorzata: $F_x(t_1, ..., t_n) = \prod_i F_{x_i}(t_i)$
- $Q_x = \prod_i Q_{x_i}$, vagyis az eloszlás, mint mérték előáll a maginális eloszlások szorzatmértékéből

**Abszolút folytonos esetben:**

T.f.h. $X$ absz. folyt., ekkor $f_x(t_1, ..., t_n) \mapsto \prod_i f_{x_i}(t_i)$

**Csoportosított függetlenség:**

Több $\sigma$-algebra diszjunkt halmazokba csoportosítva is függetlenek maradnak.

### Kolgomorov 0-1 törvény

Legyen $\mathcal{F_1}, \mathcal{F_2}, ...$ független $\sigma$-algebrák és $g_n = \sigma(\mathcal{F_n}, \mathcal{F_{n+1}}, ...)$, akkor a csoporttosított függetlenség miatt $g_n$ is független az $\mathcal{F}$-ektől.

Legyen $B \isin \cap_{n=1}^{\infty} g_n$ esemény, ekkor $P(B) = 0$ vagy $1$, azaz biztos vagy nincs rá esély.

### Borel-Cantelli Lemma

$A_1, ..., A_n \isin \mathcal{A}$ események a $\sigma$-algebrában és $\limsup A_n = \cup\cap A_k$, ekkor
1. $\sum_{n=1}^{\infty} P(A_n) \lt \infty \mapsto P(\limsup A_n) = 0$

    Vagyis 1 valószínűséggel következik be véges sok belőlük.

2. $\sum_{n=1}^{\infty} P(A_n) = \infty $ és függetlenek $\mapsto P(\limsup A_n) = 1$

    Vagyis ha független valószínűségek szummája divergens, akkor 1 valószínűséggel végtelen sok következik be belőle.


### Konvolúció

**$\R$-ben:**

Legyen $x,y: \Omega \mapsto \R)$ val. változók és $x+y=z$, ekkor $z$ sűrűségfüggvénye (absz folyt $\lambda$-ra):

$f_{x+y}(z) = \int_{-\infty}^{\infty} f_x(t) \cdot f_y(z-t) d\lambda(t)$

Ha nem absz. folyt, akkor csal az eloszlásfüggvényt lehet megadni, mint Lebesque-Stieljes integrál:

$F_{x+y}(z) = \int_{-\infty}^{\infty} F_x(z-t) dF_y(t)$

Z eloszlása: $Q_z = Q_x \times Q_y \mapsto$ a két eloszlás konvolúciója

**$\R^n$-ben:**

Legyenek Legyen $\underline x, \underline y: \Omega \mapsto \R^n$ val. változók és $\underline x+ \underline y=\underline z$:

- absz. folyt. esetben: $f_z(\underline z) = \int_{\R^n} f_x(\underline t) \cdot f_y(\underline z - \underline t) \; d\lambda_n(t)$

- nem absz. folyt. esetben: $F_z(\underline z) = \int_{\R^n} F_x(\underline z - \underline t) \; dF_y(\underline t)$


## III. Várható érték, magasabb momentumok, kapcsolódó egyenlőtlenségek

### Várható érték

$x: \Omega \mapsto \R$ esetén $\mathbb{E}(x) = \int_\R x \; dQ_x = \int_\Omega X \; dP$

- $x: \Omega \mapsto \R^{n \times m} \quad (X:\Omega \mapsto \R)$ esetben elemenként számoljuk a várható értéket
- Ha a sűrűségfüggvény absz. folyt. $\lambda$ Lebesque mértékre, akkor $\mathbb{E}(X) = \int_\R t f_x(t) \; d\lambda$ Lebesque integrál.

Tulajdonságok:
- Nem biztos, hogy létezik és értelmes
- $\mathbb{E}(X + Y) = \mathbb{E}(X) + \mathbb{E}(Y)$
- $\mathbb{E}(c \cdot X) = c \cdot \mathbb{E}(X)$
- $\mathbb{E}(X \cdot Y) = \mathbb{E}(X) \cdot \mathbb{E}(Y)$, amennyiben X és Y függetlenek és véges várható értékűek.

### Szóráségyzet

Legyen $X$ valószínűségi változó véges várható értékkel, akkor a szórásnégyzet($\mathrm{Var}(X)$, $D^2(X)$):

$\mathrm{Var}(X) = \mathbb{E}((X - \mathbb{E}(X))^2) = \mathbb{E}(X^2) - (\mathbb{E}(X))^2$

Tulajdonságok:
- $\mathrm{Var}(X) \ge 0$
- $\mathrm{Var}(X) = 0 \iff P(X = \mathbb{E}(X)) = 1$, azaz ha a valószínűségi változó m.m. 1 valószínűséggel konstans akkor a szórásnégyzet 0
- $\mathrm{Var}(c \cdot X) = c^2 \cdot \mathrm{Var}(X)$
- Ha $X, Y$ független valószínűségi változók, akkor $\mathrm{Var}(X + Y) = \mathrm{Var}(X) + \mathrm{Var}(Y)$ és $\mathrm{Cov}(X,Y) = 0$
- Amennyiben $X, Y$ valószínűségi változók nem feltétlenül függetlenek, akkor $\mathrm{Var}(X + Y) = \mathrm{Var}(X) + \mathrm{Var}(Y) + 2 \cdot \mathrm{Cov}(X,Y)$

### Magasabb momentumok

**k-adik momentum:**

$\mathbb{E}(\vert X \vert^k), \quad k \in \N^+$ a k-adik abszolút momentum

**k-adik centrált momentum:**

$\mathbb{E}(\vert X - \mathbb{E}(X) \vert^k), \quad k \in \N^+$ a k-adik centrált abszolút momentum

(a 2. centrált momentum a variancia)

### Kovariancia

Kovariancia két valószínűségi változó között:

$\mathrm{Cov}(X,Y) = \mathbb{E}((X - \mathbb{E}(X)) \cdot (Y - \mathbb{E}(Y))) = \mathbb{E}(X \cdot Y) - \mathbb{E}(X) \cdot \mathbb{E}(Y)$

Tulajdonságok:
- $\mathrm{Cov}(X,X) = \mathrm{Var}(X)$
- $\mathrm{Cov}(a \cdot X, b \cdot Y) = a \cdot b \cdot \mathrm{Cov}(X,Y)$
- $\mathrm{Cov}(X + Y, Z) = \mathrm{Cov}(X,Z) + \mathrm{Cov}(Y,Z)$
- $a$ konstans esetén $\mathrm{Cov}(X, a) = 0$
- Ha $X, Y$ független valószínűségi változók, akkor $\mathrm{Cov}(X,Y) = 0$

### Kovariancia mátrix

Legyen $\underline X = (X_1, X_2, ..., X_n): \Omega \mapsto \R^n$ valószínűségi változó, akkor a kovariancia mátrix:

$\Sigma = \mathbb{E}\left( (\underline X - \mathbb{E}(X)) \cdot (\underline X - \mathbb{E}(X))^T \right)$

vagyis:

$
\Sigma = \begin{bmatrix}
\mathrm{Var}(X_1) & \mathrm{Cov}(X_1, X_2) & ... & \mathrm{Cov}(X_1, X_n) \\
\mathrm{Cov}(X_2, X_1) & \mathrm{Var}(X_2) & ... & \mathrm{Cov}(X_2, X_n) \\
... & ... & ... & ... \\
\mathrm{Cov}(X_n, X_1) & \mathrm{Cov}(X_n, X_2) & ... & \mathrm{Var}(X_n)
\end{bmatrix}
$

Tulajdonságok:
- $\Sigma$ szimmetrikus mátrix
- $\Sigma$ pozitív szemidefinit mátrix
- Ha $X_1, X_2, ..., X_n$ független valószínűségi változók, akkor $\Sigma$ diagonális mátrix

### Korrelációs együttható

A korrelációs együttható két valószínűségi változó között:
$R(X,Y) = \frac{\mathrm{Cov}(X,Y)}{\sqrt{\mathrm{Var}(X)} \cdot \sqrt{\mathrm{Var}(Y)}}$

Tulajdonságok:
- $-1 \le R(X,Y) \le 1$
- X és Y kapcsolatát normalizálva mutatkja meg, lineáris az összefüggésük:
    - $R(X,Y) = 1 \iff$ létezik olyan $a > 0$ és $b \in \R$, hogy $P(Y = a \cdot X + b) = 1$
    - $R(X,Y) = -1 \iff$ létezik olyan $a < 0$ és $b \in \R$, hogy $P(Y = a \cdot X + b) = 1$
- Ha $X, Y$ független valószínűségi változók, akkor $R(X,Y) = 0$

### Egyenlőtlenségek

**Jensen-egyenlőtlenség:**

Legyen $\mathbb{E}(X)$ létező várható értékű valószínűségi változó és $f: \R \mapsto \R$ konvex függvény, akkor:

$f(\mathbb{E}(X)) \le \mathbb{E}(f(X))$

Konvex függvény két pont közötti szakasza a függvény felett helyezkedik el.

**Minkowski-egyenlőtlenség:**

Ha $p \ge 1$ és $X, Y$ valószínűségi változók és $\Vert x \Vert_p = \mathbb{E}(\vert x \vert^p)^{\frac{1}{p}}$, ekkor a norma kielégíti a háromszög-egyenlőtlenséget:

$\Vert X + Y \Vert_p \le \Vert X \Vert_p + \Vert Y \Vert_p$

**Hölder-egyenlőtlenség:**

Legyenek $p, q \ge 1$ úgy, hogy $\frac{1}{p} + \frac{1}{q} = 1$ és $X, Y$ valószínűségi változók, akkor:

$\mathbb{E}(\vert X \cdot Y \vert) \le \Vert X \Vert_p \cdot \Vert Y \Vert_q = \mathbb{E}(\vert X \vert^p)^{\frac{1}{p}} \cdot \mathbb{E}(\vert Y \vert^p)^{\frac{1}{p}}$


## IV. Valószínűségi változók konvergenciája, 1 valószínűség, $L_p$-beli sztochasztikus konvergencia, kapcsolatok és eszközei

**Mértékelmeleti konvergenciák:**

- monoton konvergencia tétel: Ha $X_n \xrightarrow{n \mapsto \infty} X$ és $X_n \le X_{n+1}\; \forall n$, akkor $\lim\limits_{n \mapsto \infty} \mathbb{E}(X_n) = \mathbb{E}(X)$
- Fatou-lemma: $X_n \ge 0$ valószínűségi változók, akkor $\mathbb{E}(\liminf\limits_{n \mapsto \infty} X_n) \le \liminf\limits_{n \mapsto \infty} \mathbb{E}(X_n)$
- Lebesuqe-dominált konvergencia tétel: Ha $X_n \xrightarrow{1 \; p.} X$ és létezik olyan $Y$ valószínűségi változó, hogy $\forall n: \vert X_n \vert \le Y$ és $\mathbb{E}(Y) \lt \infty$, akkor $\lim\limits_{n \mapsto \infty} \mathbb{E}(X_n) = \mathbb{E}(X)$

**1 valószínűséggel konvergencia:**

$X_n \xrightarrow{1 \; p.} X \iff P(\{ \omega \in \Omega: \lim\limits_{n \mapsto \infty} X_n(\omega) = X(\omega) \}) = 1$

**L_p-beli konvergencia:**

$X_n \xrightarrow{L_p} X \iff \lim\limits_{n \mapsto \infty} \mathbb{E}(\vert X_n - X \vert^p) = 0$

**Sztochasztikus konvergencia:**

$X_n \xrightarrow{sztoch.} X \iff \forall \epsilon > 0: \lim\limits_{n \mapsto \infty} P(\vert X_n - X \vert \ge \epsilon) = 0$


**Kapcsolatok:**
- $X_n \xrightarrow{1 \; p.} X \mapsto X_n \xrightarrow{sztoch.} X$
- $X_n \xrightarrow{L_p} X \mapsto X_n \xrightarrow{sztoch.} X$
- $X_n \xrightarrow{L_p} X \mapsto X_n \xrightarrow{L_q} X, \quad p \ge q \ge 1$

**Riesz-lemma:**

Ha $X_n \xrightarrow{sztoch.} X$, akkor létezik olyan részhalmaz $X_{n_k}$, hogy $X_{n_k} \xrightarrow{1 \; p.} X$.

**Egyenletes integrálhatóság:**

Legyen $X \isin L_1 \; \mathbb{E}(\vert x \vert) \lt \infty \; H \subset L_1(P)$, $H$ egyeneletesen integrálható, ha:

$\sup \int\limits_{x \isin H \, \{ x \gt c\}} \vert x \vert dP \xmapsto{x \mapsto \infty} 0$

Átfogalmazva $H$ egyenletesen integrálható, ha $\mathbb{E}(x) \lt \infty$ és kicsi halmazokon egy korláton belül marad az integrál értéke.

L_p-beli konvergencia ekvivalens azzal, hogy sztochasztikusan konvergál és $\forall \; \vert x_n \vert^p$ képzett halmaz egyenletesen integrálható.

**Vallée-Poussin tétel:**

Egy $H \subset L_1(P)$ halmaz egyenletesen integrálható, ha:

$\lim\limits_{x \mapsto \infty} \frac{f(x)}{x} = \infty$ és $\sup\limits_{x \in H} \mathbb{E}(f(\vert x \vert)) \lt \infty$.

Vagyis létezik olyan növekvő függvény, ami gyorsabban nő, mint az identitás($x$) és a halmaz elemeinek képeire vett várható értékek korlátosak.

**Scheffé állítás:**

Legyen $x_n \ge 0$ és $X_n \mapsto X$ 1 valószínűséggel, valamint $\mathbb{E}(X_n) \mapsto \mathbb{E}(X)$, akkor $X_n \xrightarrow{L_1} X$.

## V. Valószínűségi változók gyenge és eloszlásbeli konvergenciája, karakterisztikus függvény

### Konvergenciák

**Valószínűségi mérték gyenge konvergenciája:**

$Q_n \xrightarrow{gyengén} Q \iff \forall f: \R \mapsto \R$ folytonos és korlátos függvényre:

$\int f \; dQ_n \mapsto \int  f \; dQ$

**Valószínűségi változók eloszlásbeli konvergenciája:**

$X_n \xrightarrow{eloszlásban} X \iff \forall t \isin C(F_X): \lim\limits_{n \mapsto \infty} F_{X_n}(t) = F_X(t)$

**Eloszlásbeli konvergergencia és más konvergenciák kapcsolata:**
- $X_n \xrightarrow{1 \; p.} X \mapsto X_n \xrightarrow{sztoch.} X \mapsto X_n \xrightarrow{eloszlásban} X \iff X_n \xrightarrow{gyengén} X$

**Lévy-Prohorov metrika:**

Lehet olyan távolságot definiálni valószínűségi mértékek között, ami metrika és a gyenge konvergenciát méri.

Levy-Prohorov metrika:

$\pi(P,Q) = \inf \{ \epsilon > 0: \forall A \isin \mathcal{A}, \; P(A) \le Q(A_{\epsilon}) + \epsilon \; \text{és} \; Q(A) \le P(A_{\epsilon}) + \epsilon \}$

Vagyis a két mérték akkor közel van egymáshoz, ha minden esemény mértéke közel van a másik esemény egy kis kiterjesztett változatának mértékéhez.

### Karakterisztikus függvény

$x$ valószínűségi változó karakterisztikus függvénye:

$\varphi_x(t) = \mathbb{E}(e^{i t x}) = \int\limits_{-\infty}^{\infty} e^{i t x} \; dQ_x(x)$

Ami egy $\R \mapsto \C$ komplex értékű függvény.

**Tulajdonságok**:
- $\varphi_x(0) = 1$
- $\vert \varphi_x(t) \vert \le 1$
- $\varphi_x(t)$ egyenletesen folytonos minden $t \isin \R$-en
- Mivel $f$ szimmetrikus: $\varphi_x(-t) = \overline{\varphi_x(t)}$
- Ha $x$ és $y$ független valószínűségi változók, akkor $\varphi_{x+y}(t) = \varphi_x(t) \cdot \varphi_y(t)$
- Ha $X$ absz. folyt. valószínűségi változó sűrűségfüggvénnyel $f_x$, akkor $\varphi_x(t) = \int\limits_{-\infty}^{\infty} e^{i t x} f_x(x) \; d\lambda(x)$, azaz a karakterisztikus függvény a sűrűségfüggvény Fourier-transzformáltja
- Ha $x \; L^p$-beli, akkor $\varphi_x$ differenciálható $p$-szer és $\varphi_x^{(k)}(t) = \int\limits_{-\infty}^{\infty} (i x)^k e^{i t x} \; dQ_x(x)$, valamint $\varphi_x^{(k)}(0) = i^k \mathbb{E}(X^k)$

**Inverziós formula:**

Legyen $X$ valószínűségi változó karakterisztikus függvénnyel $\varphi_x(t)$ és eloszlásfüggvénnyel $F_x(x)$, akkor ha $a,b \isin C(F_x)$, akkor:

$F_x(b) - F_x(a) = \lim\limits_{T \mapsto \infty} \frac{1}{2 \pi} \int\limits_{-T}^{T} \frac{e^{-i t a} - e^{-i t b}}{i t} \varphi_x(t) \; dt$

**Sűrűségfüggvény inverziós formula:**

Ha $X$ absz. folyt. valószínűségi változó sűrűségfüggvénnyel $f_x(x)$ és karakterisztikus függvénnyel $\varphi_x(t)$, akkor ha $f_x$ folytonos az $x$ pontban, akkor:

$f_x(x) = \lim\limits_{T \mapsto \infty} \frac{1}{2 \pi} \int\limits_{-T}^{T} e^{-i t x} \varphi_x(t) \; dt$

**Konvergencia karakterisztikus függvények alapján:**

$X_n \xrightarrow{eloszlásban} X \iff \varphi_n(t) \xrightarrow{egyenletesen} \varphi(t) $

## VI. Nagy számok gyenge és erős törvényei, független sorok

**Markov egyenlőtlenség:**

Legyen $X$ nem negatív valószínűségi változó és $a \gt 0$, akkor:

$P(X \ge a) \le \frac{\mathbb{E}(X)}{a}$

**Nagy számok törvényének általános teljesülése:**

Legyenek $X_1, X_2, ...$ független valószínűségi változók azonos eloszlással és véges várható értékkel $\mathbb{E}(X_i) = \mu \lt \infty$, akkor a mintaátlag:

$\overline{X_n} = \frac{X_1 + X_2 + ... + X_n}{n} \xrightarrow{sztoch.} \mu$

### Nagy számok gyenge törvénye

Legyenek $X_1, X_2, ...$ független, egymással páronként korrelálatlan valószínűségi változók azonos eloszlással és véges várható értékkel $\mathbb{E}(X_i) = \mu, \quad \mathrm{Var}(X_i) = \sigma^2 \lt \infty$, ekkor $\forall \epsilon \gt 0$-ra:

$P(\vert \overline{X_n} - \mu \vert \ge \epsilon) \xmapsto{n \mapsto \infty} 0$

Vagyis a tapasztalati és elméleti átlag különbsége $0$-ba konvergál sztochasztikusan $L_2$-ben.

**Feller gyenge nagy számok törvénye:**

Legyenek $X_1, X_2, ...$ független valószínűségi változók azonos eloszlással és véges várható értékkel $\mathbb{E}(X_1) = \mu \lt \infty$, valamint teljesüljön, hogy:

$\frac{\sum\limits_{i=1}^{n} X_i}{n} \xmapsto{Sztoch.} \mathbb{E}(X_1)$ 

A tapasztalati átlag sztochasztikusan konvergál az elméleti átlaghoz.

### Nagy számok erős törvénye

Legyenek $X_1, X_2, ...$ független valószínűségi változók azonos eloszlással és véges várható értékkel $\mathbb{E}(\vert X_1 \vert) \lt \infty$, akkor:

$\frac{\sum\limits_{i=1}^{n} X_i}{n} \xmapsto{1 \; p.} \mathbb{E}(X_1)$

Tapasztalati átlag 1 valószínűséggel konvergál az elméleti átlaghoz.

Megjegzések:
- Ha $\mathbb{E}(\vert X_1 \vert^2) \lt \infty$, akkor a gyenge és erős törvény is teljesül.
- Ha csak $\mathbb{E}(\vert X_1 \vert) \lt \infty$, akkor csak az erős törvény teljesül.

Alkalmazás:
- Borel-Cantelli lemma bizonyítása az erős törvény segítségével.
- Monte-Carlo integrálok numerikus közelítése.


### Egyenlőtlenségek becsléseknél

**Markov egyenlőtlenség:**
Legyen $X \ge 0$ és $\mathbb{E}(X) \lt \infty$, ekkor bármilyen T statisztika esetén:

$P(x \ge T) \le \frac{\mathbb{E}(x)}{T}$

**Csebisev egyenlőtlenség:**

Legyen $X$ valószínűségi változó véges várható értékkel és szórásnégyzettel, akkor bármilyen T statisztika esetén:

$P(\vert X - \mathbb{E}(X) \vert \ge T) \le \frac{\mathrm{Var}(X)}{T^2}$

## VII. Centrális határeloszlás tétel változatai

### Centrális határeloszlás tétel

Legyen $x_1, x_2, ...$ független, azonos eloszlású valószínűségi változók véges várható értékkel és szórásnégyzettel: $\mathbb{E}(x_i) = \mu, \quad \mathrm{Var}(x_i) = \sigma^2 \lt \infty$, ekkor a normált összeg:

$S_n = \sum\limits_{i=1}^{n} x_i$, ekkor:

$\frac{S_n - n \mu}{\sigma \sqrt{n}} \xmapsto{eloszlásban} N(0,1)$

Tulajdonságok:
- Az összeg eloszlása közelít a normális eloszláshoz, ha a mintaelemek száma elég nagy.
- Az eloszlásfüggvények konvergenciája egyenletes a valószínűségi változó folytonos pontjain.

### Független szériasorozat

Legyenek $x_{n,j}, \quad n=1,2,..., \quad j=1,2,...,k_n$ valószínűségi változók, ahol minden rögzített $n$-re $x_{n,1}, ..., x_{n,k_n}$ függetlenek. Nem szükséges, hogy azonos eloszlásúak legyenek, csak függetleneknek. 


### Lindeberg-Feller tétel

Legyen $x_{n,j}, \quad n=1,2,..., \quad j=1,2,...,k_n$ független szlriasorozat, aminek várható értéke nulla, szórásnégyzete pedig 1: $\mathbb{E}(x_{n,j}) = 0, \quad \mathrm{Var}(x_{n,j}) = 1$.

- CHT: $S_n \xmapsto{eloszlásban} N(0,1)$
- $\max\limits_{1 \le j \le k_n} \sigma_{n,j}^2 \xmapsto{n \mapsto \infty} 0$ asszimptotikusan kicsi

Lindeberg-Feller:

$\sum\limits_{j=1}^{k_n} \mathbb{E} (x_{n,j}^2 \cdot \chi_{\{ \vert x_{n,j} \vert \ge \epsilon \}}) \xmapsto{n \mapsto \infty} 0, \quad \forall \epsilon \gt 0$


### Ljapunov tétel

A momentumok segítségével mondja meg, hogy mikor tartunk a normális eloszláshoz. Feltételei a ugyan azok. mint a Lindeberg-Feller esetén.

$\varGamma_n^{2 + \delta} = \sum\limits_{j=1}^{k_n} \mathbb{E}(\vert x_{n,j} \vert^{2 + \delta}) \xmapsto{n \mapsto \infty} 0, \quad \text{valamilyen} \; \delta \gt 0$

### Berry-Esseen tétel

Legyenek $x_1, x_2, ...$ FAE val. változók, $\mathbb{E}(x_1) = 0, \; \sigma^2(x_1) = \mathbb{E}(x_1^2) és $\mathbb{E}(\vert x_{n,j} \vert^{2 + \delta}) \lt \infty$ valamilyen $0 \lt \delta \le 1$ mellett. Ekkor:

$\sup \vert P (\frac{\sum\limits_{j =1}^n x_j}{\sigma \cdot \sqrt{n}} \lt x) - \phi(x) \vert \le c_{\vartheta} \cdot \frac{\mathbb{E}(\vert x_1 \vert^{2 + \delta})}{\sigma^{2 + \delta} \cdot n^{\delta/2}}$

Ahol:
- $P(...)$ a normált átlag eloszlásfüggvénye
- $\phi(x)$ a standard normális eloszlásfüggvénye
- $c_{\vartheta}$ egy abszolút állandó, ami csak $\delta$-től függ, azaz, hogy milyen magas momentumunk van

Azért legjobb a $\delta = 1$, mert akkor lesz a legkisebb a hiba.

## VIII. Feltételes várható érték és tulajdonságai, feltételes eloszlás

Feltételes valószínűség: $P(A \vert B) = \frac{P(A \cap B)}{P(B)}$, ha $P(B) \gt 0$

### Feltételes várható érték

**Klasszikus fogalma:**

Pozitív valószínűségű eseményre nézve($P(A) \gt 0$):

$\mathbb{E}(X \vert A) = \frac{\mathbb{E}(X \cdot \chi_A)}{P(A)}$

Ahol $\chi_A$ az $A$ esemény indikátora.

**Teljes várható érték tétele:**

Legyenek $A_1, A_2, ...$ diszjunkt események, ekkor:

$\mathbb{E}(X) = \sum\limits_{i} \mathbb{E}(X \vert A_i) \cdot P(A_i)$

Feltételes várható érték feltételei:

Legyen $x: \Omega \to \mathbb{R}$ egy valós értékű valószínűségi változó, melyre $\mathbb{E}$ véges és $\mathcal{F} \sube \mathcal{A}$ egy $\sigma$-algebra. $z$ változó $x$-nek $\mathcal{F}$-re vonatkozó feltételes várható értéke, ha teljesül $z = \mathbb{E}(x \mid \mathcal{F})$ 

- $\mathcal{F}$-mérhető
- $\forall B \in \mathcal{F}$-re: $\int\limits_{B} z \; dP = \int\limits_{B} x \; dP$

Ez továbbra sem egy szám, hanem egy valószínűségi változó. A $\sigma$-algebra reprezentálja a rendelkezésre álló információt.

**Tulajdonságok:**

- Lineáris: $\mathbb{E}(aX + bY \mid \mathcal{F}) = a \mathbb{E}(X \mid \mathcal{F}) + b \mathbb{E}(Y \mid \mathcal{F})$
- $x \ge 0 \; p. \Rightarrow \mathbb{E}(x \mid \mathcal{F}) \ge 0$ 1 valószínűséggel
- $\vert \mathbb{E}(x \mid \mathcal{F}) \vert \le \mathbb{E}(\vert x \vert \mid \mathcal{F})$ (Jensen egyenlőtlenség)
- $\mathbb{E}(x \cdot y \mid \mathcal{F}) = y \cdot \mathbb{E}(x \mid \mathcal{F})$, ha $y$ $\mathcal{F}$-mérhető
- $x$ $\mathcal{F}$-mérhető $\Rightarrow \mathbb{E}(x \mid \mathcal{F}) = x$
- Ha $\mathcal{F}$ a triviális $\sigma$-algebra, akkor $\mathbb{E}(x \mid \mathcal{F}) = \mathbb{E}(x)$
- Két feltétel esetén a szűkebb számít: $y \isin \mathcal{F}: \mathbb{E}(\mathbb{E}(x \mid \mathcal{F}) \mid \mathcal{G}) = \mathbb{E}(x \mid \mathcal{G})$
- Teljes várható érték tétele: $\mathbb{E}(\mathbb{E}(x \mid \mathcal{F})) = \mathbb{E}(x)$

**Feltételes várható érték létezése és egyértelműsége:**

Tetszőleges $x$ valószínűségi változó létezik, $\mathbb{E}(x)$ létezik és véges, akkor $z = \mathbb{E}(x \mid \mathcal{F})$ létezik és m.m. egyértelmű.

**Feltételes Jensen egyenlőtlenség:**

Legyen $x: \Omega \mapsto \R^n$ valószínűségi változó és $f: \R^n \mapsto \R$ konvex függvény, akkor:

$f(\mathbb{E}(x \mid \mathcal{F})) \le \mathbb{E}(f(x) \mid \mathcal{F})$

Következmény:

$\mathbb{E}(x^2) \lt \infty,\; p = 2,\; y \; \mathcal{F}$-mérhető és $y \ne \mathbb{E}(x \mid \mathcal{F})$, akkor:

$\mathbb{E}((x - \mathbb{E}(x \mid \mathcal{F}))^2 \mid \mathcal{F}) \le \mathbb{E}((x - y)^2 \mid \mathcal{F})$

**Konvergenciák mértékelméletből:**

- Monoton konvergencia: $0 \ge z_1 \ge z_2 \ge ... \to z \; \mathbb{E}(z_n \mid \mathcal{F})$ 1 valószínűséggel
- Fatou-lemma: $\mathbb{E}(\liminf z_n \mid \mathcal{F}) \le \liminf \mathbb{E}(z_n \mid \mathcal{F})$ 1 valószínűséggel
- Lebesque-dominált konvergencia: ha van $x_n$-hez olyan $z$, hogy $\vert x_n \vert \le z$ és $\mathbb{E}(z) \lt \infty$, továbbá $x_n \to x$ 1 valószínűséggel, akkor:
$\mathbb{E}(x_n \mid \mathcal{F}) \to \mathbb{E}(x \mid \mathcal{F})$ 1 valószínűséggel

### Feltételes eloszlás

A feltételes eloszlás esetében fordítva dolgozunk, először definiálunk egy feltételes várható értéket, majd abból következtetünk a feltételes eloszlásra.

$P(A \mid \mathcal{F}) = \mathbb{E}(\chi_A \mid \mathcal{F})$ továbbra is valószínűségi változó.

Ahol $A \in \mathcal{A}$ esemény, $\mathcal{F} \sube \mathcal{A}$ egy $\sigma$-algebra és $\chi_A$ az $A$ esemény indikátora.

Megválaszthatóak $P(A \mid \mathcal{F})$ értékei úgy, hogy $\forall \omega in \Omega$-ra a valószínűségi mérték: $P(A \mid \mathcal{F})(\omega)$ legyen.

### Feltételes sűrűségfüggvény

Legyen $x, y: \Omega \to \R^2$ folytonos eloszlással $f_{x,y} = f(x,y)$ és a marginálisok $f_x(x)$ és $f_y(y)$. Ekkor a feltételes sűrűségfüggvény:

$f_{x \mid y}(x,y) = \begin{cases}
\frac{f_{x,y}(x,y)}{f_y(y)}, & f_y(y) \gt 0 \\
f_x(x), & \ f_y(y) = 0
\end{cases}$

## IX. Martingálok tulajdonságai, Doob-felbontás, kanonikus növekvő folyamata, megállás idő

Adott $\mathcal{F}_1 \sube \mathcal{F}_2 \sube ...$ növekvő $\sigma$-algebra sorozat (Filtráció) és egy $X_1, X_2, ...$ valószínűségi változó sorozata, amik az indexükhöz tartozó $\sigma$-algebrákra mérhetőek (Adaptált sorozat).

### Martingálok

Egy $(x_n, \mathcal{F}_n)$ sorozatpár martingál, ha:
- $x_n$ adaptált sorozat az $\mathcal{F}_n$ filtrációra
- minden $n$-re: $\mathbb{E}(\vert x_n \vert) \lt \infty$
- minden $n$-re: $\mathbb{E}(x_n \mid \mathcal{F}_{n-1}) = x_{n-1}$

Szubmartingál, ha az utolsó feltétel helyett: $\mathbb{E}(x_n \mid \mathcal{F}_{n-1}) \ge x_{n-1}$

Szupermartingál, ha az utolsó feltétel helyett: $\mathbb{E}(x_n \mid \mathcal{F}_{n-1}) \le x_{n-1}$

**Martingál differencia:**

$d_n = x_n - x_{n-1}, \; d_1 = x_1$

Vagyis mennyit változott a martingál egy lépésben.

Ekkor viszont $x_n$ előállítható martingál differenciák összegzésével:

$x_n = \sum\limits_{i=1}^{n} d_i$

**Valószínűségi változók, mint martingál differenciák:**

Ha $d_1, d_2, ..., d_n$ 0 várható értékű, független valószínűségi változók, akkor martingál differenciák adott $\mathcal{F}_n = \sigma(d_1, d_2, ..., d_n)$ filtrációra. Ekkor korrelálatlanok is.

**Megállási idő:**

Adott $\nu: \Omega \to \Z^+ \cup \{\infty\}$ valószínűségi változó, amire:

$\{ \nu = m \} \in \mathcal{F}_m$, $\nu$ az az esemény, $m$-et vesz fel, amikor megállok.

Vagyis $m$ időpontban tudom, hogy megállok-e vagy sem. Előtte még lehet véletlen.

**Megállított szubmartingál:**

Ha $(x_n, \mathcal{F}_n)$ szubmartingál és $\nu$ megállási idő, akkor a megállított szubmartingál $($x_{n \land \nu}, \mathcal{F}_n)$, ahol:

$x_{n \land \nu} = \begin{cases}
x_n, & n \le \nu(\omega) \\
x_{\nu(\omega)}, & n \gt \nu(\omega)
\end{cases}$

Ez felfogható úgy is, hogy a minimumot vesszük a megállási idő és az aktuális idő között.

### Doob-egyenlőtlenség

Ha tudjuk $n$ pillanatbeli momentumot, akkor egész jó képet kapunk a maximumról.

Ha $(x_n, \mathcal{F}_n)$ szubmartingál és $x_n \gt 0$, akkor:

$\mathbb{E}((x_n^*)^p) \le (\frac{p}{p-1})^p \mathbb{E}(x_n^p), \quad p > 1$

Ha $(x_n, \mathcal{F}_n)$ martingál, akkor:

$\Vert x_n^* \Vert_p \le \frac{p}{p-1} \cdot \Vert x_n \Vert_p, \quad p > 1$

Ha abszolút érték helyett más konvex függvényt alkalmazunk, akkor is hasonló egyenlőtlenséget kapunk.

### Doob-felbontás

**Előrejelezhető folyamat:**
Ha $(x_n, \mathcal{F}_n)$ mérhető, akkor a sorozat mindig az előző $\sigma$-algebrára is mérhető lesz.

**Doob-felbontás:**

$(x_n, \mathcal{F}_n)$ szubmartingál előállítható, mint $X_n = M_n + A_n$, ahol $(M_n, \mathcal{F}_n)$ martingál és $(A_n, \mathcal{F}_n)$ előrejelezhető, nemnegatv, m.m. növekvő folyamat.

Tulajdonságok:
- $A_n - A_{n-1} = \mathbb{E}(X_n - X_{n-1} \mid \mathcal{F}_{n-1}) = \mathbb{E}(d_n \mid \mathcal{F}_{n-1})$
- $A_n = \sum\limits_{i=1}^{n} \mathbb{E}(d_i \mid \mathcal{F}_{i-1})$
- $M_n = \sum\limits_{i=1}^{n} (d_i - \mathbb{E}(d_i \mid \mathcal{F}_{i-1}))$ úgy nevezett Doob-martingál

### Martingálok kanonikus növekvő folyamata

**Négyzetesen integrálható martingál kanonikus növekvő folyamata:**

Ha vesszük egy martingál négyzetét, akkor az egy szubmartingál lesz. Ebből a szubmartingálból előállítható egy kanonikus növekvő folyamat, ami a martingál varianciáját méri.

$\mathbb{E}(d_k^2 \mid \mathcal{F}_{k-1})$ a növekmény, a szummája pedig a kanonikus növekvő folyamat:

$A_n = \sum\limits_{k=1}^{n} \mathbb{E}(d_k^2 \mid \mathcal{F}_{k-1})$

A kanonikus növekvő folyamat tulajdonságai:
- $A_n$ nemnegatív, m.m. növekvő és jobbról folytonos
- $A_0 = 0$

## X. Martingálok konvergencia tételei, nagy-eltérés tételek

### Martingálok konvergenciája

1. Legyen $(x_n, \mathcal{F}_n)$ martingál és $\sup\limits_{n} \mathbb{E}(x_n^2) \lt \infty$, akkor $L_2$-ben korlátos. Ebbők következik, hogy:
    - $x_n$ konvergens 1 valószínűséggel és $L_2$-ben is
    - $L_2$-bem korlátos martingál 1 valószínűséggel és $L_1$-ben is konvergens
    - Doob-egyenlőtlenségből pedig következik, hogy $x_n^*$ is korlátos

2. Legyen $(x_n, \mathcal{F}_n)$ szubmartingál $L_2$-ben korlátos és nemnegatív. Ekkor:
    - $x_n$ konvergens 1 valószínűséggel és $L_2$-ben is
    - Ha $\sup\limits_{n} \mathbb{E}(x_n) \lt \infty$, akkor $x_n$ konvergens 1 valószínűséggel és $L_1$-ben is
3. Legyen $(x_n, \mathcal{F}_n)$ szupermartingál, ha nemnegatív akkor $x_n$ konvergens 1 valószínűséggel és $L_1$-ben is.
4. Krickeberg-felbontás: Ha $(x_n, \mathcal{F}_n)$ martingál $L_1$-ben korlátos, akkor felbontható két nemnegatív szubmartingál különbségeként: $x_n = x_n^+ - x_n^-$, ahol $x_n^+, x_n^- \ge 0$ és mindkettő $L_1$-ben korlátos.
5. Ha egy martingál $L_1$-ben korlátos, akkor konvergens 1 valószínűséggel és $L_1$-ben is.

**Reguláris martingál:**

**Ekvivalens állítások:**

Bármilyen martingálra $(x_n, \mathcal{F}_n)$ az alábbi állítások ekvivalensek:
- $L_1$-ben konvergens 
- Egyenletesen integrálható
- Reguláris martingál

**$p \gt 1$ esetén ekvivalensek:**

- $L_p$-ben konvergens
- $L_p$-ben korlátos
- Reguláris martingál $x \isin L_p$

### Becslések, egyenlőtlenségek martingálokra

***Bernstein-féle maximum becslés:**

$(x_n, \mathcal{F}_n)$ martingálra akarjuk becsülni, hogy a maximum nagyobb-e, mint adott $\lambda$:

$P(x_n^* \ge \lambda) \le e^{-t\lambda} \cdot \mathbb{E}[e^{t x_n}]$

Ahol $t \gt 0$ és $\lambda$ tetszőleges.

Ha növeljük $\lambda$-t, akkor csökkenni fog az egyenlőtlenség jobb oldala, $t$-t pedig úgy válasszuk meg, hogy minimalizáljuk a jobb oldalt.

**Azuma-Hoeffding egyenlőtlenség:**

Legyen $(x_n, \mathcal{F}_n)$ egy martingál, amire $|x_n - x_{n-1}| \le c_n$ teljesül m.m. minden $n$-re, vagyis a növekményei korlátosak. Ekkor bármilyen $\lambda \gt 0$ és $x_0 = 0$-ra:

$P(x_n \ge \lambda) \le e^{-\frac{\lambda^2}{2 \sum_{k=1}^n c_k^2}}$

$P(\vert x_n \vert \ge \lambda) \le 2 e^{-\frac{\lambda^2}{2 \sum_{k=1}^n c_k^2}}$

Ha $S_n = 1$, vagyis a növekmények korlátja 1, akkor:

$P( x_n \ge \lambda) \le e^{-\frac{\lambda^2}{n}}$

**Talagrand egyenlőtlenség:**

Legyen $x_1, x_2, ..., x_n$ FAE valószínűségi változók $[0,1]$ intervallumon és $f: \R^n \to \R$ konvex és Lipschitz-folytonos függvény:

$P(\vert f(x_1, x_2, ..., x_n) - m_f \vert \ge \lambda) \le 4 e^{-\frac{\lambda^2}{4}}$

Ahol $m_f$ a $f(x_1, x_2, ..., x_n)$ mediánja.
