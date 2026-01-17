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

**Gyakoriságok $\chi^2$ asszimptotája:**

Legyen $A_1, ..., A_r$ teljes eseményrendszer, $P(A_i) = p_i, \; i = 1, ..., r$, a mintában $A_i \, k_i$-szer teljesül, azaz összesen $n$ mintaelemünk van.

$p_1, ..., p_r$ valószínűségekkel és $n$ elemű független mintából az egyes események gyakorisága legyen $n_1, ..., n_r$. Ekkor:

$\chi^2 = \sum\limits_{i=1}^{r} \frac{(n_i - n p_i)^2}{n p_i} \xmapsto{eloszlásban} \chi^2_{r-1}$, ha $n \to \infty$

### Diszkrét illeszkedésvizsgálat

$n$ db osztályzott mefigyelésünk van, ahol $r$ db osztályba sorolva, $n_1, ..., n_r$ gyakoriságokat kapunk. Az elméleti valószínűségek $p_1, ..., p_r$ adottak.

Hipotézisek:
- $H_0$: Az eloszlás megfelel az elméletinek, azaz $P(A_i) = p_i, \; i = 1, ..., r$
- $H_1$: Az eloszlás nem felel meg az elméletinek

Próbafüggvény:

$\chi^2 = \sum\limits_{i=1}^{r} \frac{(n_i - n p_i)^2}{n p_i} \sim \chi^2_{r-1}, \; n \to \infty$

Kritikus tartomány: $\mathcal{X}_k = \{ x : \chi^2 \gt \chi^2_{r-1}(\alpha) \}$, $\alpha$ kritikus érték mellett.

Ökölszabály: Ha $n_i \lt 5$, akkor vonjuk össze az osztályokat.

### Becsléses illeszkedésvizsgálat

Ha $p_i$-k becsült valószínűségek valamilyen paramétercsaládból arra is végezhetünk illeszkedésvizsgálatot.

Legyen $A_1, ..., A_r$ teljes eseményrendszer, ahol $P_{\vartheta}(A_i) = p_i(\vartheta), \; i = 1, ..., r$, a mintában $A_i \, k_i$-szer teljesül, azaz összesen $n$ mintaelemünk van. $\vartheta \isin \Theta \mapsto \R^s$ ;és $\hat \vartheta$ ML becslőfüggvény, ami $\hat \vartheta = \varphi(n_1, ..., n_r)$ becslést ad a valódi $\vartheta$ paraméterre és $\hat p_i = p_i(\hat \vartheta)$.

Próbafüggvény:

$\chi^2 = \sum\limits_{i=1}^{r} \frac{(n_i - n \hat p_i)^2}{n \hat p_i} \xmapsto{eloszlásban} \chi^2_{r - s - 1}, \; n \to \infty$

Hipotézisek:
- $H_0$: Az eloszlás megfelel az elméletinek, azaz $P_{\vartheta}(A_i) = p_i(\vartheta), \; i = 1, ..., r$
- $H_1$: Az eloszlás nem felel meg az elméletinek

### Diszkrét homogenitásvizsgálat

Van két mintánk az $r$ osztályozás szerint: $n_1, ..., n_r$ és $m_1, ..., m_r$ gyakoriságokkal, összesen $n$ és $m$ mintaelemmel. Kérdesünk: Ugyan olyan eloszlásból származnak-e a minták?

Hipotézisek:
- $H_0$: A két minta ugyan olyan eloszlásból származik
- $H_1$: A két minta nem ugyan olyan eloszlásból származik

Próbafüggvény:

$\chi^2 = n \cdot m \sum \limits_{i=1}^{r} \frac{( \frac{n_i}{n} - \frac{m_i}{m} )^2}{n_i + m_i} \xmapsto{eloszlásban} \chi^2_{r-1}, \; n, m \to \infty$

**Folytonos eloszlások illeszkedésvizsgálata:**

Diszkretizálás: $r$ db diszjunkt osztályra feldaraboljuk az eseményterünket és így alkalmazzuk a diszkrét illeszkedésvizsgálatot.

De így információt vesztünk, ezért beírjuk $x$-et a saját folytonos eloszlásfüggvényébe, ekkor $F(x) \sim U(0,1)$ lesz. Így visszatranszformáltuk az egyfajta véletlen változóvá.

### Kolgomorov próbák

**Kolmogorov-Smirnov próba:**

Van egy $\hat F_n$ tapasztalai és $F$ elméleti eloszlásfüggvényünk.

Próbafüggvények:

- $D_n^+ = \sup\limits_{x \in \R} ( \hat F_n(x) - F(x) )$

- $D_n^- = \sup\limits_{x \in \R} ( F(x) - \hat F_n(x) )$

- $D_n = \sup\limits_{x \in \R} | \hat F_n(x) - F(x) |$

Vagyis a legnagyobb eltérés az elméleti és a tapasztalati eloszlásfüggvény között.


**Kolmogorov eloszlás illeszkedésvizsgálatra:**

Ha $F$ valódi eloszlásfüggvény, akkor:

$D_n^+$-re: $\lim \limits_{n \to \infty} P( \sqrt{n} D_n^+ \le Y ) = 1 - e^{-2 Y^2}$

$D_n$-re: $\lim \limits_{n \to \infty} P( \sqrt{n} D_n \le Y ) = 1 - 2 \sum \limits_{k=1}^{\infty} (-1)^{k} e^{-2 k^2 Y^2}$

Hipotézisek:
- $H_0$: Az eloszlás megfelel az elméletinek, azaz $F$ az elméleti eloszlásfüggvény
- $H_1$: Az eloszlás nem felel meg az elmélet

Kritikus tartomány: $\mathcal{X}_e = \{ x : \sqrt{n} D_n \gt D(\alpha) \}$, ahol $D(\alpha)$ a kritikus érték.


**Kolmogorov eloszlás homogenitásvizsgálatra:**

Van két minta, amikhez tartozó tapasztalati eloszlásfüggvények: $\hat F_n$ és $\hat G_m$. Ugyan olyan eloszlásból származnak-e a minták?

Próbafüggvény:

$D_{n,m} = \sup\limits_{x \in \R} | \hat F_n(x) - \hat G_m(x) |$

$\lim \limits_{n, m \to \infty} P( \sqrt{\frac{n \cdot m}{n + m}} D_{n,m} \le Y )$ Kolmogorov eloszlásfüggvénye

Hipotézisek:
- $H_0$: A két minta ugyan olyan eloszlásból származik
- $H_1$: A két minta nem ugyan olyan eloszlásból származik

## X. Lineáris modell, Lineáris hipotézis normális lineáris modellben

Legyen $y$ egy $n$ dimenziós normális vektor, $x$ egy $n \times p$ mátrix, $\beta$ egy $p$ dimenziós vektor és $\varepsilon$ hibatag egy $n$ dimenziós normális vektor, ahol $\mathbb{E}(\varepsilon_i) = 0, \; \text{Var}(\varepsilon_i) = \sigma^2$ és $\mathbb{E}(\varepsilon_i \varepsilon_j) = 0$ ha $i \neq j$.

### A lineáris modell:

$y = X \beta + \varepsilon$

OLS: Ordinary Least Squares, azaz a legkisebb négyzetek módszere, ami a hibatag négyzetösszegét minimalizálja:

$\Vert \varepsilon \Vert^2 = \Vert y - X \beta \Vert^2 \to \min_{\beta}$

### Gauss-Markov egyenlet:

Ha $X$ teljes rangú, akkor az OLS becslő:

$\hat \beta = (X^T X)^{-1} X^T y$

### Próbafüggvények lineáris hipotézisek vizsgálatára:

Adott egy lineáris modell, ekkor $\hat y = X \hat \beta$ az OLS becslés a várható értékre és $\hat \varepsilon = y - \hat y$ a becsült hibatag.

**t-próba**

Hipotézisek:
- $H_0$: $\hat \beta = 0$
- $H_1$: $\hat \beta \ne 0$

Próbafüggvény:

$t = \frac{\hat \beta_j}{s_n^* \cdot \sqrt{a_{jj}}} \sim t_{n-p}$

Kritikus tartomány:
- Kétoldali próba: $\mathcal{X}_e = \{ x : |t| \gt t_{n-p, \alpha/2} \}$

**F-próba**

Hipotézisek:
- $H_0$: A lineáris hipotézis igaz
- $H_1$: A lineáris hipotézis hamis

Próbafüggvény:

$F = \frac{( \text{RSS}_0 - \text{RSS} ) / q}{\text{RSS} / (n - p)} \sim F_{q, n-p}$

Ahol $\text{RSS}_0$ a nullhipotézis alatti maradék négyzetösszeg, $\text{RSS}$ a teljes modell maradék négyzetösszeg, $q$ a lineáris hipotézis szabadságfoka, $p$ a modell paramétereinek száma és $n$ a minta mérete.

Kritikus tartomány: $\mathcal{X}_e = \{ x : F \gt F_{q, n-p}(\alpha) \}$, ahol $q$ a lineáris hipotézis szabadságfoka.
