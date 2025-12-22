*Készítette: Dittrich Levente, 2025*

többi vidi:
- [Negyedik előadás](https://youtu.be/o2uHHnHpi0c?si=Ulw4zSMNANNtUYGK)
- [Ötödik előadás](https://youtu.be/RT-_aTsoUiU?si=1voF8UZPWMwMgmcM)
- [Hatodik előadás](https://youtu.be/rxe9meZ_U_4?si=-lw57oZYsXkVmY-p)
- [Hetedik előadás](https://youtu.be/UxXO897rMFY?si=CTL90wsZ-2FZUjEZ)
- [Nyolcadik előadás](https://youtu.be/va36j0_Pvsc?si=2UVW7EzGmNYT4n85)
- [Kilencedik előadás](https://youtu.be/fDVl9W8NtyM?si=P8GizxJ7fuxF4T4Y)
- [Tizedik előadás](https://youtu.be/QvnxFoF7Vi0?si=rsakZAkJHmbU3j0_)
- [Tizenegyedik előadás](https://youtu.be/wngnbELDnmg?si=_0GUgF7eteBHSMXc)
- [Tizenkettedik előadás](https://youtu.be/KYoly4FVF3E?si=AAWg8H28boo8hO6Y)


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

$\alpha: \mathcal{A} \rarr \reals$ halmazfüggvény, feltevések:
- $\empty \in \mathcal{A}$ (tartalmazza az üreshalmazt)
- $\alpha \ge 0$ (nemnegatív)
- $\alpha(\empty) = 0$ (üreshalmaz mértéke 0)

Típusok:
- **$\alpha$ monoton**, ha: $A, B \in \mathcal{A}$ és $A \subset B$, akkor $\alpha(A) \le \alpha(B)$
- **$\alpha$ additív**, ha: $A_1, A_2, ... , A_n \in \mathcal{A}$ halmazokra $\cup_{k=1}^{n} A_k \in \mathcal{A}$ esetén $\alpha(\cup_{k=1}^{n} A_k) = \sum_{k=1}^{n} \alpha(A_k)$
- **$\alpha$ $\sigma$-additív**, ha: $A_1, A_2, ... \in \mathcal{A}$ halmazokra $\cup_{k=1}^{\infty} A_k \in \mathcal{A}$ esetén $\alpha(\cup_{k=1}^{\infty} A_k) = \sum_{k=1}^{\infty} \alpha(A_k)$

### Mérhető tér

$(X, \mathcal{A})$ mérhető tér, ha $\mathcal{A} \in \mathcal{P}(X)$ $\sigma$-algebra. Ekkor \mathcal{A} elemei mérhető halmazok.

### Mérhető leképezés

Adott $(X, \mathcal{M})$ és $(Y, \mathcal{N})$ mérhető terek, az $f: X \rarr Y (\mathcal{M}, \mathcal{N})$ mérhető leképezés. Ekkor $\{ A \subset Y: f^{-1}(A) \in \mathcal{M} \}$ az halmazrendszer $\sigma$-algebra $Y$-on.

### Egyszerű függvények

Legyen $(X, \mathcal{M})$ mérhető tér, ekkor az $f: x \rarr \reals$ leképezést egyszerű függvénynek nevezzük, ha mérhető és értékkészlete véges. Ha $f,g$ egyszerű függvény, akkor $f+g$, $f \cdot g$, $max(f,g)$, $min(f,g)$ is egyszerű függvény.

### Mérték

Legyen (X, \mathcal{M}) mérhető tér, a $\mu: \mathcal{M} \rarr \overline\reals$ leképezést mértéknek nevezzük, ha
1. $\mu \ge 0$
2. $\mu(\empty) = 0$
3. $H_n \in \mathcal{M}, H_n \cap H_k = 0$ esetén $\mu(\cup_{i=1}^{\infty} H_i) = \sum_{i=1}^{\infty} \mu(H_i)$


**The Bright Side of Mathematics vidik**: 
- [$\sigma$-algebra](https://youtu.be/xZ69KEg7ccU?si=C9r1hWmVKRvSQdif)
- [Borel $\sigma$-algebra](https://youtu.be/z5m6HXKx0Wo?si=CTafKwAV9K5xf1TA)
- [Mérhető terek](https://youtu.be/11heoNVavvM?si=siO9Wsuj485i5DWe)
- [Mértékek](https://youtu.be/7O7qPrNIt7w?si=k13l2xuJWvkvXic2)

## II. Integrál, függvénysorozatok, függvénysorok és integráljaik


## III. Mértékek kiterjesztése. Lebesque- és Lebesque-Stieljes mérték


## IV. Riemann- , Riemann-Stieljes integrál, modern kontextusban. Mértéktartó leképezések


## V. Előjeles mértékek és variációik, felbontások


## VI. Abszolút folytonos és szinguláris mértékek, Lebesque-felbontás, Radon-Nikodym tétel, mértékek differenciálása


## VII. Korlátos változású, absz folyt. és szinguláris függvények, felbontásuk, differenciálásuk


## VIII. Mértékek szorzata



# Valószínűségszámítás

## I. Valószínűségi mezők, változók, alapvető objektumok. Eloszlások, sűrűségfüggvények, transzformációk spec esetei, Doob Lemma

### Valószínűségi mező

$(\Omega, \mathcal{A}, P)$ mértéktér, ahol
- $\Omega$ az (elemi) eseménytér, ez egy mérhető $\sigma$-algebra
- $\mathcal{A}$ a megfigyelhető események halmazrendszere 
- $P$ valószínűségi mérték, $P \in [0,1]$ és $P(\Omega) = 1$

### Valószínűségi változó

$x: \Omega \rarr \reals$ valamilyen eseménytérből $(\mathcal{X}, B)$ mérhető térbe képező mérhető függvény.

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

- szorzattérbe képez ~ peremeloszlás

- több változónál $x_i = \pi_i \cdot x$ függvény $x$ marginálisa, $Q_{x_i}$ marginális eloszlása. 

### Eloszlásfüggvények

$F_x$ meghatározza $Q_x$-et.

Valós eset: $x \in \reals^n$

- $n=1$ esetén:
    - $Q_x$ meghatározásához elég $Q_x((-\infty, t)) = P(X \lt t) \coloneqq F_x(t) \rarr$ eloszlásfüggvény a $t$ helyen
- $n \gt 1$ esetén:
    - $Q_x((-\infty, t_1) \times (-\infty, t_2) \times ... \times (-\infty, t_n)) = P(x_1 < t_1, ... , x_n < t_n) \coloneqq F_x(t_1, ..., t_n)$

#### Tulajdonságok



### Sűrűségfüggvények



### Változók transzformációi


### Doob Lemma


### Sűrűségfüggvény spec. esetei


## II. Függetlenség, kapcsolat eloszlással, asszimptotikus állítások, Kolgomorov 1-0, Borell-Cantelli, Konvolúció


## III. Várható érték, magasabb momentumok, kapcsolódó egyenlőtlenségek


## IV. Valószínűségi változók konvergenciája, 1 valószínűség, $L_p$-beli sztochasztikus konvergencia, kapcsolatok és eszközei


## V. Valószínűségi változók gyenge és eloszlásbeli konvergenciája, karakterisztikus függvény


## VI. Nagy számok gyenge és erős törvényei, független sorok


## VII. Centrális határeloszlás tétel változatai


## VIII. Feltételes várható érték és tulajdonságai, feltételes eloszlás


## IX. Martingálok tulajdonságai, Doob-felbontás, kanonikus növekvő folyamata, megállás idő


## X. Martingálok konvergancia tételei, nagy-eltérés tételek


# Statisztika

## I. Statisztikai mező, alapfogalmak. Tapasztalati becslések


## II. Dominált statisztikai mező, elégséges statisztikák


## III. Többdimenziós norm. eloszlás, nemcentrális Khi-négyzet eloszlás


## IV. Becslések elmélete, Blackwell-izálás


## V. Fisher-információ és regularitás-feltételek


## VI. Információs határ, MM és ML módszerek


## VII. Hipotézisvizsgálat alapjai, likelihood-hányados próba egyszerű hipotéziseknél


## VIII. Normális eloszlás paramétereire vonatkozó próbák


## IX. Khi-négyzet próbák illeszkedésvizsgálatra és következményeik. Folytonos illeszkedésvizsgálat


## X. Lineáris modell, Lineáris hipotézis normális lineáris modellben

