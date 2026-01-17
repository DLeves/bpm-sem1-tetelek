# Mértékelmélet

Órai videók:
- [Első előadás](https://youtu.be/OXQnszgqr38?si=MunomfBGGzM-mily)
- [Második előadás](https://youtu.be/XwVpHkQnmrE?si=-TJKX-JSLYFBGsre)
- [Harmadik előadás](https://youtu.be/0cUc5JkPuag?si=SjTLq8BqAgGA_z66)

## I. Mérhető tér, mérhető leképezések, mérték

Ez a fejezet adja a teljes tárgy „nyelvét”: milyen halmazokat tekintünk mérhetőnek (σ-algebra), és hogyan értelmezünk rajtuk mértéket. A mérhető leképezések azért kulcsfontosságúak, mert integrálásnál és valószínűségszámításban állandóan ősképekkel dolgozunk. Az egyszerű függvények pedig a Lebesgue-integrál felépítésének alapkövei: ezekkel közelítjük a bonyolultabb mérhető függvényeket.

Alapfogalmak:
- $X$ alaptér
- $\mathcal{P}(X)$: hatványhalmaz (powerset) - $X$ halmaz minden részhalmazának rendszere
- $A \subset \mathcal{P}(X)$: halmazrendszer

### Halmazrendszerek

- **Modulus**: ha $A, B \in \mathcal{A}$ esetén $A \setminus B \in \mathcal{A}$
- **Félgyűrű**: ha $A, B \in \mathcal{A}$ esetén $A \cap B \in \mathcal{A}$
- **Algebra**: ha $A, B \in \mathcal{A}$ esetén $X \setminus A \in \mathcal{A}$
- **$\sigma$-algebra**: $\mathcal{A} \subseteq \mathcal{P}(X)$ $\sigma$-algebra, ha:
    - $\emptyset, X \in \mathcal{A}$
    - $A \in \mathcal{A} \Rightarrow A^c := X \setminus A \in \mathcal{A}$
    - $A_i \in \mathcal{A},\ i \in \N \Rightarrow \bigcup_{i=1}^{\infty} A_i \in \mathcal{A}$
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

$(X, \mathcal{A})$ mérhető tér, ha $\mathcal{A} \in \mathcal{P}(X)$ $\sigma$-algebra. Ekkor $\mathcal{A}$ elemei mérhető halmazok.

Topologikus tér ($(X,\tau)$) egy általánosított metrikus tér. A metrikus tér, egy olyan halmaz, amin értelmezett egy metrika (távolságfüggvény).

### Mérhető leképezés

Adott $(X, \mathcal{M})$ és $(Y, \mathcal{N})$ mérhető terek, az $f: X \mapsto Y (\mathcal{M}, \mathcal{N})$ mérhető leképezés. Ekkor $\{ A \subset Y: f^{-1}(A) \in \mathcal{M} \}$ az halmazrendszer $\sigma$-algebra $Y$-on.

Generált alterekkel tulajdonság:

$U \subset \mathcal{P}(Y)$ és $\forall u \in U: f^{-1}(u) \in \mathcal{M}$
- $\forall u \in \sigma(U)$-ra is $\mapsto$ a generált altér is a $\sigma$-algebrában van
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

Legyen $(X, \mathcal{M})$ mérhető tér, a $\mu: \mathcal{M} \mapsto \overline\R$ leképezést mértéknek nevezzük, ha
1. $\mu \ge 0$
2. $\mu(\empty) = 0$
3. $H_n \in \mathcal{M}, H_n \cap H_k = 0$ esetén $\mu(\cup_{i=1}^{\infty} H_i) = \sum_{i=1}^{\infty} \mu(H_i)$


**The Bright Side of Mathematics vidik**: 
- [$\sigma$-algebra](https://youtu.be/xZ69KEg7ccU?si=C9r1hWmVKRvSQdif)
- [Borel $\sigma$-algebra](https://youtu.be/z5m6HXKx0Wo?si=CTafKwAV9K5xf1TA)
- [Mérhető terek](https://youtu.be/11heoNVavvM?si=siO9Wsuj485i5DWe)
- [Mértékek](https://youtu.be/7O7qPrNIt7w?si=k13l2xuJWvkvXic2)

## II. Integrál, függvénysorozatok, függvénysorok és integráljaik

Itt épül fel a Lebesgue-integrál: először egyszerű függvényekre definiáljuk, majd monoton közelítéssel kiterjesztjük általános nemnegatív (majd előjeles) függvényekre. A vizsgán tipikusan a konvergenciatételek (monoton konvergencia, Fatou, dominált konvergencia) a legfontosabbak, mert ezek indokolják a határátmenetek és integrálás felcserélését. Ezek a tételek adják a Lebesgue-integrál „erejét” a Riemann-integrállal szemben.

### Integrál

Adott $f \ge 0$ egyszerű függvény és $(X, \mathcal{M}, \mu)$ mértéktér, valamint $H \in \mathcal{M}$ mérhető halmaz. $f$ értékei $c_1, ..., c_n$ és $A_k = \{x: f(x) = c_k \}$, vagyis $A_k$ az a halmaz, ahol $f$ felveszi a $c_k$ értéket.

Ekkor $f$ függvény $H$-n vett $\mu$ szerinti integrálja:

$\int_H f \, d\mu = \sum_{k=1}^n c_k \cdot \mu(H \cap A_k)$

- Vagyis a halmazok mértéke súlyozva a függvényértékkel
- Ami nem más, mint a $c_k$ magasságokkal az $A_k$ hosszok szorozva $\mapsto$ terület

**Megjegyzések**:

Adott $0 \le g \le f$ mérhető függvények és $A \subset B$ halmazok, ekkor

- $\int_A g \, d\mu \le \int_A f \, d\mu \le \int_B g \, d\mu$

- $g \mid_A \equiv c$ (konstans) esetén $\int_A f \; d\mu = c \cdot \mu(A)$ (megj: $g \mid_A$ a $g$ függvény megszorítva $A$ pontra/környezetére)

- $\mu(A) = 0 \mapsto \int_A f \; d\mu = 0$, vagyis üres halmazon integrálva nullát kapunk

- $\int_A f \; d\mu = \int_B f \cdot \chi_A \; d\mu$, vagyis $A$-n vett integrál megegyezik a $B$-n vett $f$ és az indikátorfüggvény szorzatának integráljával.

- $\int_A (f + c \cdot g) \; d\mu = \int_A f \; d\mu + c \cdot \int_A g \; d\mu$ integrálási azonosság

- $\varphi(H) = \int_H f \; d\mu$ az integrálás, mint halmazfüggvény mérték

### Lebesque integrál

Legyen $f \ge 0$ mérhető, $H \in \mathcal{M}$ mérhető halmaz, ekkor:

$\int_H f \, d\mu = \sup\Big\{\int_H g \, d\mu : 0 \le g \le f,\ g\ \text{egyszerű}\Big\}.$

**Megjegyzések**:
- $f^+ = \max(f,0), f^- = -\min(f,0)$ adott, ha $\int_X f^+ d\mu$ vagy $\int_X f^- d\mu$ véges akkor $f$ integrálható, illetve $\int_X f^+ d\mu - \int_X f^- d\mu$ véges esetén $f$ végesen integrálható.

- $\lVert f \rVert_{L^1} := \int_X \lvert f \rvert \, d\mu$ értelmes (ha véges)

### Monoton konvergencia tétele

Legyen $0 \le f_1 \le ... \le f_n$ m.m. monoton növekvő, $\lim_{n \to \infty} f_n = f$ pontonként konvergáló, mérhető függvénysorozat.

Ekkor az integrál is konvergál: $\lim_{n \to \infty} \int_X f_n \, d\mu = \int_X f \, d\mu$.

Ilyen tételek miatt sokszor jobb a Lebesque integrál a Riemann integrálnál.

### Összeg integrálja

 $\int_A (f + g) \, d\mu = \int_A f \, d\mu + \int_A g \, d\mu$, ahol $f, g \ge 0$

### Beppo-Levi Tétel

Ha $f_n \ge 0$ mérhető, akkor a függvények összegének integrálja megegyezik az integráljaik összegével.

$\int_X \sum_{n=1}^{\infty} f_n \; d\mu = \sum_{n=1}^{\infty} \int_X f_n \; d\mu$

### Fatou-Lemma

a $f_n \ge 0$ mérhető, akkor:

$\int_A \liminf f_n \; d\mu \le \liminf \int_A f_n \; d\mu$

### Lebesque-dominált konvergencia tétel

$f_n$ mérhető és $\lvert f_n \rvert \le g, \quad g \in L^1(\mu)$, ekkor $f_n \to f$, valamint:

$\lim_{n\to\infty} \int_X f_n \, d\mu = \int_X f \, d\mu$

Ha a két fv m.m. megegyezik, akkor az integráljuk is. Ilyenkor $g$ majorálja (dominálja) $\mid f_n \mid$-et, vagyis felettük helyezkedik el. 

**The Bright Side of Mathematics vidik**: 
- [Lebesque integrál](https://www.youtube.com/watch?v=TG67nsccqeQ&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=6)
- [Riemann integrál vs. Lebesque integrál](https://www.youtube.com/watch?v=PGPZ0P1PJfw&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=24)
- [Monton konvergencia tétel](https://www.youtube.com/watch?v=1tzaUiZJXm8&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=7)
- [Lebesque-dominált konvergencia](https://www.youtube.com/watch?v=eu-6_wpTE-A&list=PLBh2i93oe2qvMVqAzsX1Kuv6-4fjazZ8j&index=10)

## III. Mértékek kiterjesztése. Lebesque- és Lebesque-Stieljes mérték

Ennek a fejezetnek a lényege, hogy hogyan tudunk „jó” módon mértéket definiálni először egyszerű halmazcsaládon (pl. intervallumok, téglák), majd kiterjeszteni σ-algebrára. A külső mérték és a Carathéodory-kritérium a standard eszköz: ezzel kapjuk a Lebesgue-mértéket és a Lebesgue-mérhető halmazok σ-algebráját. A Lebesgue–Stieltjes mérték pedig megmutatja, hogyan kódol egy monoton függvény egy mértéket (és hogyan jelennek meg az „atomok”).

### Külső mértékek

$\alpha$ külső mérték: $\mathcal{A} \subseteq \mathcal{P}(X)$ halmazrendszeren, $\alpha(\emptyset) = 0$ és $\alpha \ge 0$, $\alpha: \mathcal{A} \to \overline \R$. $A_1, A_2, ... \in \mathcal{A}$ halmazokra $\alpha\big(\bigcup_{i=1}^{\infty} A_i\big) \le \sum_{i=1}^{\infty} \alpha(A_i)$, azaz $\sigma$-szubadditív.

Ekkor legyen:

$\alpha(H) = \inf \Big\{ \sum_{i=1}^\infty \alpha(A_i) : H \subseteq \bigcup_{i=1}^\infty A_i,\ A_i \in \mathcal{A} \Big\}$

**Külső mértékek kiterjesztése:**

A külső mértékkel mérhatő halmazok egy $\sigma$-algebrát alkotnak, amennyiben teljesül a Caratheodory tétel. Legyen ez a $\mathcal{M} \, \sigma$-algebra

Legyen $\alpha$ egy külső mérték $\mathcal{M}$-en, illetve legyen $\mathcal{A} \subseteq \mathcal{M}$, ekkor a $\mu \coloneqq \alpha \mid_\mathcal{A}$, azaz a külső mértéket megszorítva $\mathcal{A}$-ra megkapjuk a mértéket $\mathcal{A}$-n.

Legyen $\mathcal{M}_{\alpha} \subset \mathcal{P}(X) \; \sigma$-algebra, ekkor: $(X, \mathcal{M}, \mu)$ teljes mértéktér.

### Lebesque mérték

Intuíció: A Lebesque-mérték az „hossz / terület / térfogat” formális általánosítása úgy, hogy nagyon sok (nem csak „szép”) halmazra is értelmezhető legyen, és teljesüljön a $\sigma$-additivitás.

**Konstrukció (Carathéodory-féle kiterjesztés):**

1) **Félgyűrű / téglák (alapcsalád):** $\R^n$-ben tekintsük a félzárt téglákat
$$R = \prod_{j=1}^n (a_j,b_j], \qquad a_j < b_j.$$
Ezeken definiáljuk a „térfogat” előmértéket:
$$\alpha(R) := \prod_{j=1}^n (b_j-a_j).$$

2) **Külső mérték (Lebesque-külső mérték):** Tetszőleges $E\subset \R^n$ halmazra
$$\lambda_n^*(E)
= \inf\Big\{\sum_{k=1}^\infty \alpha(R_k)\;:\; E\subset \bigcup_{k=1}^\infty R_k,\; R_k\text{ félzárt téglák}\Big\}.$$
Vagyis $E$-t téglákkal lefedjük, összeadjuk a térfogataikat, és ezek infimumát vesszük.

3) **Lebesque-mérhetőség (Carathéodory-kritérium):** Egy $H\subset\R^n$ halmaz Lebesque-mérhető, ha minden $A\subset\R^n$-re
$$\lambda_n^*(A)=\lambda_n^*(A\cap H)+\lambda_n^*(A\setminus H).$$

4) **Lebesque-mérték:** A Lebesque-mérték $\lambda_n$ a $\lambda_n^*$ megszorítása a Lebesque-mérhető halmazok $\sigma$-algebrájára:
$$\lambda_n := \lambda_n^*\big|_{\mathcal{L}}.$$

**1D eset (hossz):** $n=1$-ben $\lambda_1 = \lambda$ és intervallumokra
$$\lambda((a,b))=\lambda([a,b])=\lambda((a,b])=\lambda([a,b))=b-a.$$

**Fontos tulajdonságok (vizsgára):**
- $\lambda_n$ mérték: $\sigma$-additív, $\lambda_n(\emptyset)=0$.
- **Transzláció invariáns:** $\lambda_n(E+x)=\lambda_n(E)$ minden mérhető $E$-re és $x\in\R^n$-re.
- **Teljes (complete):** ha $\lambda_n(N)=0$ és $A\subset N$, akkor $A$ is mérhető és $\lambda_n(A)=0$.
- **$\sigma$-véges:** pl. $\R^n=\bigcup_{k=1}^\infty[-k,k]^n$, és $\lambda_n([-k,k]^n)<\infty$.
- Minden Borel-halmaz Lebesque-mérhető (a Lebesque-$\sigma$-algebra tartalmazza a Borel-$\sigma$-algebrát).

### Lebesque-mérhető halmazok

Egy $H \subset \R^n$ halmaz **Lebesque-mérhető** (Carathéodory-értelemben), ha minden $A\subset \R^n$-re teljesül:
$$\lambda_n^*(A) = \lambda_n^*(A\cap H) + \lambda_n^*(A\setminus H).$$

Jelölés: a Lebesque-mérhető halmazok $\sigma$-algebrája legyen
$$\mathcal{L}^n := \{H\subset \R^n : H\ \text{Lebesque-mérhető}\}.$$

**Fontos tények:**
- $\mathcal{L}^n$ valóban $\sigma$-algebra, és $\lambda_n := \lambda_n^*\big|_{\mathcal{L}^n}$ mérték rajta.
- $\mathcal{B}(\R^n) \subset \mathcal{L}^n$ (minden Borel-halmaz Lebesque-mérhető).
- $\lambda_n$ teljes: ha $\lambda_n(N)=0$ és $A\subset N$, akkor $A\in\mathcal{L}^n$ és $\lambda_n(A)=0$.

### Lebesque-Stieljes mérték

Legyen $f: \R \to \R$ **monoton növekvő** (nemcsökkenő) és **jobbról folytonos**. Ekkor a félgyűrűn
$$\mathcal{I}:=\{(a,b] : -\infty < a < b < \infty\}$$
adott
$$\mu_f((a,b]) := f(b) - f(a)$$
egy **előmértéket** (premeasure) ad.

**Tétel (kiterjesztés):** $\mu_f$ egyértelműen kiterjeszthető a $\sigma(\mathcal{I})$-re (ez a Borel-$\sigma$-algebra $\mathcal{B}(\R)$), így kapunk egy Borel-mértéket, a (Lebesque–)Stieltjes-mértéket. A teljes mértéktér a szokásos módon a $\mu_f$ szerinti kompletten (nullhalmazok részhalmazainak hozzávételével) állítható elő.

**Hasznos képletek / megjegyzések:**
- Általában $\mu_f(\{a\}) = f(a) - f(a-)$, ahol $f(a-):=\lim_{x\uparrow a} f(x)$ (az „atom” nagysága).
- Ha $f$ folytonos, akkor $\mu_f$ atommentes (nincsenek pozitív tömegű pontok).
- Példa: $f(x)=x$ esetén $\mu_f = \lambda$ (a Lebesque-mérték $\R$-en).

**The Bright Side of Mathematics vidik**: 
- [Lebesque mérték](https://youtu.be/7O7qPrNIt7w?t=852&si=j4vxLnAO6Dx9XJWC)
- [Lebesque-Stieljes mérték](https://youtu.be/IsmgLGVpLpQ?si=rNoRbBoMjnO0qJ-g)
- [Külső mértékek 1.](https://youtu.be/LC-9KzxVoWI?si=7Q91X0ORbRqdFcav)
- [Külső mértékek 2.](https://youtu.be/e8yg3FtjO5s?si=G4dsGltlNrT0WEwH)
- [Külső mértékek 3.](https://youtu.be/iA6ATJFViUs?si=iWtzaH82o7FhTFRg)

## IV. Riemann-, Riemann-Stieljes integrál, modern kontextusban. Mértéktartó leképezések

Ez a fejezet hidat épít a klasszikus integrálok (Riemann, Riemann–Stieltjes) és a mértékelméleti nézőpont között: ugyanazok a fogalmak más absztrakciós szinten jelennek meg. Vizsgán fontos érteni, hogy a Stieltjes-integrál természetes módon kapcsolódik a Stieltjes-mértékhez. A mértéktartó leképezések pedig azt formalizálják, mikor „nem változik” a mérték (és így az integrál) egy transzformáció alatt.

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

A $f$ függvényt Riemann–Stieltjes integrálhatónak nevezzük $g$ szerint, ha $\sup\{ L(f,g,P): P \}$ = $\inf\{ U(f,g,P): P \}$. Ekkor az integrál értéke:

$\int_a^b f(x) \; dg(x) = \sup\{ L(f,g,P): P \} = \inf\{ U(f,g,P): P \}$

### Mértéktartó leképezések

$(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha:

 $\forall B \in \mathcal{N}: f^{-1}(B) \in \mathcal{M}$ és $\mu(f^{-1}(B)) = \nu(B)$

 Tulajdonságok:
- Legyen $h: Y \mapsto \R$, és $f: X \mapsto Y$ mértéktartó, ha $\int_x h \; d\mu = \int_y h \; d\nu$
- $(X, \mathcal{M}, \mu) \xrightarrow{f} (Y, \mathcal{N}, \nu)$ mértéktartó leképezés, ha $h: Y \mapsto \R$ mérhető, akkor $h \circ f: X \mapsto \R$ is mérhető és $\int_X h \circ f \; d\mu = \int_Y h \; d\nu$


## V. Előjeles mértékek és variációik, felbontások

Az előjeles mértékekkel már nem csak „tömeget” mérünk, hanem pozitív és negatív hozzájárulások is lehetnek. A teljes variáció (|μ|) azért lényeges, mert ezzel lehet normálisan „nagyságot” rendelni egy előjeles mértékhez, és integrálási becsléseket ad. A Hahn- és Jordan-felbontás a vizsga szempontjából alap: minden előjeles mérték felbontható pozitív részek különbségeként, jól kontrollált módon.

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

Ez a fejezet a „sűrűség” fogalmát teszi precízzé: a Radon–Nikodym tétel megmondja, mikor írható egy mérték egy másikhoz képest integrálható függvénnyel (deriválttal). A Lebesgue-felbontás pedig azt mondja ki, hogy egy mérték egy abszolút folytonos és egy szinguláris részből áll össze, és ez a felbontás egyértelmű. A mértékek differenciálása (alsó/felső derivált) a lokális arányokból nyeri vissza a sűrűséget.

### Abszolút folytonos és szinguláris mértékek

**Abszolút folytonos mérték**:

$\alpha$ mérték abszolút folytonos $\beta$ mértékhez képest, ha

$\forall A \in \mathcal{M}, \beta(A) = 0 \mapsto \alpha(A) = 0$. Jelölése: $\alpha \ll \beta$

- A halmazok amik 0-ák $\beta$-ra, azok $\alpha$-ra is 0-ák

- Jele: $\alpha \ll \beta$

**Szinguláris mérték**:

$\alpha$ és $\beta$ mérték szingulárisak egymáshoz képest, ha van $X = A \cup B$ diszjunkt halmazok és $\alpha(B) = \beta(A) = 0$. Jelölése: $\alpha \perp \beta$. $A$ csak az $\alpha$-nak, $B$ csak a $\beta$-nak a hordozója.

### Lebesque-felbontási tétel

Adott egy $\nu$ akár előjeles és egy $\mu$ hagyományos mérték, mindkettő $\sigma$-additív. Ekkor létezik olyan $\alpha$ és $\beta$ mérték, hogy

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

Adott $\alpha \ll \beta$ mértékek és $h \in L^1(\beta)$ és $f = \frac{d\alpha}{d\beta}$, akkor:

$\int_H h \; d\alpha = \int_X h \cdot f \; d\beta = \int_H h \frac{d\alpha}{d\beta} \; d\beta$

**Előjeles mérték szerinti integrálás**:

Adott $\nu \ll \tau$  előjeles mérték, $h \in L^1(\tau)$ és $f: X \to \overline \R$ mérhető függvény, akkor:

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

Legyen $\nu$ lokálisan véges, előjeles Borel-mérték és van egy $\nu = \int f \; d\mu$ felbontása, ahol $f \in L^1(\mu)$, akkor $\mu$-szer majdnem minden $x$-re:

$\underline{D}_\mu \nu(x) = \overline{D}_\mu \nu(x) = f(x)$

- $\mu$ majdnem minden $x$-re létezik a derivált és az egyenlő $f(x)$-el
- $D_\mu \nu(x) = f(x)$ visszaadja a Radon-Nikodym deriváltat

**The Bright Side of Mathematics vidik**: 
- [Radon-Nikodym tétel és Lebesque felbontás](https://youtu.be/12kFDeN6xuI?si=5LAAf9_PP6JjGB9a)

## VII. Korlátos változású, absz folyt. és szinguláris függvények, felbontásuk, differenciálásuk

Itt a mértékekről visszafordulunk függvényekhez: egy korlátos változású (BV) függvényhez természetesen társul Lebesgue–Stieltjes mérték, és a tulajdonságok mértékelméletileg jól kezelhetők. A vizsgán tipikusan a BV → „monoton különbsége”, illetve az abszolút folytonos/szinguláris felbontás és a majdnem mindenütt vett deriválhatóság a kulcs. Intuíció: az abszolút folytonos rész „integrálható deriváltból” jön, a szinguláris rész pedig nullmértékű halmazon koncentrálódik.

### Korlátos változású függvények

Adott $f: I \mapsto \R$ függvény, ekkor az $f$ korlátos változású, ha létezik olyan $M \ge 0$, hogy minden felosztásra $I = \{ x_0, x_1, ... , x_n \}$, ahol $a = x_0 \lt x_1 \lt ... \lt x_n = b$ teljesül:

$\tau_f(I) = \sup \{ \sum_{i=1}^{n} \vert f(x_i) - f(x_{i-1}) \vert: n \ge 1, x_0 < x_1 < ... < x_n \in I \} \le \infty$

Azaz feldarabolva az $I$ intervallumot, a függvényértékek különbségeinek összege felülről korlátos, vagyis supremuma véges.

$f: I \mapsto \R$ akkor és csak akkor korlátos változású, ha $f = f_1 - f_2$, ahol $f_1, f_2$ véges, monoton növekvő függvények.

### Abszolút folytonos függvények

Egy $f: I \mapsto \R$ függvény abszolút folytonos, ha bármely diszjunkt intervallum családra, melynek összhossza (Lebesque mértéke) kisebb, mint egy adott $\delta$ érték, a függvényértékek különbségeinek összege kisebb, mint egy adott $\epsilon$ érték.

$\forall \epsilon \gt 0 \; \exists \delta \gt 0$ úgy, hogy bármely diszjunkt intervallum családra $\{ (a_i, b_i) \}$, ahol $\sum (b_i - a_i) \lt \delta$, teljesül: $\sum \vert f(b_i) - f(a_i) \vert \lt \epsilon$

- $\vert b_i - a_i \vert = \lambda(I_i)$, ahol $\lambda$ a Lebesque-mérték
- $\vert f(b_i) - f(a_i) \vert = \mu_f(I_i)$, ahol $\mu_f$ a $f$-hez tartozó Lebesque–Stieltjes mérték

**Tétel:** Korlátos változású függvény Lebesque–Stieltjes mértéke majdnem minden pontban differenciálható, és a derivált integrálja visszaadja a függvényt.

### Szinguláris függvények

Egy $f: I \mapsto \R$ függvény szinguláris, ha korlátos változású és létezik olyan $N \subset I$ halmaz, melynek Lebesque mértéke $0$, és $f$ csak ezen a halmazon változik.

### Korlátos változású függvények

Legyen $f: I \mapsto \R$ függvény, ekkor léteznek olyan $f_{1}, ..., f_n: I \mapsto \R$ korlátos változású függvények, hogy:
- $f = \sum_{i=1}^n f_i$
- $f$ korlátos változású $\iff$ minden $f_i$ korlátos változású
- Tagonként lehet deriválni m.m. x-en, és az eredmény a teljes függvény deriváltja lesz m.m. x-en

### Luzin tulajdonságú függvények

Olyan halmazfüggvények, amik minden nullmértékű halmazt nullmértékű halmazra képeznek.

$\lambda(A) = 0 \implies \lambda(f(A)) = 0$

### Abszolút folytonos függvények 2.

Ha létezik $f$ mérhető függvény és $f'$ véges minden $x \in H$-en, akkor:
- $f'$ mérhető
- $\lambda(f(H)) = \int_H \vert f' \vert \; d\lambda$, azaz a mértéke felülről becsülhető a derivált abszolútértékének integráljával $H$-n
- $\lambda(f(H)) \lt \int_H \vert f'' \vert \; d\lambda$, ha $f''$ létezik és véges minden $x \in H$-en, vagyis a függvény mértéke kisebb lesz, mint a második derivált abszolútértékének integrálja $H$-n


$f$ függvény pontosan akkor lesz abszolút folytonos, ha van egy $g$ függvény, amire igaz, hogy $f$ megváltozása $g$ integráljával egyenlő minden intervallumon.

$f(y)-f(x) = \int\limits_{[x,y]} g(t) \, d\lambda(t), \; \forall x \le y \in I$

Ez akkor is érvényes, ha $f$ deriválható és $f' = g$ majdnem minden pontban. Abszolút folytonosság $\iff$ deriválhatóság majdnem minden pontban és a függvény visszaállítása a derivált integráljával.

### Lipschitz-folytonos függvények

Legyen $f: I \mapsto \R$ függvény, akkor Lipschitz-folytonos, ha létezik olyan $K \gt 0$ konstans, hogy minden $x,y \in I$-re:

$\vert f(x) - f(y) \vert \le K \cdot \vert x - y \vert$, ahol $K$ a Lipschitz-állandó.

Ha korlátos változású a függvény, akkor felbontható abszolút folytonos és szinguláris részre.

## VIII. Mértékek szorzata

Ez a fejezet azt magyarázza meg, hogyan építünk mértéket szorzattéren úgy, hogy a „téglákon” a természetes szorzatképlet adódjon. A konstrukció csúcspontja a Fubini-tétel: megfelelő feltételek mellett a többszörös integrál felbontható iterált integrálokra, és a sorrend felcserélhető. Vizsgán fontos, hogy lásd a feltételeket (pl. $L^1$-integrálhatóság) és a következményt (mérhetőség + egyenlőségek).

**Intuíció**:

Legyen két mérhető térünk $(X, \mathcal{M}, \mu)$ és $(Y, \mathcal{N}, \nu)$. Ekkor a két tér szorzata egy új mérhető teret hoz létre, ahol a halmazok a két eredeti tér halmazainak szorzataként értelmezhetők. A mértékek szorzata pedig egy új mértéket definiál ezen a szorzat téren, amely a két eredeti mérték kombinációját tükrözi.

Legyen a két mérhető tér szorzata pl. egy mérhető tégla, ekkor $\mathcal{T} = \{ A \times B \}$, ahol $A \in \mathcal{M}, B \in \mathcal{N}$. Ekkor a szorzatmérték a következőképpen definiálható:

$\alpha(\mathcal{T}) = \alpha(A \times B) = \mu(A) \cdot \nu(B)$

Tétel: $\alpha$ $\sigma$-additív $\mathcal{T}$-re.

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

Adott $(X, \mathcal{M}, \mu)$ és $(Y, \mathcal{N}, \nu)$ és az általuk alkotott szorzatmértékes tér $(Z, \mathcal{S}, \varphi)$ esetén, ha $f \in L^1(\varphi)$ (pl. $\int_Z \lvert f \rvert \, d\varphi < \infty$), akkor:

$g(x) = \int_Y f(x,y) \; d\nu(y)$ m.m. mérhető és $g \in L^1(\mu)$, továbbá:

$\int_Z f(x,y) \; d\varphi(x,y) = \int_X g(x) \; d\mu(x)$

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
