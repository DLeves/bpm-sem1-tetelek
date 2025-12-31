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
    - $a \in \mathcal{A} \mapsto \mathcal{A^c} := X \setminus A \in \mathcal{A}$
    - $\mathcal{A_i} \in \mathcal{A}, i \in \N \mapsto \cup_{i=1}^{\infty} \mathcal{A_i} \in \mathcal{A}$
- **Generált $\sigma$-algebra**: Tetszőleges $\mathcal{U}$ rendszerhez $\exists$ egy legszűkebb $\sigma$-algebra ami tartalmazza $\mathcal{U}$-t, jelölés: $\sigma(\mathcal{U})$
- **Borel $\sigma$-algebra**: A legkisebb $\sigma$-algebra, ami tartalmaz minden nyílt halmazt. Legyen $(X,\tau)$ topologikus tér, ekkor $B(X):= \sigma(\tau)$

### Halmazfüggvények

$\alpha: \mathcal{A} \mapsto \R$ halmazfüggvény, feltevések:
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

Adott $(X, \mathcal{M})$ és $(Y, \mathcal{N})$ mérhető terek, az $f: X \mapsto Y (\mathcal{M}, \mathcal{N})$ mérhető leképezés. Ekkor $\{ A \subset Y: f^{-1}(A) \in \mathcal{M} \}$ az halmazrendszer $\sigma$-algebra $Y$-on.

Generált alterekkel tulajdonság:

$U \subset \mathcal{P}(Y) \; \forall u \isin U: f^{-1}(u) \isin M$
- $\forall u \isin \sigma(U)$-ra is $\mapsto$ a generált altér is a $\sigma$-algebrában van
- elég a generált alteret nézni, hogy mérhető-e 1-1 helyen, nem kell a teljeset

### Egyszerű függvények

Legyen $(X, \mathcal{M})$ mérhető tér, ekkor az $f: x \mapsto \R$ leképezést egyszerű függvénynek nevezzük, ha mérhető és értékkészlete véges. Ha $f,g$ egyszerű függvény, akkor $f+g$, $f \cdot g$, $max(f,g)$, $min(f,g)$ is egyszerű függvény, így mérhető is.

Az egyszerű függvény előáll $f= \sum_{i=1}^{k} c_i \chi_{A_i}$-ból, ahol
- $c_i$ a súlyozás
- $\chi_{A_i}$ indikátorfüggvény

**Egyenletes konvergencia**: Legyen $f: X \mapsto \overline\R$ mérhető, ekkor megadható $f_i$ egyszerű függvények sorozata úgy, hogy 
- monoton nőnek
- $f_i \mapsto f$
- $\{ x: f(x) \lt a\}$-n egyenletesen konvergens

**Suprémum és infinimum**:
$f_n: X \mapsto \overline \R$ mérhető $\mapsto \sup f_n, \inf f_n, \lim\sup f_n, \lim\sup f_n$ is mérhetők
- $\sup f_n$: a függvény legmagasabb értéke az adott pontban
- $\lim\sup f_n$: a legmagasabb érték, amit elér a függvény, ahogy halad $\infty$ felé

Infinimum hasonlóan, csak legkisebb értékkel.

### Mérték

Legyen (X, \mathcal{M}) mérhető tér, a $\mu: \mathcal{M} \mapsto \overline\R$ leképezést mértéknek nevezzük, ha
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
- Ami nem más, mint a $c_k$ magasságokkal az $A_k$ hosszok szorozva $\mapsto$ terület

**Megjegyzések**:

Adott $0 \le g \le f$ mérhető függvények és $A \subset B$ halmazok, ekkor

- $\int_A g \, d\mu \le \int_A f \, d\mu \le \int_B g \, d\mu$

- $g \mid_A \equiv c$ (konstans) esetén $\int_A f \; d\mu = c \cdot \mu(A)$ (megj: $g \mid_A$ a $g$ függvény megszorítva $A$ pontra/környezetére)

- $\mu(A) = 0 \mapsto \int_A f \; d\mu = 0$, vagyis üres halmazon integrálva nullát kapunk

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

Legyen $0 \le f_1 \le ... \le f_n$ m.m. monoton növekvő, $\lim_{n \mapsto \infty} f_n = f$ pontonként konvergáló, mérhető függvénysorozat.

Ekkor az inegrál is konvergál $\lim_{n \mapsto \infty} \int_X f_n \; d\mu = \int_x f \; d\mu$ 

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

$f_n$ mérhető és $\mid f_n \mid \le g, \quad g \isin L_1$, ekkor $f_n \mapsto f$, valamint:

$\int_X f \; d\mu = lim \int_x f_n \; d\mu$

Ha a két fv m.m. megegyezik, akkor az integráljuk is. Ilyenkor $g$ majorálja (dominálja) $\mid f_n \mid$-et, vagyis felettük helyezkedik el. 

**The Bright Side of Mathematics vidik**: 
- [Lebesque integrál](https://www.youtube.com/watch?v=TG67nsccqeQ&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=6)
- [Riemann integrál vs. Lebesgue integrál](https://www.youtube.com/watch?v=PGPZ0P1PJfw&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=24)
- [Monton konvergencia tétel](https://www.youtube.com/watch?v=1tzaUiZJXm8&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=7)
- [Lebesque-dominált konvergencia](https://www.youtube.com/watch?v=eu-6_wpTE-A&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=10)

## III. Mértékek kiterjesztése. Lebesque- és Lebesque-Stieljes mérték

### Külső mértékek

$\alpha$ külső mérték: $\mathcal{A} \sube \mathcal{P}(X)$ halmazrendszeren, $\alpha(\empty) = 0$ és $\alpha \ge 0$, $\alpha: \mathcal{A} \mapsto \overline \R$. $A_1, A_2, ... \in \mathcal{A}$ halmazokra $\alpha(\cup_{i=1}^{\infty} A_i) \le \sum_{i=1}^{\infty} \alpha(A_i)$

$\empty \isin \mathcal{A} \sube \mathcal{P}(X), \; \alpha \ge 0$-ra:
$\varphi_\alpha(H) = \inf \{ \sum \alpha(A_i) \mid \cup A_i \gt H_i ; A_i \isin \mathcal{A}\}$

Legyen $\mathcal{l}_\alpha$ egy külső mérték $\mathcal{P(X)}$-en, ha $\alpha$ egy külső mérték az $\mathcal{A}: \varphi_\alpha \mid \mathcal{A} = \alpha$-n.

Legyen $\mathcal{M}_{\varphi_\alpha \subset \mathcal{P}(X) \; \sigma}$-algebra, ekkor: $(X, \mathcal{M}, \mu)$ teljes mértéktér.


### Lebesque mérték

Legyen $X = \R^n, \; \mathcal{A} = $ téglatér és $\alpha$ a térfogat mérték, ekkor a $\varphi_\alpha$ külső mérték a Lebesque-mérték $\lambda_n$.

### Lebesque-mérhető halmazok

Egy $H \sube \R^n$ halmaz Lebesque-mérhető, ha $\forall A \sube \R^n$-re: $\lambda_n(A) = \lambda_n(A \cap H) + \lambda_n(A \setminus H)$. Jelölése: $\mathcal{L}_p$ a Lebesque-mérhető $\sigma$-algebra.

### Lebesque-Stieljes mérték

Legyen $f: \R \mapsto \R$ monoton növekvő és jobbról folytonos, ekkor a $\mu_f((a,b]) = f(b) - f(a)$ definiál egy félgyűrű mértéket a téglatéren. Ebből kiterjeszthető egy teljes mértéktérre, ez a Lebesque-Stieljes mérték. Jelölése: $\mu_f$.

**The Bright Side of Mathematics vidik**: 
- [Lebesque mérték](https://youtu.be/7O7qPrNIt7w?t=852&si=j4vxLnAO6Dx9XJWC)
- [Lebesque-Stieljes mérték](https://youtu.be/IsmgLGVpLpQ?si=rNoRbBoMjnO0qJ-g)
- [Külső mértékek 1.](https://youtu.be/LC-9KzxVoWI?si=7Q91X0ORbRqdFcav)
- [Külső mértékek 2.](https://youtu.be/e8yg3FtjO5s?si=G4dsGltlNrT0WEwH)
- [Külső mértékek 3.](https://youtu.be/iA6ATJFViUs?si=iWtzaH82o7FhTFRg)

## IV. Riemann-, Riemann-Stieljes integrál, modern kontextusban. Mértéktartó leképezések

### Riemann integrál

Legyen $f: [a,b] \mapsto \R$ korlátos függvény, valamint $P = \{ x_0, x_1, ... , x_n \}$ egy felosztás $[a,b]$-n, ahol $a = x_0 \lt x_1 \lt ... \lt x_n = b$. Ekkor az $i$-edik részintervallumon:

- $m_i = \inf\{ f(x): x \in [x_{i-1}, x_i] \}$
- $M_i = \sup\{ f(x): x \in [x_{i-1}, x_i] \}$
- $\Delta x_i = x_i - x_{i-1}$

Ekkor a felül- és alulösszeg:
- $U(f,P) = \sum_{i=1}^{n} M_i \cdot \Delta x_i$
- $L(f,P) = \sum_{i=1}^{n} m_i \cdot \Delta x_i$

A $f$ függvényt Riemann-integrálhatónak nevezzük, ha $\sup\{ L(f,P): P \}$ = $\inf\{ U(f,P): P \}$. Ekkor az integrál értéke:

$\int_a^b f(x) \; dx = \sup\{ L(f,P): P \} = \inf\{ U(f,P): P \}$

### Riemann-Stieljes integrál

Legyen $f,g: [a,b] \mapsto \R$ korlátos függvények, valamint $P = \{ x_0, x_1, ... , x_n \}$ egy felosztás $[a,b]$-n, ahol $a = x_0 \lt x_1 \lt ... \lt x_n = b$. Ekkor az $i$-edik részintervallumon:

- $m_i = \inf\{ f(x): x \in [x_{i-1}, x_i] \}$
- $M_i = \sup\{ f(x): x \in [x_{i-1}, x_i] \}$
- $\Delta g_i = g(x_i) - g(x_{i-1})$

Ekkor a felül- és alulösszeg:
- $U(f,g,P) = \sum_{i=1}^{n} M_i \cdot \Delta g_i$
- $L(f,g,P) = \sum_{i=1}^{n} m_i \cdot \Delta g_i$

A $f$ függvényt Riemann-Stieljes integrálhatónak nevezzük $g$ szerint, ha $\sup\{ L(f,g,P): P \}$ = $\inf\{ U(f,g,P): P \}$. Ekkor az integrál értéke:

$\int_a^b f(x) \; dg(x) = \sup\{ L(f,g,P): P \} = \inf\{ U(f,g,P): P \}$

### Mértéktartó leképezések

$(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha:

 $\forall B \in \mathcal{N}: f^{-1}(B) \in \mathcal{M}$ és $\mu(f^{-1}(B)) = \nu(B)$

 Tulajdonságok:
- Legyen $h: Y \mapsto \R$, és $f: X \mapsto Y$ mértéktartó, ha $\int_x h \; d\mu = \int_y h \; d\nu$
- $(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha $h: Y \mapsto \R$ mérhető, akkor $h \circ f: X \mapsto \R$ is mérhető és $\int_X h \circ f \; d\mu = \int_Y h \; d\nu$


## V. Előjeles mértékek és variációik, felbontások

### Előjeles mérték

Legyen $(X, \mathcal{M})$ mérhető tér, az $\mu: \mathcal{M} \mapsto \overline \R$ leképezést előjeles mértéknek nevezzük, ha
1. $\mu(\empty) = 0$
2. $\mu \; \sigma$-additív

### Variációk

**Teljes variáció**:

$\mid \mu \mid (A) = \sup \{ \sum_{i=1}^{n} \mid \mu(A_i) \mid \mid A = \cup_{i=1}^{n} A_i, A_i \cap A_j = \empty, A_i \in \mathcal{M} \}$

**Pozitív variáció:**

$\mu^+(A) = \sup \{ \mu(B) \mid B \subset A, B \in \mathcal{M} \}$

**Negatív variáció:**

$\mu^-(A) = -\inf \{ \mu(B) \mid B \subset A, B \in \mathcal{M} \}$

### Jordan-felbontás

$\mu = \mu^+ - \mu^-$ és $\mid \mu \mid = \mu^+ + \mu^-$

Minden mérték előállítható két pozitív mérték különbségeként.

### Hahn-felbontás

Legyen $(X, \mathcal{M}, \mu)$ előjeles mértéktér, ekkor létezik $P, N \in \mathcal{M}$ olyan, hogy
- $P \cup N = X, \; P \cap N = \empty$
- $\forall A \in \mathcal{M}, A \subset P \mapsto \mu(A) \ge 0$
- $\forall A \in \mathcal{M}, A \subset N \mapsto \mu(A) \le 0$


## VI. Abszolút folytonos és szinguláris mértékek, Lebesque-felbontás, Radon-Nikodym tétel, mértékek differenciálása

### Abszolút folytonos és szinguláris mértékek

**Abszolút folytonos mérték**:

$\alpha$ mérték abszolút folytonos $\beta$ mértékhez képest, ha

$\forall A \in \mathcal{M}, \beta(A) = 0 \mapsto \alpha(A) = 0$. Jelölése: $\alpha \ll \beta$

- A halmazok amik 0-ák $\beta$-ra, azok $\alpha$-ra is 0-ák

- Jele: $\alpha \ll \beta$

**Szinguláris mérték**:

$\alpha$ és $\beta$ mérték szingulárisak egymáshoz képest, ha van $X = A \cup B$ diszjunkt halmazok és $\alpha(B) = \beta(A) = 0$. Jelölése: $\alpha \perp \beta$. $A$ csak az $\alpha$-nak, $B$ csak a $\beta$-nak a hordozója.

### Lebesque-felbontási tétel

Adott egy $\nu$ akár előjeles és egy $mu$ hagyományos mérték, mindkettő $\sigma$-additív. Ekkor létezik olyan $\alpha$ és $\beta$ mérték, hogy

- $\nu = \alpha + \beta$ egyértelmű felbontás, ahol 
    - $\alpha \ll \mu$ (absz. folytonos)
    - $\beta \perp \mu$ (szinguláris)

### Radon-Nikodym tétel

Adott $\nu$ előjeles és $\mu$ hagyományos mérték, mindkettő $\sigma$-véges, továbbá $\nu \ll \mu$. Ekkor létezik olyan $f: X \mapsto \overline \R$ mérhető függvény, hogy:

$\nu(A) = \int_A f \; d\mu, \quad \forall A \in \mathcal{M}$

**Radon-Nikodym derivált**:

Az $f$ függvényt a $\nu$ mérték $\mu$ mérték szerinti Radon-Nikodym deriváltjának nevezzük, ha:
- Ha van egy abszolút folytonos mértékünk egy másik mértékhez képest, akkor létezik egy olyan függvény, ami az első mértéket a második mérték integráljaként adja vissza.
- $f$ egy sűrűségfüggvénynek is megfelel

f = $\frac{d\nu}{d\mu}$

Adott $\alpha \ll \beta$ mértékek és $h \isin L_1(\beta)$ és $f = \frac{d\alpha}{d\beta}$, akkor:

$\int_H h \; d\alpha = \int_X h \cdot f \; d\beta = \int_H h \frac{d\alpha}{d\beta} \; d\beta$

**Előjeles mérték szerinti integrálás**:

Adott $\nu \ll \tau$  előjeles mérték, $h \isin L_1(\tau)$ és $f: X \mapsto \overline \R$ mérhető függvény, akkor:

$\int_H h \; d\nu = \int_H h \cdot f \; d\tau = \int_H h \frac{d\nu}{d\tau} \; d\tau$

**Totális variáció:**

$\mid \nu \mid (A) = \int_A \mid \frac{d\nu}{d\tau} \mid \; d\tau$

Legyen $\nu(A)$ előjeles és $\mu \; \sigma$-véges mértékek, $\nu \ll \mu$, ha $\forall \epsilon \gt 0 \; \exists \delta \gt 0$ úgy, hogy $\mu(A) \lt \delta \implies \mid \nu(A) \mid \lt \epsilon$ 


**Alsó és felső derivált:**

- Alsó derivált: $\underline{D}_\mu \nu(x) = \liminf_{r \mapsto 0} \frac{\nu(B(x,r))}{\mu(B(x,r))}$

- Felső derivált: $\overline{D}_\mu \nu(x) = \limsup_{r \mapsto 0} \frac{\nu(B(x,r))}{\mu(B(x,r))}$

Összefüggés:
- $\underline{D}_\mu \nu(x) \le \overline{D}_\mu \nu(x)$
- Ha $\underline{D}_\mu \nu(x) = \overline{D}_\mu \nu(x)$, akkor a közös értéket $\mu$-szer majdnem minden $x$-re $\frac{d\nu}{d\mu}(x)$-nek nevezzük.

Legyen $\nu$ lokálisan véges, előjeles Borel-mérték és van egy $\nu = \int f \; d\mu$ felbontása, ahol $f \in L_1(\mu)$, akkor $\mu$-szer majdnem minden $x$-re:

$\underline{D}_\mu \nu(x) = \overline{D}_\mu \nu(x) = f(x)$

- $\mu$ majdnem minden $x$-re létezik a derivált és az egyenlő $f(x)$-el
- $D_\mu \nu(x) = f(x)$ visszaadja a Radon-Nikodym deriváltat

**The Bright Side of Mathematics vidik**: 
- [Radon-Nikodym tétel és Lebesque felbontás](https://youtu.be/12kFDeN6xuI?si=5LAAf9_PP6JjGB9a)

## VII. Korlátos változású, absz folyt. és szinguláris függvények, felbontásuk, differenciálásuk

### Korlátos változású függvények

Adott $f: I \mapsto \R$ függvény, ekkor az $f$ korlátos változású, ha létezik olyan $M \ge 0$, hogy minden felosztásra $I = \{ x_0, x_1, ... , x_n \}$, ahol $a = x_0 \lt x_1 \lt ... \lt x_n = b$ teljesül:

$\tau_f(I) = \sup \{ \sum_{i=1}^{n} \vert f(x_i) - f(x_{i-1}) \vert: n \ge 1, x_0 < x_1 < ... < x_n \in I \} \le \infty$

Azaz feldarabolva az $I$ intervallumot, a függvényértékek különbségeinek összege felülről korlátos, vagyis supremuma véges.

$f: I \mapsto \R$ akkor és csak akkor korlátos változású, ha $f = f_1 - f_2$, ahol $f_1, f_2$ véges, monoton növekvő függvények.

### Abszolút folytonos függvények

Egy $f: I \mapsto \R$ függvény abszolút folytonos, ha bármely diszjunkt intervallum családra, melynek összhossza(Lebesque mértéke) kisebb, mint egy adott $\delta$ érték, a függvényértékek különbségeinek összege kisebb, mint egy adott $\epsilon$ érték.

$\forall \epsilon \gt 0 \; \exists \delta \gt 0$ úgy, hogy bármely diszjunkt intervallum családra $\{ (a_i, b_i) \}$, ahol $\sum (b_i - a_i) \lt \delta$, teljesül: $\sum \vert f(b_i) - f(a_i) \vert \lt \epsilon$

- $\vert b_i - a_i \vert = \lambda(I_i)$, ahol $\lambda$ a Lebesque-mérték
- $\vert f(b_i) - f(a_i) \vert = \mu_f(I_i)$, ahol $\mu_f$ a $f$-hez tartozó Lebesque-Stieljes mérték

**Tétel:** Korlátos változású függvény Lebesque-Stieljes mértéke majdnem minden pontban differenciálható, és a derivált integrálja visszaadja a függvényt.

### Szinguláris függvények

Egy $f: I \mapsto \R$ függvény szinguláris, ha korlátos változású és létezik olyan $N \subset I$ halmaz, melynek Lebesque mértéke $0$, és $f$ csak ezen a halmazon változik.

### Korlátos változású függvények

Legyem $f: I \mapsto \R$ függvény, ekkor léteznek olyan $f_{1}, ..., f_n: I \mapsto \R$ korlátos változású függvények, hogy:
- $f = \sum_{i=1}^n f_i$
- $f$ korlátos változású $\iff$ minden $f_i$ korlátos változású
- Tagonként lehet deriválni m.m. x-en, és az eredmény a teljes függvény deriváltja lesz m.m. x-en

### Luzin tulajdonságú függvények

Olyan halmazfüggvények, amik minden nullmértékű halmazt nullmértékű halmazra képeznek.

$\lambda(A) = 0 \implies \lambda(f(A)) = 0$

### Abszolút folytonos függvények 2.

Ha létezik $f$ mérhető függvény és $f'$ véges minden $x \isin H$-en, akkor:
- $f'$ mérhető
- $\lambda(f(H)) = \int_H \vert f' \vert \; d\lambda$, azaz a mértéke felülről becsülhető a derivált abszolútértékének integráljával $H$-n
- $\lambda(f(H)) \lt \int_H \vert f'' \vert \; d\lambda$, ha $f''$ létezik és véges minden $x \isin H$-en, vagyis a függvény mértéke kisebb lesz, mint a második derivált abszolútértékének integrálja $H$-n


$f$ függvény pontosan akkor lesz abszolút folytonos, ha van egy $g$ függvény, amire igaz, hogy $f$ megváltozása $g$ integráljával egyenlő minden intervallumon.

$f(y)-f(x) = \int\limits_{[x,y]} g(t) \, d\lambda(t), \; \forall x \le y \isin I$

Ez akkor is érvényes, ha $f$ deriválható és $f' = g$ majdnem minden pontban. Abszolút folytonosság $\iff$ deriválhatóság majdnem minden pontban és a függvény visszaállítása a derivált integráljával.

### Lipschitz-folytonos függvények

Legyem $f: I \mapsto \R$ függvény, akkor Lipschitz-folytonos, ha létezik olyan $K \gt 0$ konstans, hogy minden $x,y \isin I$-re:

$\vert f(x) - f(y) \vert \le K \cdot \vert x - y \vert$, ahol $K$ a Lipschitz-állandó.

Ha korlátos változású a függvény, akkor felbontható abszolút folytonos és szinguláris részre.

**The Bright Side of Mathematics vidik**: 
- []()
- []()

## VIII. Mértékek szorzata

**Intuíció**:

Legyen két mérhető térünk $(X, \mathcal{M}, \mu)$ és $(Y, \mathcal{N}, \nu)$. Ekkor a két tér szorzata egy új mérhető teret hoz létre, ahol a halmazok a két eredeti tér halmazainak szorzataként értelmezhetők. A mértékek szorzata pedig egy új mértéket definiál ezen a szorzat téren, amely a két eredeti mérték kombinációját tükrözi.

Legyen a két mérhető tér szorzata pl. egy mérhető tégla, ekkor $\mathcal{T} = \{ A \times B \}$, ahol $A \in \mathcal{M}, B \in \mathcal{N}$. Ekkor a szorzatmérték a következőképpen definiálható:

$\alpha(\mathcal{T}) = \alpha(A \times B) = \mu(A) \cdot \nu(B)$

Tétel: $\alpha \; \sigma$-additv $\mathcal{T}$-re.

Ha vesszük $\mathcal{T}$ véges unióját, akkor:
- $A$ modulus lesz
- $\alpha$ kiterjeszthető lesz $A$-ra
- $\alpha \implies \varphi$ külső mérték lesz 

### Szorzatmérték

Legyen két mérhető térünk $(X, \mathcal{M}, \mu)$ és $(Y, \mathcal{N}, \nu)$. Ekkor a szorzatmérték egy új mértéket definiál a szorzat téren $(Z, \mathcal{S}, \varphi)$, ha:
- $Z = X \times Y$
- $\varphi$ az $\alpha$ kiterjesztése az A modulusról, megszorítva $\mathcal{S}$-re.
- $\mathcal{S}$ a $\varphi$-mérhető $\sigma$-algebra

### Fubini-tétel

A adott  $(X, \mathcal{M}, \mu)$ és $(Y, \mathcal{N}, \nu)$ és az általuk alkotott szorzatmértékes tér $(Z, \mathcal{S}, \varphi)$ esetén, ha $f \isin L_1(\varphi)$ vagy $\int_Z f \; d\varphi$ létezik és $\varphi$-véges, akkor:

$g(x) = \int_Y f(x,y) \; d\nu(y)$ m.m. mérhető és $g \isin L_1(\mu)$, továbbá:

$\int_Z g(x,y) \; d\varphi(x,y) = \int_X g(x) \; d\mu(x)$

### Véges sok tér szorzata

Adott $(X_i, \mathcal{M}_i, \mu_i)$ mérhető terek esetén, ahol $i = 1, 2, ... , n$, a szorzatmértékes tér $(Z, \mathcal{S}, \varphi)$ a következőképpen definiálható:

- $Z = X_1 \times X_2 \times ... \times X_n$
- $k$-szoros téglákhoz $\alpha$, ezek kiterjesztése $\varphi$-re $\mathcal{S}$-en
- $\mathcal{S}$ a $\varphi$-mérhető $\sigma$-algebra 

### Tetszőleges sok tér szorzata

Tetszőlegesen sok mértéktér esetén legyen majdnem minden tag mértéke 1, azaz $(X_i, \mathcal{M}_i, \mu_i)$, ahol $i \in I$ és $\mu_i(X_i) = 1$ minden kivétellel. Ekkor a szorzatmértékes tér $(Z, \mathcal{S}, \varphi)$ a következőképpen definiálható:

- $Z = \prod_{i \in I} X_i$
- $k$-szoros téglákhoz $\alpha$, ezek kiterjesztése $\varphi$-re $\mathcal{S}$-en
- $\mathcal{S}$ a $\varphi$-mérhető $\sigma$-algebra

**The Bright Side of Mathematics vidik**: 
- [Mértékek szorzata](https://youtu.be/BTU69ezkpZw?si=Wq68uU3O9sAs7i7P)
- [Fubini-tétel](https://youtu.be/sedRkfTNCRE?si=D5cvqtnc0WnC2QY6)

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


## X. Martingálok konvergencia tételei, nagy-eltérés tételek


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

$x: (\Omega, \mathcal{A}, \mathcal{P}) \mapsto (\mathcal{X}, \mathcal{B})$ (azaz a statisztikai mező teréből képez mérhető térbe) mérhető függvényt mintának hívunk.

- A minta eloszlása egy $P \isin \mathcal{P}$ mellett $Q = P \circ X^{-1}$
- $(\mathcal{X},\mathcal{B},\mathcal{Q})$ is statisztikai mező lesz
- Sok esetben: $x = (x_1, x_2, ..., x_n)$ FAE

### Statisztika

$T: \mathcal{X} \mapsto \mathcal{Y}$ minta teréből valamilyen mérhető térbe $(\mathcal{Y},\mathcal{C})$ képezést statisztikának nevezünk. Ez a mintaelemek mérhető függvénye, lényege, hogy kiszámolunk valamit az adatokból.

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
- $\mathbb{E}[Q_q^*](B) = Q(B) \mapsto Q_n^*(B) \mapsto Q(B)$ 1 valószínűséggel a mintanagyság növelésével
- $\mathrm{Var}(Q_n^*(B)) = \frac{1}{n} Q(B)(1-Q(B))$
- Normálás: $\sqrt{n} (Q_n^*(B)-Q(B)) \mapsto N(0, Q(B)(1-Q(B))$ eloszlásban

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
- $\lim\limits_{x \mapsto -\infty} F_n^*(x) = 0, \; \lim\limits_{x \mapsto \infty} F_n^*(x) = 1$
- $F_n^*(t) = Q_n^*((-\infty, t))$ egydim esetben


### Glivenko-Cantinelli tétel

Ha $\xi_1, ..., \xi_n$ független minta, akkor $n \mapsto \infty$-vel:

$\sup \mid F_n^*(t) - F(t) \mid \mapsto 0$,  1 valószínűséggel.

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

$S(x) = S(y) \mapsto \frac{f_{\vartheta}(x)}{f_{\vartheta}(y)}$ nem függ $\vartheta$-tól $\mu \times \mu$ domináló szorzatmérték szerint.

Legyen $S$ statisztika, $x,y$ minta. $S$ pontosan akkor minimálisan elégséges, ha:

$S(x) = S(y) \Longleftrightarrow \frac{f_{\vartheta}(x)}{f_{\vartheta}(y)}$ nem függ $\vartheta$-tól $\mu \times \mu$ domináló szorzatmérték és $(x,y) \isin \mathcal{X}^2$ szerint.



## III. Többdimenziós norm. eloszlás, nemcentrális Khi-négyzet eloszlás

### Többdimenziós normális eloszlás

Legyen $\underline X = (X_1, X_2, ..., X_n): \Omega \mapsto \R^n$ valószínűségi változó, akkor $\underline X$ többdimenziós normális eloszlású, ha minden $\underline a \in \R^n$-re az egydimenziós valószínűségi változó $\underline a^T \cdot \underline X$ normális eloszlású.

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

$m_{1|2} = m_1 + \Sigma_{12} \cdot \Sigma_{22}^{-1} \cdot (y_2 - m_2) \mapsto$ a várható érték lineáris függvénye a feltételnek

$\Sigma_{1|2} = \Sigma_{11} - \Sigma_{12} \cdot \Sigma_{22}^{-1} \cdot \Sigma_{21} \mapsto$ a kovariancia mátrix nem függ a feltételtől

### Nemcentrális Khi-négyzet eloszlás

Legyenek $X_1, X_2, ..., X_n$ független normális eloszlású valószínűségi változók, ahol $X_i \sim N(0,1)$, akkor a következő valószínűségi változó nemcentrális Khi-négyzet eloszlású:

$\sum_{j = 1}^n x_j^2 = \Vert x \Vert^2$ n szabadságfokú $\chi^2$ eloszlású.

$ \Vert \underline u \Vert_2 = \sqrt{\sum_{i=1}^n u_i^2}$ 2-es norma, ha $\underline u \isin \R^n$.

Ha $\underline Y \sim N(m, Id) \mapsto \Vert \underline Y \Vert_2^2$ eloszlása csak $\Vert m \Vert_2^2$-től függ, azaz a várható érték vektortól, ez a $\lambda$ paraméter a nemcentrálisitás paramétere.

**Ortogonális felbontás alterekre**

Legyen $\underline x \sim N_n(m, \sigma^2 Id),\; \R^n = L_1 \oplus L_2 \oplus ... \oplus L_k, \; \dim L_i = r_i$  (ortogonális felbontás alterekre), akkor: $P_i$ vetítés mátrixa $L_i$-re, $\; \underline x_i = P_i\underline x,\; \underline m_i = P_i \underline m$

Ebből következik, hogy:
$ \underline x_i \sim N_{ri}(\underline m_i, \sigma^2 P_i)$ és $\Vert x_i \Vert_2^2 \sim \sigma^2 x_{ri}^2 [\frac{\Vert \underline m_i \Vert^2}{\sigma^2}]$

**Nem-szingularitás esetén:**

Ha $\Sigma$ nem szinguláris, akkor $\underline X \sim N_n(m, \Sigma)$ esetén:

$\underline x^T \cdot \Sigma^{-1} \cdot \underline x \sim \chi_n^2[\underline m^T \cdot \Sigma^{-1} \cdot \underline m]$

## IV. Becslések elmélete, Blackwell-izálás

Keretrendszer: valamilyen $g(\nu)$-t szeretnénk becsülni, ahol $\nu$ ismeretlen paraméter. Van egy $T$ statisztikánk, ami alapján becslést készítünk: $\hat g(T)$.

### Becslés

$g: \varTheta \mapsto \mathcal{Y}, \; T: \mathcal{X} \mapsto \mathcal{Y}$, ahol $g$ a paramétermező mérhető függvénye és $T$ a minta alapján képzett statisztika. Ekkor $T(x)$ a $g(\nu)$ becslése.

**Torzítatlan becslés:**

Akkor mondjuk, hogy $T$ torzítatlan becslés $g(\nu)$-ra, ha:

$\mathbb{E}_{\nu}(T) = g(\nu), \; \forall \nu \in \varTheta$

Vagyis várható értékben megegyezik a becsült paraméterrel minden paraméterértékre.

Ha van torzítás, akkor:

$B_{\nu}(T) = \mathbb{E}_{\nu}(T) - g(\nu)$

**Veszteségfüggvény:**

Legyen $W: \R^k \times \Theta \mapsto \R_+$, ekkor 

$W(T(x); \nu)$ azt mutatja meg, hogy mennyire rossz a $T(x)$ becslés, ha a valódi paraméter $\nu$.

Tulajdonságok:
- $W(z; \nu) \ge 0, \; \forall z \isin \R^k, \nu \isin \Theta$
- $W(g(\nu); \nu) = 0, \; \forall \nu \isin \Theta$
- Első változójában konvex függvény

**Rizikófüggvény:**

Legyen $T$ becslés $g(\nu)$-ra és $W$ veszteségfüggvény, akkor a rizikófüggvény:

$R_{\nu}(T) = \mathbb{E}_{\nu}[W(T(X); \nu)]$

Vagyis a várható veszteség a becslés és a valódi paraméter között.

**Becslés összehasonlítása rizikófüggvénnyel:**

- Ekvivalens becslések: $R_{\nu}(T_1) = R_{\nu}(T_2), \; \forall \nu \isin \Theta$
- Jobb becslés: $R_{\nu}(T_1) \le R_{\nu}(T_2), \; \forall \nu \isin \Theta$ és van olyan $\nu_0$, hogy $R_{\nu_0}(T_1) \lt R_{\nu_0}(T_2)$
- Mátrix- és skalárfüggvényeknél nem mindig tudunk összehasonlítani

**Megengedhető, optimális, minimax becslések:**

Ha $\mathcal{D}$ becslések halmaza, akkor:
- $T \isin \mathcal{D}$ megengedhető, ha maximális, azaz nincs nála jobb nem-ekvivalens becslés a $\mathcal{D}$-ben, de lehet olyan, amivel nem összehasonlítható
- $T^* \isin \mathcal{D}$ optimális, ha minden $T$-vel összehasonlítható és jobb náluk. Négyzetes veszeteségfüggvénynél hatásosnak is hívják.
- $T^{**} \isin \mathcal{D}$ minimax, ha $\sup\limits_{\nu \in \Theta} R_{\nu}(T^{**}) = \inf\limits_{T \in \mathcal{D}} \sup\limits_{\nu \in \Theta} R_{\nu}(T)$, azaz a rizikófüggvény maximumát minimalizálja 

**Becslések besorolásának kapcsolata:**

Optimális $T$ becslés megengedhető és minimax is egyben.

**Négyzetes veszteségfüggvény (hatásos becslés feltétele):**

Négyzetes veszteségfüggvény esetén a hatásos/optimális becslés $\iff$ minimális varianciájú torzítatlan becslés. Képlettel:

$R_{\nu}(T) = \mathbb{E}_{\nu}[(T(X) - g(\nu))^2] = \mathrm{Var}_{\nu}(T) + B_{\nu}^2(T)$

**Hatásos becslés egyértelműsége:**

Ha $\mathcal{D}$ becslésosztály konvex, $W$ első változójában szigorúan konvex veszteségfüggvény és létezik hatásos becslés $T^* \isin \mathcal{D}$, akkor az egyértelmű.

**Konzisztencia:**

A becslések számának növelésével $T_n$ becsléssorozatot kapunk $g(\nu)$-ra. Ekkor:
- Gyenge konzisztencia: $T_n \xrightarrow{Sztoch.} g(\nu)$ minden $\nu \isin \Theta$-ra
- Erős konzisztencia: $T_n \xrightarrow{1} g(\nu)$ minden $\nu \isin \Theta$-ra

### Blackwell-izálás

Adott $g(\nu)$ becslésére egy $T$ becslése és $S$ elégséges statisztika. Ekkor a következő becslés:

$\tilde T(x) = \mathbb{E}_{\nu}(T \mid S = S(x))$

Egy új becslés, ami $S$-re kondicionálja az eredeti becslést.

$\tilde T$ torzítása megegyezik $T$ torzításával, de kisebb vagy egyenlő a varianciája minden $\nu \isin \Theta$-ra, azaz $\tilde T$ jobb vagy egyenlő $T$-nél rizikófüggvény alapján.

**Teljes T-statisztika:**

$S$ statisztika teljes, ha nem lehet olyan nem-triviális elégséges statisztikát találni, hogy:

$\mathbb{E}_{\nu}(\varphi(T)) = 0, \; \forall \nu$-re.

- Ha $T$ teljes elégséges statisztika, akkor bármely $g(\nu)$-ra egyetlen torzítatlan becslés létezik $T$-re kondicionálva.
- Ha $S$ teljes elégséges statisztika, akkor minimálisan elégséges is egyben.

**Optimális $\tilde T$ blackwell-izálással:**

Tetszőleges $T$ becslés és $S$ teljes elégséges statisztika esetén a $\tilde T$ blackwell-izált becslés optimális minden $\nu \isin \Theta$-ra.

$\tilde T(x)$ optimális a torzítatlan becslések halmazában, mert:
- $R_{\nu}(\tilde T) \le R_{\nu}(T)$ minden $\nu$-ra
- mindennel összehasonlítható
- $\tilde T /; T$-től független

## V. Fisher-információ és regularitás-feltételek

### Likelihood és loglikelihood függvény

Adott egy $x$ minta, ekkor a likelihood függvény:

$L(\vartheta; x) = f_{\vartheta}(x)$

Loglikelihood függvény:

$l(\vartheta; x) = \ln L(\vartheta; x) = \ln f_{\vartheta}(x)$

### Fisher-információ

Legyen $X$ valószínűségi változó sűrűségfüggvénye $f_{\vartheta}(x)$, ahol $\vartheta \in \Theta \subset \R$ egy paraméter. Ekkor a Fisher-információ a következőképpen definiálható:

$I(\vartheta) = \mathbb{E}_{\vartheta} \left[ \left( \frac{\partial}{\partial \vartheta} \ln f_{\vartheta}(X) \right)^2 \right]$

**Tulajdonságok:**

- Domináló mértéktől független
- Szimmetrikus, pozitív szemidefinit mátrix
- Additív független minták esetén: $I_n(\vartheta) = n \cdot I(\vartheta)$
- Ha a sűrűségfüggvény kétszer differenciálható, akkor: $I(\vartheta) = - \mathbb{E}_{\vartheta} \left[ \frac{\partial^2}{\partial \vartheta^2} \ln f_{\vartheta}(X) \right]$

### Regularitás-feltételek

**Gyenge regularitás-feltétel:**

$\mu$ domináló mérték mellett a következők teljesülnek:
- $\vartheta \mapsto f_{\vartheta}(x)$ folytonosan differenciálható $\mu$- majdnem minden $x$-re
- $I(\vartheta)$ véges, nem-szinguláris és $\vartheta$-ban folytonos

Gyenge regularitás esetén ha adott egy lokálisan korlátos $T(x)$ statisztika és $g(\vartheta) = \mathbb{E}_{\vartheta}(T(x))$ ekkor a deriváltja jól számolható, azaz $g$ folytonosan differenciálható: 

$\partial_{\vartheta} g(\vartheta) = \mathbb{E}_{\vartheta}(T(X) \cdot \partial_{\vartheta} l(\vartheta; X))$

**Erős regularitás-feltétel:**

$\mu$ domináló mérték mellett a következők teljesülnek:
- $l(\vartheta)$ kétszer folytonosan differenciálható $\vartheta$-ban, $\mu$- majdnem minden $x$-re
- $\sup\limits_{\vartheta} \Vert \partial_{\vartheta}^{2}l_x(\vartheta)\Vert \le M(x)$ és $\sup\limits_{\vartheta} \mathbb{E}_{\vartheta}(M(X))^2 \lt \infty$

Erős regularitás esetén:
- $\forall \vartheta \in \Theta : \int \partial_{\vartheta} f_{\vartheta}(x) d\mu(x) = 0$
- $I(\vartheta) = - \mathbb{E}_{\vartheta}(\partial_{\vartheta}^{2} l(\vartheta; X))$

### Állítások Fisher-információról

**Független minta esetén az információk összeadódnak**:

$x,y$ független, de ugyan olyan paraméterű eloszlásból, akkor:
$I_{x,y}(\vartheta) = I_x(\vartheta) + I_y(\vartheta)$

**Fisher-információ statisztikából**:

Ha $\mathcal{X}$ téren értelmezett mintából egy $\mathcal{Y}$ téren értelmezett $T$ statisztikát képezünk, akkor a Fisher-információ csökkenhet:
$I_T(\vartheta) \le I_X(\vartheta)$

Ha $T$ elégséges statisztika, akkor egyenlőség áll fenn:
$I_T(\vartheta) = I_X(\vartheta)$

**Fisher-információ és átparaméterezés**:

Ha átparaméterezünk egy $\varphi: \Psi \mapsto \Theta$ sima bijekcióval, akkor az új paraméter szerinti Fisher-információ a következőképpen alakul:
$I_{\Psi}(\psi) = I_{\Theta}(\varphi(\psi)) \cdot (\varphi'(\psi))^2$

Vagyis a Fisher-információ skálázódik az átparaméterezés deriváltjának négyzetével.

## VI. Információs határ, MM és ML módszerek

### Információs határ

Az információs határ azt jelenti, hogy bármely torzítatlan becslés varianciája nem lehet kisebb, mint a Fisher-információ inverze.

Előfeltételek:
- Gyenge regularitás
- $T$ torzítatlan becslés $g(\vartheta)$-ra
- $\mathbb{E}_{\vartheta}(\Vert T(X) \Vert^2) \lt \infty$, lokálisan korlátos
- $G(\vartheta) = \partial_{\vartheta} g(\vartheta)$ létezik és folytonos

Ekkor a becslés szórása alulról korlátos:

$\mathrm{Var}_{\vartheta}(T) \ge G(\vartheta) \cdot I^{-1}(\vartheta) \cdot G^T(\vartheta)$

Következmények:
- Amilyen nagy Fisher-információ, olyan kicsi lehet a becslés varianciája
- Akármilyen jól becsülünk, a szórás nem közelíti a nullát, ha a Fisher-információ véges
- Ha $\nu$-t becsüljük, akkor a korlát egyszerűsödik: $\mathrm{Var}_{\vartheta}(T) \ge I^{-1}(\vartheta)$

### Cramér-Rao egyenlőtlenség

**Torzítatlan becslésekre:**
Előfeltételek:
- Gyenge regularitás
- $T$ becslés $g(\vartheta)$-ra
- Torzítás nem megengedett
- $\mathbb{E}_{\vartheta}(\Vert T(X) \Vert^2) \lt \infty$, lokálisan korlátos
- $G(\vartheta) = \partial_{\vartheta} g(\vartheta)$ létezik

Ekkor a becslés szórása alulról korlátos:

$\mathrm{Var}_{\vartheta}(T) \ge (G(\vartheta)) \cdot I^{-1}(\vartheta) \cdot (G(\vartheta))^T$

**Torzított becslésekre:**
Előfeltételek:
- Gyenge regularitás
- $T$ becslés $g(\vartheta)$-ra
- $\mathbb{E}_{\vartheta}(\Vert T(X) \Vert^2) \lt \infty$, lokálisan korlátos

Ha nem torztatlan a $T$ statisztika, akkor is van információs határ, de korrigálni kell a torzítás és a torzítás deriváltjának függvényével:

$g: \Theta \mapsto \R^k$ folytonosan differenciálható $ \implies b_T(\vartheta)$ differenciálható ($B = \partial_{\vartheta} b_T$)

$R_T(\vartheta) \ge (G(\vartheta) + B(\vartheta)) \cdot I^{-1}(\vartheta) \cdot (G(\vartheta) + B(\vartheta))^T$

### Momentum-módszer (MM)

Legyen $\varphi: \mathcal{X} \mapsto \R^k$ mérhető függvény, akkor a momentum-módszerrel úgy próbáljuk megbecsülni a $\vartheta$ paramétert, hogy a minta alapján képzett tapasztalati momentumokat egyenlővé tesszük az elvi momentummal.

Legyen még $\varphi(\vartheta) = (\mathbb{E}_{\vartheta}(\varphi_1(X)), ..., \mathbb{E}_{\vartheta}(\varphi_k(X)))$ kiválasztott több momentumfüggvény, akkor a becslés:

$\hat{\vartheta} = \varphi^{-1}(\frac{1}{n} \sum_{i=1}^n \varphi(X_i^{j1}), ... , \frac{1}{n} \sum_{i=1}^n \varphi(X_i^{jp}))$

Ha $\varphi$ $p$-dimenziós, akkor $p$ db momentum kell, viszont figyelni kell arra, hogy ne egy altérbe essenek, vagyis lineárisan független alterekben legyenek.

### Maximum likelihood módszer (ML)

**Paraméter ML becslése:**

A maximum-likelihood elve szerint az ismeretlen paraméter azon értékét fogadjuk el, amely mellett a bekövetkezett eredmény maximális valószínűségű/sűrűségű.

Legyen x fix minta, $x \mapsto f_{\vartheta}(x)$-t adott $\vartheta$-ban maximalizáljuk és azt a $\hat{\vartheta}$-t választjuk, ahol $\partial_{\vartheta} l(\vartheta; x) = 0$, ez a likelihood egyenlet. 

Tulajdonságok, ha a minta mérete elég nagy és teljesülnek az erős regularitás-feltételek:
- Van a likelihood egyenletnek megoldása
- Van olyan $\hat \vartheta$ ami lokális maximum
- Erősen konzisztens, azaz $\hat \vartheta_n \xmapsto{1} \vartheta$
- Aszimptotikusan normális eloszlású: $\sqrt{n}(\hat \vartheta_n - \vartheta) \xmapsto{d} N(0, I^{-1}(\vartheta))$

**Indukált likelihood, paraméter függvények ML becslése:**

Ha $g(\vartheta)$-t szeretnénk becsülni, akkor az máshogy kell hozzáállni:
- Ha $g$ bijektív, akkor átparaméterezve becslünk: $\psi = g(\vartheta)$ és az új paraméter szerinti likelihood egyenletet oldjuk meg
- Ha $g$ nem bijektív, akkor az indukált likelihood függvényt kell maximalizálni:
    $f_{\gamma}^*(x) = \sup \{ f_{\vartheta}(x) : g(\vartheta) = \gamma \}$

Ha $\vartheta$ ML becslője $\hat \vartheta$, akkor $g(\hat \vartheta)$ az indukált likelihood szerinti ML becslés $g(\vartheta)$-ra.

**ML becslés és elégséges statisztika:**
 
Ha van ML becslés, akkor felírható olyan is, ami elégséges statisztika függvénye.

**Bahadur-tétele, asszimptotikus Cramer-Rao:**

Cramer-Rao-t terjeszti ki aszimptotikus esetre:

Legyenek adottak az erős regularitási feltételek, legyen $g$ folytonosan differenciálható, $G (\vartheta) = \partial_{\vartheta} g(\vartheta)$ és legyen $T_n: \mathcal{X}^n \mapsto \R^k$ torzítatlan becslés $g(\vartheta)$-ra, ami konzisztens és aszimptotikusan normális eloszlású:

$Q(\vartheta) = \ge G(\vartheta) \cdot I^{-1}(\vartheta) \cdot G^T(\vartheta)$

Következménye, hogy az ML becslés aszimptotikusan optimális, azaz eléri az információs határt.

## VII. Hipotézisvizsgálat alapjai, likelihood-hányados próba egyszerű hipotéziseknél

### Hipotézis, ellenhipotézis

Intuíció: Nem az összes mérték közül keressük az igazit, hanem $\mathcal{P} = \mathcal{P}_0 \cup^* \mathcal{P}_1$ diszjunkt halmazokra bontjuk fel. Az eloszlás vagy paraméter teret ketté bontjuk és a kérdés, hogy melyik részbe tartozik a valódi eloszlás.

$H_0: P \in \mathcal{P}_0$ nullhipotézis

$H_1: P \in \mathcal{P}_1$ ellenhipotézis

Ha paramétermezőn vagyunk, akkor: $\Theta = \Theta_0 \cup^* \Theta_1$

Vagy elfogadjuk, vagy elvetjük a nullhipotézist.

**Döntés vs minta:**

A mintát is szét kell bontani $\mathcal{X} = \mathcal{X}_k \cup \mathcal{X}_e$, ahol $\mathcal{X}_k$ elfogadási tartomány és $\mathcal{X}_e$ elutasítási tartomány.

Ekkor a döntési szabály:
- Ha $x \in \mathcal{X}_e$, akkor elfogadjuk $H_0$-t
- Ha $x \in \mathcal{X}_k$, akkor elutasítjuk $H_0$-t

**Asszimetria a hipotézisek között:**

- Ha $H_0$: $\mathcal{P}_0$ nagyvonalúan belefér a képbe $x$ minta alapján, akkor engedékenyebbek vagyunk
- Ha $H_1$: $\mathcal{P}_0$ iszonyúan nem stimmel, szinte köze nincs hozzá, akkor nagyon markánsan, szignifikánsan $\mathcal{P}_1$-ben vagyunk

### Hibák

**Hibák típusai:**
- Elsőfajú hiba: $H_0$ ($P \in \mathcal{P}_0$) igaz, de elutasítjuk, ezt nagyon nem szeretnénk
- Másodfajú hiba: $H_1$ ($P \in \mathcal{P}_1$) igaz, de elfogadjuk $H_0$-t, ezt is szeretnénk elkerülni, de nem annyira, mint az elsőfajút

**Terjedelem:**

$\alpha = \sup\limits_{P \in \mathcal{P}_0} P_{\vartheta}(\mathcal{X}_k)$ a kritikus tartomány valószínűsége, ha a valódi $\vartheta$ a nullhipotézis tartományában van, vagyis az elsőfajú hiba valószínűsége.

**Erő:**

$\beta(\vartheta) = P_{\vartheta}(\mathcal{X}_e)$ a kritikus tartomány valószínűsége, ha a valódi $\vartheta$ az ellenhipotézis tartományában van, vagyis a másodfajú hiba valószínűsége.

**Mikor jó egy próba?**

- Torzítatlan: Erő $\ge$ terjedelem $\rarr$ $\beta(\vartheta) \ge \alpha, \; \forall \vartheta \in \Theta_1$
- Összehasonlítás: Egy próba $(\mathcal{X}_k, \mathcal{X}_e)$ jobb egy másiknál $(\mathcal{X}_k', \mathcal{X}_e')$, ha ugyan olyan terjedelme van, de nagyobb az ereje minden $\vartheta \in \Theta_1$-re.
- Definiálható fix $\alpha$ mellett egyenletesen legerősebb próba, ami $\max \beta(\vartheta)$-t adja minden $\vartheta \in \Theta_1$-re.
- Egy próbasorozat konzisztens, ha rögzített $\alpha$ esetén a minta méretének ($n$) növelésével az erő tart 1-hez: $\lim\limits_{n \to \infty} \beta_n(\vartheta) = 1, \; \forall \vartheta \in \Theta_1$

**Véletlenített próba:**

Nem egy döntést kapunk, hanem valószínűséget és a végén ez alapján sorsolunk eredményt.

### Likelihood-hányados próba

**Neyman-Pearson lemma:**

Ha $H_0, H_1$ egyszerű hipotézisek és $n$ elemű mintánk van, akkor a próbafüggvény:

$\varphi(x) = \begin{cases}
1, & \text{ha } \frac{f(\vartheta_1; x)}{f(\vartheta_0; x)} \gt c \\
\gamma, & \text{ha } \frac{f(\vartheta_1; x)}{f(\vartheta_0; x)} = c \\
0, & \text{ha } \frac{f(\vartheta_1; x)}{f(\vartheta_0; x)} \lt c
\end{cases}$ 

Ahol $c$ a kritikus érték. A próbafüggvényt paramétereit minden $\alpha$-hoz lehet úgy választani, hogy a próba terjedelme $\alpha$ legyen. Ez a próba lesz az egyenletesen legerősebb próba minden $\alpha$-ra.

Ez a likelihood-hányados próba: Ha $x$-nek $n$ elemű mintáját nézzük, akkor nem egy tört, hanem többnek a szorzata van, ezért logaritmizálva kényelmesebb dolgozni vele.

Aszimptotikusan: $\frac{\prod\limits_{i=1}^{n} f_1 (x_i)}{\prod\limits_{i=1}^{n} f_0 (x_i)} \xRightarrow{log} \sum\limits_{i=1}^n \log \frac{f_1(x_i)}{f_0(x_i)} \approx -n D(P_1 \Vert P_0)$ a nagy számok erős törvénye miatt. Itt $\Vert$ a két mérték összehasonlítását jelenti.

**Kullback-Leibler divergencia:**

A Neyman-Pearson lemmában szereplő $D(P_1 \Vert P_0)$ a Kullback-Leibler divergencia, ami két eloszlás közötti távolságot méri:

$D(P_1 \Vert P_0) = \int - \log \frac{dQ}{dP} \; dP$

Nem szimmetrikus, azaz $D(P_1 \Vert P_0) \neq D(P_0 \Vert P_1)$ általában. A minta méretének növelésével a két eloszlás közötti különbség egyre jobban látszik a divergencia miatt, azaz jobb lesz a próba és eloszlásban normális lesz.

**Nagy minta esetén az erő határértéke:**

Nagymintás próba esetén az erő tart egyhez:

$d_n = n D(P_0 \vert P_1) + \sqrt{n} \cdot \sigma \Phi^{-1}(\alpha)$

Ahol $\sigma: \log \frac{f_1}{f_0}$ szórása és $\Phi^{-1}$ a standard normális eloszlás inverze.

Ekkor a próba:

$\varphi(x) = \begin{cases}
1, & \text{ha } \log \frac{f_1(x)}{f_0(x)} \ge e^{-d_n} \\
0, & \text{egyébként}
\end{cases}$

- Terjedelme $n \mapsto \infty$-ben tart $\alpha$-hoz
- Ereje $n \mapsto \infty$-ben tart 1-hez, $\beta \gt 1 - e^{-nD(P_1 \Vert P_0)-\delta(n)}$

## VIII. Normális eloszlás paramétereire vonatkozó próbák

### Khi-négyzet eloszlás

$x \sim N(0, I_n) \; n$-dimenziós normális eloszlás esetén: $y = \Vert x \Vert^2, \; y \isin [0, \infty)$ eloszlása $n$ szabadságfokú Khi-négyzet eloszlású.

### Student-féle t eloszlás

Legyen $x \sim N(0,1), \; y \sim \chi^2_n$ eloszlású független valószínűségi változók, akkor a következő valószínűségi változó eloszlása Student-féle t eloszlású $n$ szabadságfokkal:

$t = \frac{x}{\sqrt{\frac{y}{n}}}$

Tulajdonságok:
- az eloszlás szimmetrikus
- $n = 1$ esetén Cauchy-eloszlás
- $n \to \infty$ esetén normális eloszlás

### F-eloszlás

Legyenek $x \sim \chi^2_m, \; y \sim \chi^2_n$ független valószínűségi változók, akkor a következő valószínűségi változó eloszlása F-eloszlású $m$ és $n$ szabadságfokkal:

$F = \frac{\frac{x}{m}}{\frac{y}{n}}$

Tulajdonságok:
- $F_{n,m} \sim \frac{1}{F_{m,n}}$
- $F_{1,n} \sim t_n^2$
- Rögzített $n$ mellett, $F_{m,n} \xmapsto{m \to \infty} \chi_n^2$

### Fisher-Bartlett tétel

Ha $n$ elemű mintánk van, $X_1, ..., X_n \sim N(\mu, \sigma^2)$ független, akkor:

- A mintaátlag és a tapasztalati szórás $(\overline x, s_n^*)$ együtt elégséges statisztika
- $\overline X$ és $s_n^*$ függetlenek egymástól
- $\overline X \sim N(\mu, \frac{\sigma^2}{n})$
- $s_n^{*2} \sim \frac{\sigma^2 }{n-1} \cdot \chi_{n-1}^2$

### u-próbák

**Egymintás u-próba:**

A várható értéket keressük, $\sigma^2$ ismert, $\mu$ nem, a terjedelem $\alpha$ adott.

A próbafüggvény:

$u = \frac{\overline X - \mu_0}{\sigma / \sqrt{n}} \sim N(0,1)$

Hipotézisek:
- Kétoldali próba: $H_0: \mu = \mu_0$ vs $H_1: \mu \neq \mu_0$
- Jobb oldali próba: $H_0: \mu \le \mu_0$ vs $H_1: \mu \gt \mu_0$
- Bal oldali próba: $H_0: \mu \ge \mu_0$ vs $H_1: \mu \lt \mu_0$

Kritikus tartomány:
- Kétoldali próba: $\mathcal{X}_e = \{ x : |u| \gt u_{\alpha/2} \}$
- Jobb oldali próba: $\mathcal{X}_e = \{ x : u \gt u_{\alpha} \}$
- Bal oldali próba: $\mathcal{X}_e = \{ x : u \lt -u_{\alpha} \}$

**Kétmintás u-próba:**

A várható értékek egyezését keressük.

Van két független mintánk, $X_1, ..., X_n \sim N(\mu_1, \sigma_1^2)$ és $Y_1, ..., Y_m \sim N(\mu_2, \sigma_2^2)$, ahol $\sigma_1^2, \sigma_2^2$ ismertek.

A próbafüggvény:

$u = \frac{(\overline X - \overline Y) - (\mu_1 - \mu_2)}{\sqrt{\frac{\sigma_1^2}{n} + \frac{\sigma_2^2}{m}}} \sim N(0,1)$

Ha $\mu_1 - \mu_2 = 0$, akkor a hipotézisek és kritikus tartományok ugyan azok, mint az egymintás u-próbánál.

### t-próbák

**Egymintás t-próba:**

A várható értéket keressük, $\mu, \sigma^2$ ismeretlen, $x_1, ..., x_n \sim N(\mu, \sigma^2)$ független minta, $\mu_0$ adott.

Próbafüggvény:

$t = \frac{\overline X - \mu_0}{s_n^*} \cdot \sqrt{n} \sim t_{n-1}$

ha $H_0: \mu = \mu_0$.

Kritikus tartomány:
- Kétoldali próba: $\mathcal{X}_e = \{ x : |t| \gt t_{n-1, \alpha/2} \}$
- Jobb oldali próba: $\mathcal{X}_e = \{ x : t \gt t_{n-1, \alpha} \}$
- Bal oldali próba: $\mathcal{X}_e = \{ x : t \lt -t_{n-1, \alpha} \}$

**Kétmintás t-próba:**

Két független minta, minden paraméter ismeretlen, de a szórások egyenlőek: $X_1, ..., X_n \sim N(\mu_1, \sigma^2)$ és $Y_1, ..., Y_m \sim N(\mu_2, \sigma^2)$.

Próbafüggvény:

$t = \frac{(\overline X - \overline Y) - (\mu_1 - \mu_2)}{s_p^* \cdot \sqrt{\frac{1}{n} + \frac{1}{m}}} \sim t_{n+m-2}$

**Welch-próba:**

Két független minta, minden paraméter ismeretlen, a szórások nem feltétlen egyenlőek: $X_1, ..., X_n \sim N(\mu_1, \sigma_1^2)$ és $Y_1, ..., Y_m \sim N(\mu_2, \sigma_2^2)$.

Próbafüggvény:

$t = \frac{(\overline X - \overline Y) - (\mu_1 - \mu_2)}{\sqrt{\frac{s_{n}^{*2}}{n} + \frac{s_{m}^{*2}}{m}}} \sim t_{\nu}$

Ahol a $\nu$ szabadságfok fiktív, képlettel számolható.

### F-próbák

**Kétmintás F-próba:**

Két független minta szórásnégyzetének egyezését keressük: $X_1, ..., X_n \sim N(\mu_1, \sigma_1^2)$ és $Y_1, ..., Y_m \sim N(\mu_2, \sigma_2^2)$.

Ha $H_0: \sigma_1^2 = \sigma_2^2, \; H_1: \sigma_1^2 \ne \sigma_2^2$, akkor a próbafüggvény:

$F = \frac{s_{n}^{*2}}{s_{m}^{*2}} \sim F_{n-1, m-1}$

Kritikus tartomány:
- Kétoldali próba: $\mathcal{X}_e = \{ x : F \lt F_{n-1, m-1, \alpha/2} \text{ vagy } F \gt F_{n-1, m-1, 1-\alpha/2} \}$
- Jobb oldali próba: $\mathcal{X}_e = \{ x : F \gt F_{n-1, m-1, 1-\alpha} \}$
- Bal oldali próba: $\mathcal{X}_e = \{ x : F \lt F_{n-1, m-1, \alpha} \}$

**Egymintás F-próba:**

A kétmintás F-próba leegszerűsödik egymintás F-próbává, ha a második minta szórásnégyzetét ismertnek vesszük. Hipotézisek: $H_0: \sigma^2 = \sigma_0^2, \; H_1: \sigma^2 \ne \sigma_0^2$.

Próbafüggvény:

$F = \frac{s_{n}^{*2}}{\sigma_0^2} \sim \frac{1}{n-1} \cdot \chi_{n-1}^2$

Kritikus tartomány:
- Kétoldali próba: $\mathcal{X}_e = \{ x : F \lt \frac{1}{n-1} \cdot \chi_{n-1, \alpha/2}^2 \text{ vagy } F \gt \frac{1}{n-1} \cdot \chi_{n-1, 1-\alpha/2}^2 \}$
- Jobb oldali próba: $\mathcal{X}_e = \{ x : F \gt \frac{1}{n-1} \cdot \chi_{n-1, 1-\alpha}^2 \}$
- Bal oldali próba: $\mathcal{X}_e = \{ x : F \lt \frac{1}{n-1} \cdot \chi_{n-1, \alpha}^2 \}$  

## IX. Khi-négyzet próbák illeszkedésvizsgálatra és következményeik. Folytonos illeszkedésvizsgálat

### Diszkrét illeszkedésvizsgálat

### Diszkrét homogenitásvizsgálat

## X. Lineáris modell, Lineáris hipotézis normális lineáris modellben

