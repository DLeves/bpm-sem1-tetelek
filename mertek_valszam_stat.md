*Készítette: Dittrich Levente, 2025*

# Mértékelmélet

Órai videók:
- [Első előadás](https://youtu.be/OXQnszgqr38?si=MunomfBGGzM-mily)
- [Második előadás](https://youtu.be/XwVpHkQnmrE?si=-TJKX-JSLYFBGsre)
- [Harmadik előadás](https://youtu.be/0cUc5JkPuag?si=SjTLq8BqAgGA_z66)

## I. Mérhető tér, mérhető leképezések, mérték

Alapfogalmak:
- $X$ alaptér
- $\mathcal{P}(X)$: hatványhalmaz (powerset) - $X$ halmaz minden részhalmazának rendszere
- $A \subset \mathcal{P}(X)$: halmazrendszer

### Halmazrendszerek

- **Modulus**: ha $A, B \in \mathcal{A}$ esetén $A \setminus B \in \mathcal{A}$
- **Félgyűrű**: ha $A, B \in \mathcal{A}$ esetén $A \cap B \in \mathcal{A}$
- **Algebra**: ha $A, B \in \mathcal{A}$ esetén $X \setminus A \in \mathcal{A}$
- **$\sigma$-algebra**: $\mathcal{A} \sube \mathcal{P}(X)$ $\sigma$-algebra, ha:
    - $0, X \in \mathcal{A}$
    - $a \in \mathcal{A} \Rarr \mathcal{A^c} := X \setminus A \in \mathcal{A}$
    - $\mathcal{A_i} \in \mathcal{A}, i \in \N \Rarr \cup_{i=1}^{\infty} \mathcal{A_i} \in \mathcal{A}$
- **Generált $\sigma$-algebra**: Tetszőleges $\mathcal{U}$ rendszerhez $\exists$ egy legszűkebb $\sigma$-algebra ami tartalmazza $\mathcal{U}$-t, jelölés: $\sigma(\mathcal{U})$
- **Borel $\sigma$-algebra**: A legkisebb $\sigma$-algebra, ami tartalmaz minden nyílt halmazt. Legyen $(X,\tau)$ topologikus tér, ekkor $B(X):= \sigma(\tau)$

### Halmazfüggvények

$\alpha: \mathcal{A} \rarr \R$ halmazfüggvény, feltevések:
- $\empty \in \mathcal{A}$ (tartalmazza az üreshalmazt)
- $\alpha \ge 0$ (nemnegatív)
- $\alpha(\empty) = 0$ (üreshalmaz mértéke 0)

Típusok:
- **$\alpha$ monoton**, ha: $A, B \in \mathcal{A}$ és $A \subset B$, akkor $\alpha(A) \le \alpha(B)$
- **$\alpha$ additív**, ha: $A_1, A_2, ... , A_n \in \mathcal{A}$ halmazokra $\cup_{k=1}^{n} A_k \in \mathcal{A}$ esetén $\alpha(\cup_{k=1}^{n} A_k) = \sum_{k=1}^{n} \alpha(A_k)$
- **$\alpha$ $\sigma$-additív**, ha: $A_1, A_2, ... \in \mathcal{A}$ halmazokra $\cup_{k=1}^{\infty} A_k \in \mathcal{A}$ esetén $\alpha(\cup_{k=1}^{\infty} A_k) = \sum_{k=1}^{\infty} \alpha(A_k)$

### Mérhető tér

$(X, \mathcal{A})$ mérhető tér, ha $\mathcal{A} \in \mathcal{P}(X)$ $\sigma$-algebra. Ekkor \mathcal{A} elemei mérhető halmazok.

Topologikus tér ($(X,\tau)$) egy általánosított metrikus tér. A metrikus tér, egy olyan halmaz, amin értelmezett egy metrika (távolságfüggvény).

### Mérhető leképezés

Adott $(X, \mathcal{M})$ és $(Y, \mathcal{N})$ mérhető terek, az $f: X \rarr Y (\mathcal{M}, \mathcal{N})$ mérhető leképezés. Ekkor $\{ A \subset Y: f^{-1}(A) \in \mathcal{M} \}$ az halmazrendszer $\sigma$-algebra $Y$-on.

Generált alterekkel tulajdonság:

$U \subset \mathcal{P}(Y) \; \forall u \isin U: f^{-1}(u) \isin M$
- $\forall u \isin \sigma(U)$-ra is $\rarr$ a generált altér is a $\sigma$-algebrában van
- elég a generált alteret nézni, hogy mérhető-e 1-1 helyen, nem kell a teljeset

### Egyszerű függvények

Legyen $(X, \mathcal{M})$ mérhető tér, ekkor az $f: x \rarr \R$ leképezést egyszerű függvénynek nevezzük, ha mérhető és értékkészlete véges. Ha $f,g$ egyszerű függvény, akkor $f+g$, $f \cdot g$, $max(f,g)$, $min(f,g)$ is egyszerű függvény, így mérhető is.

Az egyszerű függvény előáll $f= \sum_{i=1}^{k} c_i \chi_{A_i}$-ból, ahol
- $c_i$ a súlyozás
- $\chi_{A_i}$ indikátorfüggvény

**Egyenletes konvergencia**: Legyen $f: X \rarr \overline\R$ mérhető, ekkor megadható $f_i$ egyszerű függvények sorozata úgy, hogy 
- monoton nőnek
- $f_i \rarr f$
- $\{ x: f(x) \lt a\}$-n egyenletesen konvergens

**Suprémum és infinimum**:
$f_n: X \rarr \overline \R$ mérhető $\Rarr \sup f_n, \inf f_n, \lim\sup f_n, \lim\sup f_n$ is mérhetők
- $\sup f_n$: a függvény legmagasabb értéke az adott pontban
- $\lim\sup f_n$: a legmagasabb érték, amit elér a függvény, ahogy halad $\infty$ felé

Infinimum hasonlóan, csak legkisebb értékkel.

### Mérték

Legyen (X, \mathcal{M}) mérhető tér, a $\mu: \mathcal{M} \rarr \overline\R$ leképezést mértéknek nevezzük, ha
1. $\mu \ge 0$
2. $\mu(\empty) = 0$
3. $H_n \in \mathcal{M}, H_n \cap H_k = 0$ esetén $\mu(\cup_{i=1}^{\infty} H_i) = \sum_{i=1}^{\infty} \mu(H_i)$


**The Bright Side of Mathematics vidik**: 
- [$\sigma$-algebra](https://youtu.be/xZ69KEg7ccU?si=C9r1hWmVKRvSQdif)
- [Borel $\sigma$-algebra](https://youtu.be/z5m6HXKx0Wo?si=CTafKwAV9K5xf1TA)
- [Mérhető terek](https://youtu.be/11heoNVavvM?si=siO9Wsuj485i5DWe)
- [Mértékek](https://youtu.be/7O7qPrNIt7w?si=k13l2xuJWvkvXic2)

## II. Integrál, függvénysorozatok, függvénysorok és integráljaik

### Riemann integrál

Adott $f \ge 0$ egyszerű függgvény és $(X, \mathcal{M}, \mu)$ mértéktér, valamint $H \isin \mathcal{M}$ mérhető halmaz. $f$ értékei $c_1, ..., c_n$ és $A_k = \{x: f(x) = c_k \}$, vagyis $A_k$ az a halmaz, ahol $f$ felveszi a $c_k$ értéket.

Ekkor $f$ függvény $H$-n vett $\mu$ szerinti integrálja:

$\int_H f \, d\mu = \sum_{k=1}^n c_k \cdot \mu(H \cap A_k)$

- Vagyis a halamzok mértéke súlyozva a függvényértékkel
- Ami nem más, mint a $c_k$ magasságokkal az $A_k$ hosszok szorozva $\Rarr$ terület

**Megjegyzések**:

Adott $0 \le g \le f$ mérhető függvények és $A \subset B$ halmazok, ekkor

- $\int_A g \, d\mu \le \int_A f \, d\mu \le \int_B g \, d\mu$

- $g \mid_A \equiv c$ (konstans) esetén $\int_A f \; d\mu = c \cdot \mu(A)$ (megj: $g \mid_A$ a $g$ függvény megszorítva $A$ pontra/környezetére)

- $\mu(A) = 0 \Rarr \int_A f \; d\mu = 0$, vagyis üres halmazon integrálva nullát kapunk

- $\int_A f \; d\mu = \int_b f \cdot \chi_A \; d\mu$, vagyis $A$-n vett integrál megegyezik a $B$-n vett $f$ és az indikátorfüggvény szorzatának integráljával.

- $\int_A (f + c \cdot g) \; d\mu = \int_A f \; d\mu + c \cdot \int_A g \; d\mu$ integrálási azonosság

- $\varphi(H) = \int_H f \; d\mu$ az integrálás, mint halmazfüggvény mérték

### Lebesque integrál

Legyen $f \ge 0$ mérhető, $H \isin \mathcal{M}$ mérhető halamaz, ekkor:

$\int_H f \; f\mu = \sup \{\int_H g \; d\mu: 0 \le g \le f \}$, g egyszerű függvény. Ez azt jelenti, hogy $f$ integrálja a szuprémuma minden $f$ alatti függvény integráljának.

**Megjegyzések**:
- $f^+ = \max(f,0), f^- = -\min(f,0)$ adott, ha $\int_X f^+ d\mu$ vagy $\int_X f^- d\mu$ véges akkor $f$ integrálható, illetve $\int_X f^+ d\mu - \int_X f^- d\mu$ véges esetén $f$ végesen integrálható.

- $L_1 = \int \mid f \mid \; d\mu$ értelmes és véges
### Monton konvergencia tétel

Legyen $0 \le f_1 \le ... \le f_n$ m.m. monoton növekvő, $\lim_{n \rarr \infty} f_n = f$ pontonként konvergáló, mérhető függvénysorozat.

Ekkor az inegrál is konvergál $\lim_{n \rarr \infty} \int_X f_n \; d\mu = \int_x f \; d\mu$ 

Ilyen tételek miatt sokszor jobb a Lebesque integrál a Riemann integrálnál.

### Összeg integrálja

 $\int_A (f + g) \; d\mu = \int_A f \; d\mu + \cdot \int_A g \; d\mu$, ahol $f, g \ge 0$

### Beppo-Levi Tétel

Ha $f_n \ge 0$ mérhető, akkor a függvények összegének integrálja megegyezik az integráljaik összegével.

$\int_X \sum_{n=1}^{\infty} f_n \; d\mu = \sum_{n=1}^{\infty} \int_X f_n \; d\mu$

### Fatou-Lemma

a $f_n \ge 0$ mérhető, akkor:

$\int_A \liminf f_n \; d\mu \le \liminf \int_A f_n \; d\mu$

### Lebesque-dominált konvergencia tétel

$f_n$ mérhető és $\mid f_n \mid \le g, \quad g \isin L_1$, ekkor $f_n \rarr f$, valamint:

$\int_X f \; d\mu = lim \int_x f_n \; d\mu$

Ha a két fv m.m. megegyezik, akkor az integráljuk is. Ilyenkor $g$ majorálja (dominálja) $\mid f_n \mid$-et, vagyis felettük helyezkedik el. 

## III. Mértékek kiterjesztése. Lebesque- és Lebesque-Stieljes mérték

### Külső mértékek

$\alpha$ külső mérték: $\mathcal{A} \sube \mathcal{P}(X)$ halmazrendszeren, $\alpha(\empty) = 0$ és $\alpha \ge 0$, $\alpha: \mathcal{A} \rarr \overline \R$. $A_1, A_2, ... \in \mathcal{A}$ halmazokra $\alpha(\cup_{i=1}^{\infty} A_i) \le \sum_{i=1}^{\infty} \alpha(A_i)$

$\empty \isin \mathcal{A} \sube \mathcal{P}(X), \; \alpha \ge 0$-ra:
$\varphi_\alpha(H) = \inf \{ \sum \alpha(A_i) \mid \cup A_i \gt H_i ; A_i \isin \mathcal{A}\}$

Legyen $\mathcal{l}_\alpha$ egy külső mérték $\mathcal{P(X)}$-en, ha $\alpha$ egy külső mérték az $\mathcal{A}: \varphi_\alpha \mid \mathcal{A} = \alpha$-n.

Legyen $\mathcal{M}_{\varphi_\alpha \subset \mathcal{P}(X) \; \sigma}$-algebra, ekkor: $(X, \mathcal{M}, \mu)$ teljes mértéktér.


### Lebesque mérték

Legyen $X = \R^n, \; \mathcal{A} = $ téglatér és $\alpha$ a térfogat mérték, ekkor a $\varphi_\alpha$ külső mérték a Lebesque-mérték $\lambda_n$.

### Lebesque-mérhető halmazok

Egy $H \sube \R^n$ halmaz Lebesque-mérhető, ha $\forall A \sube \R^n$-re: $\lambda_n(A) = \lambda_n(A \cap H) + \lambda_n(A \setminus H)$. Jelölése: $\mathcal{L}_p$ a Lebesque-mérhető $\sigma$-algebra.

### Lebesque-Stieljes mérték

Legyen $f: \R \rarr \R$ monoton növekvő és jobbról folytonos, ekkor a $\mu_f((a,b]) = f(b) - f(a)$ definiál egy félgyűrű mértéket a téglatéren. Ebből kiterjeszthető egy teljes mértéktérre, ez a Lebesque-Stieljes mérték. Jelölése: $\mu_f$.

## IV. Riemann-, Riemann-Stieljes integrál, modern kontextusban. Mértéktartó leképezések

### Riemann integrál

### Riemann-Stieljes integrál

### Mértéktartó leképezések

$(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha:

 $\forall B \in \mathcal{N}: f^{-1}(B) \in \mathcal{M}$ és $\mu(f^{-1}(B)) = \nu(B)$

 Tulajdonságok:
- Legyen $h: Y \rarr \R$, és $f: X \rarr Y$ mértéktartó, ha $\int_x h \; d\mu = \int_y h \; d\nu$
- $(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha $h: Y \rarr \R$ mérhető, akkor $h \circ f: X \rarr \R$ is mérhető és $\int_X h \circ f \; d\mu = \int_Y h \; d\nu$



## V. Előjeles mértékek és variációik, felbontások


## VI. Abszolút folytonos és szinguláris mértékek, Lebesque-felbontás, Radon-Nikodym tétel, mértékek differenciálása


## VII. Korlátos változású, absz folyt. és szinguláris függvények, felbontásuk, differenciálásuk


## VIII. Mértékek szorzata



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

$x: \Omega \rarr \R$ valamilyen eseménytérből $(\mathcal{X}, B)$ mérhető térbe képező mérhető függvény.

### Val. változó eloszlása

Egy mérték $Q_x(B) = P(X^{-1}(B))$ mértéktartó transzformáció x-szerinti ősképének valószínűsége, $B \in \mathcal{B}$.
- Mértéktartó az eloszlás, így $(\mathcal{X}, \mathcal{B}, Q_x)$ mértéktér lesz, sőt valószínűségi tér.
- $Q_x(X) = P(X^{-1}(\mathcal{X})) = P(\Omega) \Rarr$ a mértéktér inverze a valószínűségi tér 

#### Mértékterek szorzata és annak mérhetősége

Több változót összeszorozva is val. változót kapunk. Eloszlása mértékteret alkot, hiszen mértéktereket tudunk szorozni.

$(\Omega_i, \mathcal{A}_i, P_i)$ ahol $i \in I$-re $X_i: \Omega_i \rarr (\mathcal{X}_i, B_i) \quad (\Omega, \mathcal{A}, P) = \prod_{i = I} (\Omega_i, \mathcal{A}_i, P_i)$

$(\mathcal{X}, B) = \prod_{i \in I} (\mathcal{X}_i, B_i) \rarr$ csak a téglatér $X=(x_1 \times x_2 \times ...) \quad \Omega \rarr X$

$X$ mérhető $\iff \forall i$-re $X_i$ mérhető. 

#### Margináns

$X: \Omega \rarr \mathcal{X}$ val. változóból váltva, $X_i$ val. változó lesz $X$ marginálisa.

- Szorzattérbe képez ~ peremeloszlás

- Több változónál $x_i = \pi_i \cdot x$ függvény $x$ marginálisa, $Q_{x_i}$ marginális eloszlása. 

### Eloszlásfüggvények

$F_x$ meghatározza $Q_x$-et.

Valós eset: $x \in \R^n$

- $n=1$ esetén:
    - $Q_x$ meghatározásához elég $Q_x((-\infty, t)) = P(X \lt t) \coloneqq F_x(t) \rarr$ eloszlásfüggvény a $t$ helyen
- $n \gt 1$ esetén:
    - $Q_x((-\infty, t_1) \times (-\infty, t_2) \times ... \times (-\infty, t_n)) = P(x_1 < t_1, ... , x_n < t_n) \coloneqq F_x(t_1, ..., t_n)$

**Tulajdonságok:**

Minden ilyen tulajdonságú függvény eloszlásfüggvény:

- $n=1$ esetén:
    - Monoton növő $\Rarr$ nagyobb halmaznak nagyobb vagy egyenlő a mértéke
    - $\lim\limits_{x \rarr -\infty} F_x(x) = 0, \; \lim\limits_{x \rarr \infty} F_x(x) = 1$
    - Balról folytonos

- $n \gt 1$ esetén:
    - Monoton növő mindegyik koordinátában (változóban)
    - $\lim\limits_{min(x_i) \rarr -\infty} F_x(\underline x) = 0, \; \lim\limits_{min(x_i) \rarr \infty} F_x(\underline x) = 1$
    - Balról folytonos mindegyik változójában
    - $\forall \underline a \lt \underline b \isin \R^n$-re (azaz minden koordinátában veszünk egyet, ami nagyobb, mint a másik):
        - $\sum_{\epsilon \isin \{ 0,1\}^n } (-1)^{1-\sum \epsilon_i} \cdot F_x(\epsilon \underline b + (1-\epsilon) \underline a) \ge 0$ = szita formula

### Sűrűségfüggvények

$x$ változó $x: \Omega \rarr X$ $\mu$-re $x$ által indukált Q_x mérték absz. folytonos $x \ll \mu$, ($\mu \; \sigma$-véges és $(X,\mathcal{B}, \mu)$ mértéktér) ha $Q_x \ll \mu$, ekkor a sűrűségfüggvény a Radon-Nikodym derivált:

$
    f_x = \frac{dQ_x}{d\mu}
$

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

Legyne $h: \mathcal{X} \rarr Y, \; g: \mathcal{X} \rarr \R^n$ mérhető és $g$ mérhető a $h$ által generált $\sigma$-algebrára. Ekkor létezik: $l: Y \rarr \R^n$ mérhető függvény úgy, hogy $g = l \circ h$.

- Ez az $l$ függvény összeköti a $g$-t és $h$-t, úgy megy tovább $Y$-ból $\R^{n}$-be, hogy megkapjuk $g$-t
- Felhasználása: $f_x^h = \frac{dQ_x \mid_{\sigma(h)}}{d\mu \mid_{\sigma(h)}} \Rarr$ vagyis megszorítjuk a mértéket az adott $\sigma$-algebrára.


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
Legyenek $x = (x_1, ... , x_n): \Omega \rarr \R \;$ $n$ dimenziós val. változók, ekkor:

- $x_1, ..., x_n$ független val. változók
- $X$ eloszlásfüggvénye a marginális eloszlásfüggvények szorzata: $F_x(t_1, ..., t_n) = \prod_i F_{x_i}(t_i)$
- $Q_x = \prod_i Q_{x_i}$, vagyis az eloszlás, mint mérték előáll a maginális eloszlások szorzatmértékéből

**Abszolút folytonos esetben:**

T.f.h. $X$ absz. folyt., ekkor $f_x(t_1, ..., t_n) \Rarr \prod_i f_{x_i}(t_i)$

**Csoportosított függetlenség:**

Több $\sigma$-algebra diszjunkt halmazokba csoportosítva is függetlenek maradnak.

### Kolgomorov 0-1 törvény

Legyen $\mathcal{F_1}, \mathcal{F_2}, ...$ független $\sigma$-algebrák és $g_n = \sigma(\mathcal{F_n}, \mathcal{F_{n+1}}, ...)$, akkor a csoporttosított függetlenség miatt $g_n$ is független az $\mathcal{F}$-ektől.

Legyen $B \isin \cap_{n=1}^{\infty} g_n$ esemény, ekkor $P(B) = 0$ vagy $1$, azaz biztos vagy nincs rá esély.

### Borel-Cantelli Lemma

$A_1, ..., A_n \isin \mathcal{A}$ események a $\sigma$-algebrában és $\limsup A_n = \cup\cap A_k$, ekkor
1. $\sum_{n=1}^{\infty} P(A_n) \lt \infty \Rarr P(\limsup A_n) = 0$

    Vagyis 1 valószínűséggel következik be véges sok belőlük.

2. $\sum_{n=1}^{\infty} P(A_n) = \infty $ és függetlenek $\Rarr P(\limsup A_n) = 1$

    Vagyis ha független valószínűségek szummája divergens, akkor 1 valószínűséggel végtelen sok következik be belőle.


### Konvolúció

**$\R$-ben:**

Legyen $x,y: \Omega \rarr \R)$ val. változók és $x+y=z$, ekkor $z$ sűrűségfüggvénye (absz folyt $\lambda$-ra):

$f_{x+y}(z) = \int_{-\infty}^{\infty} f_x(t) \cdot f_y(z-t) d\lambda(t)$

Ha nem absz. folyt, akkor csal az eloszlásfüggvényt lehet megadni, mint Lebesque-Stieljes integrál:

$F_{x+y}(z) = \int_{-\infty}^{\infty} F_x(z-t) dF_y(t)$

Z eloszlása: $Q_z = Q_x \times Q_y \Rarr$ a két eloszlás konvolúciója

**$\R^n$-ben:**

Legyenek Legyen $\underline x, \underline y: \Omega \rarr \R^n$ val. változók és $\underline x+ \underline y=\underline z$:

- absz. folyt. esetben: $f_z(\underline z) = \int_{\R^n} f_x(\underline t) \cdot f_y(\underline z - \underline t) \; d\lambda_n(t)$

- nem absz. folyt. esetben: $F_z(\underline z) = \int_{\R^n} F_x(\underline z - \underline t) \; dF_y(\underline t)$


## III. Várható érték, magasabb momentumok, kapcsolódó egyenlőtlenségek

### Várható érték

$x: \Omega \rarr \R$ esetén $\mathbb{E}(x) = \int_\R x \; dQ_x = \int_\Omega X \; dP$

- $x: \Omega \rarr \R^{n \times m} \quad (X:\Omega \rarr \R)$ esetben elemenként számoljuk a várható értéket
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

Legyen $\underline X = (X_1, X_2, ..., X_n): \Omega \rarr \R^n$ valószínűségi változó, akkor a kovariancia mátrix:

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

Legyen $\mathbb{E}(X)$ létező várható értékű valószínűségi változó és $f: \R \rarr \R$ konvex függvény, akkor:

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

- monoton konvergencia tétel: Ha $X_n \xrightarrow{n \rarr \infty} X$ és $X_n \le X_{n+1}\; \forall n$, akkor $\lim\limits_{n \rarr \infty} \mathbb{E}(X_n) = \mathbb{E}(X)$
- Fatou-lemma: $X_n \ge 0$ valószínűségi változók, akkor $\mathbb{E}(\liminf\limits_{n \rarr \infty} X_n) \le \liminf\limits_{n \rarr \infty} \mathbb{E}(X_n)$
- Lebesuqe-dominált konvergencia tétel: Ha $X_n \xrightarrow{1 \; p.} X$ és létezik olyan $Y$ valószínűségi változó, hogy $\forall n: \vert X_n \vert \le Y$ és $\mathbb{E}(Y) \lt \infty$, akkor $\lim\limits_{n \rarr \infty} \mathbb{E}(X_n) = \mathbb{E}(X)$

**1 valószínűséggel konvergencia:**

$X_n \xrightarrow{1 \; p.} X \iff P(\{ \omega \in \Omega: \lim\limits_{n \rarr \infty} X_n(\omega) = X(\omega) \}) = 1$

**L_p-beli konvergencia:**

$X_n \xrightarrow{L_p} X \iff \lim\limits_{n \rarr \infty} \mathbb{E}(\vert X_n - X \vert^p) = 0$

**Sztochasztikus konvergencia:**

$X_n \xrightarrow{sztoch.} X \iff \forall \epsilon > 0: \lim\limits_{n \rarr \infty} P(\vert X_n - X \vert \ge \epsilon) = 0$


**Kapcsolatok:**
- $X_n \xrightarrow{1 \; p.} X \Rarr X_n \xrightarrow{sztoch.} X$
- $X_n \xrightarrow{L_p} X \Rarr X_n \xrightarrow{sztoch.} X$
- $X_n \xrightarrow{L_p} X \Rarr X_n \xrightarrow{L_q} X, \quad p \ge q \ge 1$

**Riesz-lemma:**

Ha $X_n \xrightarrow{sztoch.} X$, akkor létezik olyan részhalmaz $X_{n_k}$, hogy $X_{n_k} \xrightarrow{1 \; p.} X$.

**Egyenletes integrálhatóság:**

Legyen $X \isin L_1 \; \mathbb{E}(\vert x \vert) \lt \infty \; H \subset L_1(P)$, $H$ egyeneletesen integrálható, ha:

$\sup \int\limits_{x \isin H \, \{ x \gt c\}} \vert x \vert dP \xmapsto{x \rarr \infty} 0$

Átfogalmazva $H$ egyenletesen integrálható, ha $\mathbb{E}(x) \lt \infty$ és kicsi halmazokon egy korláton belül marad az integrál értéke.

L_p-beli konvergencia ekvivalens azzal, hogy sztochasztikusan konvergál és $\forall \; \vert x_n \vert^p$ képzett halmaz egyenletesen integrálható.

**Vallée-Poussin tétel:**

Egy $H \subset L_1(P)$ halmaz egyenletesen integrálható, ha:

$\lim\limits_{x \rarr \infty} \frac{f(x)}{x} = \infty$ és $\sup\limits_{x \in H} \mathbb{E}(f(\vert x \vert)) \lt \infty$.

Vagyis létezik olyan növekvő függvény, ami gyorsabban nő, mint az identitás($x$) és a halmaz elemeinek képeire vett várható értékek korlátosak.

**Scheffé állítás:**

Legyen $x_n \ge 0$ és $X_n \rarr X$ 1 valószínűséggel, valamint $\mathbb{E}(X_n) \rarr \mathbb{E}(X)$, akkor $X_n \xrightarrow{L_1} X$.

## V. Valószínűségi változók gyenge és eloszlásbeli konvergenciája, karakterisztikus függvény



## VI. Nagy számok gyenge és erős törvényei, független sorok


## VII. Centrális határeloszlás tétel változatai


## VIII. Feltételes várható érték és tulajdonságai, feltételes eloszlás


## IX. Martingálok tulajdonságai, Doob-felbontás, kanonikus növekvő folyamata, megállás idő


## X. Martingálok konvergancia tételei, nagy-eltérés tételek


# Statisztika

Órai videók:
- [Kilencedik előadás](https://youtu.be/fDVl9W8NtyM?si=P8GizxJ7fuxF4T4Y)
- [Tizedik előadás](https://youtu.be/QvnxFoF7Vi0?si=rsakZAkJHmbU3j0_)
- [Tizenegyedik előadás](https://youtu.be/wngnbELDnmg?si=_0GUgF7eteBHSMXc)
- [Tizenkettedik előadás](https://youtu.be/KYoly4FVF3E?si=AAWg8H28boo8hO6Y)


## I. Statisztikai mező, alapfogalmak. Tapasztalati becslések

### Statisztikai mező

$(\Omega, \mathcal{A}, \mathcal{P})$ a mérhető tér ugyan az, mint korábban (azaz $(\Omega, \mathcal{A}, P)$), azonban itt $\mathcal{P}$ egy halmaznyi mérték, valószínűségi mértékek egy családja.
- Több valószínűség van, ahol $\forall P \isin \mathcal{P}$ valószínűségi mezőt kapunk.
- $\mathcal{P} \sube \mathcal{M}_0 = $ { $P$ valószínűségi mérték $(\Omega, \mathcal{A})$-n$ }.

### Paraméter

Paraméterezve a halmaznyi mérték: $P \isin \{ \mathcal{P}_\vartheta: \vartheta \isin \Theta \}$, ahol $\Theta$ a paramétertér és $\vartheta$ a paraméter.

### Statisztikai minta és eloszlása

$x: (\Omega, \mathcal{A}, \mathcal{P}) \rarr (\mathcal{X}, \mathcal{B})$ (azaz a statisztikai mező teréből képez mérhető térbe) mérhető függvényt mintának hívunk.

- A minta eloszlása egy $P \isin \mathcal{P}$ mellett $Q = P \circ X^{-1}$
- $(\mathcal{X},\mathcal{B},\mathcal{Q})$ is statisztikai mező lesz
- Sok esetben: $x = (x_1, x_2, ..., x_n)$ FAE

### Statisztika

$T: \mathcal{X} \rarr \mathcal{Y}$ minta teréből valamilyen mérhető térbe $(\mathcal{Y},\mathcal{C})$ képezést statisztikának nevezünk. Ez a mintaelemek mérhető függvénye, lényege, hogy kiszámolunk valamit az adatokból.

$T(x): \Omega \xrightarrow{\mathcal{X}} \mathcal{Y}$

- Mintaátlag
    - $\overline x = \frac{x_1 + x_2 + ... + x_n}{n}$
- Rendezett minta
    - $(x_1^*, ..., x_n^* \quad x_i^* \le x_{i+1}^*)$
- Mid-range
    - $\frac{x_n^* - x_1^*}{2}$
- Tapasztalati medián
    $
        m(x) =
        \begin{cases}
            x_{k+1}^* & n = 2k+1 \\
            \frac{x_{k}^*+x_{k+1}^*}{2} & n=2k
        \end{cases}
    $

### Tapasztalati eloszlás

Az eloszlást is csak mintából ismerjük, $Q_n^*$ mértéket keressük $(\mathcal{X}, \mathcal{B})$-n, tetszőleges $B \isin \mathcal{B}$-ra:

$
Q_n^*(B) = \frac{1}{n} \sum_{i=1}^{n} \chi_B(x_i) = \frac{1}{n} \sum_{i=1}^{n} 
$

Ahol:
- $Q_n^*(B)$: véletlen mérték, hiszen a minta eloszlása is végtelen
- $\chi_B(x_i)$: $x_i \isin B$ indikátor
- $\delta_{x_i}(B)$: pontmértékek az $x_i$ pontra koncentrálódva

Tulajdonságok:
- $\mathbb{E}[Q_q^*](B) = Q(B) \Rarr Q_n^*(B) \rarr Q(B)$ 1 valószínűséggel a mintanagyság növelésével
- $\mathrm{Var}(Q_n^*(B)) = \frac{1}{n} Q(B)(1-Q(B))$
- Normálás: $\sqrt{n} (Q_n^*(B)-Q(B)) \rarr N(0, Q(B)(1-Q(B))$ eloszlásban

### Tapasztalati becslések

Egy $\Psi(Q)$ függvény becslésének mondjuk $\hat \Psi(Q) \coloneqq \Psi(Q_n^*)$-t.
- Várható érték, $\Psi(Q) = \int_{\R} x dQ$
    - $\Psi(Q_n^*) = \int_{\R} x dQ_n^* = \frac{1}{n} \sum_{i=1}^n x_i = \overline x$
- Variancia
    - $\Psi(Q) = \int_{\R} x^2 dQ_n^* = (\int_{\R} x dQ_n^*)^2 = \frac{1}{n} [\sum_{i=1}^n x_i^2 - (\sum_{i=1}^n x_i)^2] = \frac{1}{n} \sum_{i=1}^n (x_i-\overline x)^2  = S_n^2(x)$
    - Korrigált tapasztalati szórásnégyzet: $S_n^{*2} = \frac{1}{n-1} \sum_{i=1}^n (x_i-\overline x)^2$

### Tapasztalati eloszlásfüggvény

Növekvő sorba rendezett mintából:

$
    F_n^*(t) =
    \begin{cases}
        0 & t\le x_1^*, \\
        \frac{1}{n} & x_i^* \lt t \le x_{i+1}^* \\
        1 & x_n^* \lt t
    \end{cases}
$

- Balról folytonos, magasabb dimben is
- $\lim\limits_{x \rarr -\infty} F_n^*(x) = 0, \; \lim\limits_{x \rarr \infty} F_n^*(x) = 1$
- $F_n^*(t) = Q_n^*((-\infty, t))$ egydim esetben


### Glivenko-Cantinelli tétel

Ha $\xi_1, ..., \xi_n$ független minta, akkor $n \rarr \infty$-vel:

$\sup \mid F_n^*(t) - F(t) \mid \rarr 0$,  1 valószínűséggel.

Azaz a tapasztalati eloszlás és az elvi eloszlást különbsége a nullához tart a minta növelésével. 

Nem csak egyetlen t-re, hanem egyenletesen tart az általunk megfigyelt minta alapján képzett függvény az elvi eloszláshoz.

## II. Dominált statisztikai mező, elégséges statisztikák

### Domináló mérték

Ha van egy $\mu \; \sigma$-véges mérték, hogy $\forall P \isin \mathcal{P}$-re: $P \ll \mu$ absz. folyt. akkor az a mérték dominálja a statisztikai mezőt. Az erős feltétel, hogy mind ugyan arra legyen absz. folytonos.  

### Mértékek, mértékosztályok ekvivalenciája

- $P$ és $Q$ mérték ekvivalens ($P \backsim Q$), ha $P \ll Q$ és $Q \ll P$
    
    Azaz $\forall B$ mérhető halmazra: $P(B) = 0 \Longleftrightarrow Q(B) = 0$, vagyis ugyan azok a nullmértékű halmazok mindkét mérték szerint

- $\mathcal{P}$ és $\mathcal{Q}$ mértékosztályok ekvivalensek, ha bennük minden mérték ekvivalens
    
    Azaz $\forall B$ mérhető halmazra: $\forall P \isin \mathcal{P} \;P(B) = 0 \Longleftrightarrow \forall Q \isin \mathcal{Q} \; Q(B) = 0$

### Halmos-Savage tétel

$\mathcal{P}$ mértékosztályra ekvivalensek:
- $\mathcal{P}$ dominált
- $\mathcal{P}$ megszámlálható
- A domináló $\mu$ előállítható $P_1, P_2, ... \isin \mathcal{P}$ lineáris kombinációjaként

### Elégséges statisztika

$T$-statisztika elégséges, ha $P_{\vartheta}(x \isin B \mid T)$ feltételes eloszlások $\vartheta$-tól nem függenek.

- elég egy paramétert megtartani

### Neyman-Fisher faktorizációs tétel

Paraméteres dominált statisztikai mezőn, ahol $P_{\vartheta}$ sűrűségfüggvénye $f_{\vartheta}$, a következők ekvivalensek $T$-re:

- $T$ elégséges statisztika

- Létezik $P$ lineáris kombinációjaként előállított $\mu$:
    
    $f_{\vartheta}(x) = g_{\vartheta}​(T(x)) h(x)$, ahol $g_{\vartheta}$ csak $T$-n keresztül függ $x$-től és $h(x)$ nem függ $\vartheta$-tól.

### Minimálisan elégséges statisztika

$T$-statisztika akkor minimálisan elégséges, ha minden $S$ elégséges statisztikára, azaz előáll bármilyen elégséges statisztika függvényeként.

### Hányadoskritérium

Legyen $S$ statisztika, $x,y$ minta. $S$ pontosan akkor elégséges, ha:

$S(x) = S(y) \Rarr \frac{f_{\vartheta}(x)}{f_{\vartheta}(y)}$ nem függ $\vartheta$-tól $\mu \times \mu$ domináló szorzatmérték szerint.

Legyen $S$ statisztika, $x,y$ minta. $S$ pontosan akkor minimálisan elégséges, ha:

$S(x) = S(y) \Longleftrightarrow \frac{f_{\vartheta}(x)}{f_{\vartheta}(y)}$ nem függ $\vartheta$-tól $\mu \times \mu$ domináló szorzatmérték és $(x,y) \isin \mathcal{X}^2$ szerint.



## III. Többdimenziós norm. eloszlás, nemcentrális Khi-négyzet eloszlás

### Többdimenziós normális eloszlás

Legyen $\underline X = (X_1, X_2, ..., X_n): \Omega \rarr \R^n$ valószínűségi változó, akkor $\underline X$ többdimenziós normális eloszlású, ha minden $\underline a \in \R^n$-re az egydimenziós valószínűségi változó $\underline a^T \cdot \underline X$ normális eloszlású.

#### Sűrűségfüggvény

T.f.h. $\underline X \sim N_n(\underline \mu, \Sigma)$, ahol $\underline \mu = \mathbb{E}(\underline X) \in \R^n$ és $\Sigma = \mathrm{Cov}(\underline X)$ pozitív szemidefinit mátrix, akkor $\underline X$ sűrűségfüggvénye:

$f_(\underline x) = (2\pi)^{-\frac{n}{2} \cdot e^{-\frac{\sum_{i=1}^n x_i^2}{2}}}$

**Tulajdonságok**:
- $\underline X$ komponensei függetlenek $\iff \Sigma$ diagonális mátrix
- gömbszimmetrikus eloszlás: elég tudni, hogy x milyen távol van a középponttól
- alap forma: $f(x) = \frac{1}{\sigma \sqrt{2\pi}} \cdot e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
- alap std. norm. forma: $f(x) = \frac{1}{\sqrt{2\pi}} \cdot e^{-\frac{x^2}{2}}$

**Lineáris transzformációk:**

Legyen x n-dimen std. norm. eloszlású, $A \isin \R^{k \times n}, m \isin \R^k$, akkor $y = A \cdot x + m$ k-dimenziós eloszlású. Ekkor $y \sim N_k(m, A \cdot A^T)$

- Ha $A$ nem-elfajuló mátrix, akkor absz. folyt. a $k$-dimenziós Lebesque mértékre és sűrűségfüggvénye megadható a várható érték és a kovariancia mátrix segítségével: $f_y(y) = \frac{1}{(2\pi)^{\frac{k}{2}} \cdot det(\Sigma)^{\frac{1}{2}}} \cdot e^{-\frac{1}{2} (y-m)^T \cdot (\Sigma)^{-1} \cdot (y-m)}$

- $B \isin \R^{\mathcal{l} \ times n}, \; n \isin \R^{\mathcal{l}}$, akkor $z = B \cdot y + n$ is $\mathcal{l}$-dimenziós normális eloszlású, $z \sim N_{\mathcal{l}}(B \cdot m + n, B \cdot A \cdot A^T \cdot B^T)$

- Ha $\underline y \isin \R^2$ vektort két részre bontjuk: $\underline y = \begin{bmatrix} \underline y_1 \\ \underline y_2 \end{bmatrix}$, akkor $\underline y_1$ és $\underline y_2$ is normális eloszlású, továbbá függetlenek, ha a kovariancia mátrixukban a megfelelő helyeken 0 szerepel.

#### Függetlenség

Legyen $\underline y \isin \R^2$ vektort két részre bontjuk: $\underline y = \begin{bmatrix} \underline y_1 \\ \underline y_2 \end{bmatrix}$, akkor $\underline y_1$ és $\underline y_2$-ra a kovariancia mátrix $2\times 2$ blokkmátrix lesz:

$ \Sigma = \begin{bmatrix}
\Sigma_{11} & \Sigma_{12} \\
\Sigma_{21} & \Sigma_{22}
\end{bmatrix} $

Amennyiben $\underline y$ normális eloszlásű volt, úgy $\Sigma_{12} = \Sigma_{21} = 0$, akkor $\underline y_1$ és $\underline y_2$ függetlenek. A nulla kovariancia szükséges és elégséges feltétel a függetlenségre, ha egy $\underline y$-ból jönnek. Fordítva nem igaz, hogy nulla kovariancia esetén függetlenek lennének.

**Két független normális eloszl. kovariancia mátrixa:**

Legyen $\underline y = N(m, \Sigma)$ esetén:

$ Ay + b $ és $ Cy + d $ függetlenek $\Longleftrightarrow A \cdot \Sigma \cdot C^T = 0$

**Szingularitás esetén:**

Ha $\Sigma$ nem szinguláris $\underline y = \begin{bmatrix} \underline y_1 \\ \underline y_2 \end{bmatrix}$-ra, akkor $\underline y_1$ és $\underline y_2$ függetlenek $\iff \Sigma_{12} = \Sigma_{21} = 0$

**Feltételes eloszlás:**

Legyen $\underline y = \begin{bmatrix} \underline y_1 \\ \underline y_2 \end{bmatrix} \sim N(m, \Sigma)$, ahol

$P(y_1 \mid y_2) \sim N(m_{1|2}, \Sigma_{1|2})$ továbbra is normális eloszlású és a feltételes várható érték megadható a kovariancia mátrix segítségével:

$m_{1|2} = m_1 + \Sigma_{12} \cdot \Sigma_{22}^{-1} \cdot (y_2 - m_2) \Rarr$ a várható érték lineáris függvénye a feltételnek

$\Sigma_{1|2} = \Sigma_{11} - \Sigma_{12} \cdot \Sigma_{22}^{-1} \cdot \Sigma_{21} \Rarr$ a kovariancia mátrix nem függ a feltételtől

### Nemcentrális Khi-négyzet eloszlás

Legyenek $X_1, X_2, ..., X_n$ független normális eloszlású valószínűségi változók, ahol $X_i \sim N(0,1)$, akkor a következő valószínűségi változó nemcentrális Khi-négyzet eloszlású:

$\sum_{j = 1}^n x_j^2 = \Vert x \Vert^2$ n szabadságfokú $\chi^2$ eloszlású.

$ \Vert \underline u \Vert_2 = \sqrt{\sum_{i=1}^n u_i^2}$ 2-es norma, ha $\underline u \isin \R^n$.

Ha $\underline Y \sim N(m, Id) \Rarr \Vert \underline Y \Vert_2^2$ eloszlása csak $\Vert m \Vert_2^2$-től függ, azaz a várható érték vektortól, ez a $\lambda$ paraméter a nemcentrálisitás paramétere.

**Ortogonális felbontás alterekre**

Legyen $\underline x \sim N_n(m, \sigma^2 Id),\; \R^n = L_1 \oplus L_2 \oplus ... \oplus L_k, \; \dim L_i = r_i$  (ortogonális felbontás alterekre), akkor: $P_i$ vetítés mátrixa $L_i$-re, $\; \underline x_i = P_i\underline x,\; \underline m_i = P_i \underline m$

Ebből következik, hogy:
$ \underline x_i \sim N_{ri}(\underline m_i, \sigma^2 P_i)$ és $\Vert x_i \Vert_2^2 \sim \sigma^2 x_{ri}^2 [\frac{\Vert \underline m_i \Vert^2}{\sigma^2}]$

**Nem-szingularitás esetén:**

Ha $\Sigma$ nem szinguláris, akkor $\underline X \sim N_n(m, \Sigma)$ esetén:

$\underline x^T \cdot \Sigma^{-1} \cdot \underline x \sim \chi_n^2[\underline m^T \cdot \Sigma^{-1} \cdot \underline m]$

## IV. Becslések elmélete, Blackwell-izálás


## V. Fisher-információ és regularitás-feltételek


## VI. Információs határ, MM és ML módszerek


## VII. Hipotézisvizsgálat alapjai, likelihood-hányados próba egyszerű hipotéziseknél


## VIII. Normális eloszlás paramétereire vonatkozó próbák


## IX. Khi-négyzet próbák illeszkedésvizsgálatra és következményeik. Folytonos illeszkedésvizsgálat


## X. Lineáris modell, Lineáris hipotézis normális lineáris modellben

