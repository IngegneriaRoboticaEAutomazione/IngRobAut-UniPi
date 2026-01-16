# Formulario di P.P.S

Creato da: @Elefantino - @Mova801 - @Deda404

- [Formulario di P.P.S](#formulario-di-pps)
  - [Densità Discreta](#densità-discreta)
  - [Densità Continua](#densità-continua)
  - [Composizione Tramite Funzione](#composizione-tramite-funzione)
  - [Teorema del Cambio di Variabile](#teorema-del-cambio-di-variabile)
  - [Variabile Congiunta](#variabile-congiunta)
  - [Formula di Bayes per Densità Continue](#formula-di-bayes-per-densità-continue)
  - [INDICATORI CARATTERISTICI](#indicatori-caratteristici)
    - [Funzione Cumulativa (CDF)](#funzione-cumulativa-cdf)
    - [Funzione di Sopravvivenza (SUR)](#funzione-di-sopravvivenza-sur)
    - [Mediana](#mediana)
    - [Quantile](#quantile)
    - [Valor Medio](#valor-medio)
    - [PROPRIETA' DEL VALOR MEDIO](#proprieta-del-valor-medio)
      - [Formula disintegrazione del valor medio](#formula-disintegrazione-del-valor-medio)
      - [Linearità del valor medio](#linearità-del-valor-medio)
      - [Monotonia del valor medio](#monotonia-del-valor-medio)
      - [Disuguaglianza di Markov](#disuguaglianza-di-markov)
      - [Valor Medio Variabile Composta](#valor-medio-variabile-composta)
    - [Varianza](#varianza)
    - [Deviazione Standard](#deviazione-standard)
    - [Covarianza](#covarianza)
    - [Matrice delle Covarianze](#matrice-delle-covarianze)
  - [Momenti](#momenti)
  - [Funzione Generatrice dei Momenti (MGF)](#funzione-generatrice-dei-momenti-mgf)

---

## Densità Discreta

Si dice: "Densità discreta di Probabilità di X" la funzione che ad ogni valore di $x \in \mathbb{E}$ associa la probabilità che $x=X$.  

$$x \to P(X=x|I)$$

*Nota:* La Densità discreta assume valori su $[0,1]$ quindi deve essere tale che $\sum_{x \in E} P(X=x|I)=1$.

Elenchiamo di seguito alcune formule utili per la Densità Discreta:

1. Variabile Aleatoria Costante: $P(X=x|I)=1$
2. Densità Discreta Uniforme: $P(X=x|I)=1/n$
3. Bernulli: Se $x$ ha valori in $[0,1]$ allora
   - caso: $P(X=0|I)=1-P$
   - caso: $P(X=1|I)=P$
4. Densità Binomiale: $P(X=x|I)=\binom{n}{k} p^k (1-p)^{n-k}$
5. Densità di Poisson: $P(X=x|I)=e^{-\lambda}\frac{\lambda^k}{k!}$
6. Esponenziale: per $\lambda = 1/n$
   - $P(X=x|I)=\lambda e^{-\lambda x}$
7. Gaussiana: $P(X=x|I)=\frac{1}{\sigma \sqrt{2 \pi}} e^{-\frac{(x-\mu)^2}{2 \sigma^2}}$

---

## Densità Continua

Se $X$ è una variabile aleatoria a valori in $\mathbb{R}$, e sia $f:\mathbb{R} \to [0,\infty[$ , una funzione integrabile tale che:
$$\int_{-\infty}^{+\infty} f(x) dx = 1$$  
Si dice che $X$ ha denistà continua se vale per ogni interballo $[a,b] \subseteq \mathbb{R}$:
$$P(a \leq X \leq b | I) = \int_{a}^{b} f(x) dx$$
*Nota:* Notazione usata: $f(x) = P(X=x|I)$

---

## Composizione Tramite Funzione  

Se $X$ è una variabile aleatoria a valori in $E$ e $g: E \to F$ è una funzione, si definisce la variabile aleatoria $g(X)$ a valori in $F$ tramite il sistema di alternative per $z \in F$:
$$(g(X)=z|I) = (X \in g^{-1}(z)) $$  

---

## Teorema del Cambio di Variabile

Sia $X$ una variabile aleatoria a valori in $\mathbb{R}$ con densità continua $P(X=x|I)$.  
Sia $g$ una funzione derivabile con derivata continua e mai nulla, allora $g(x)$ ammette densità continua e vale:
$$P(g(X)=z|I) = P\left(X = g^{-1}(z) | I\right) \cdot \frac{1}{|g'(g^{-1}(z))|}$$  

---

## Variabile Congiunta

L'evento dove due variabili aleatorie $X$ e $Y$ assumono rispettivamente i valori $x$ e $y$ si indica con:
$$P((X,y)=(x,y)) = P(X=x,Y=y)$$  
Le leggi marginali sono :  

- $P(X=x)$
- $P(Y=y)$

Prese separatamente.

La legge congiunta è la densità: $P(X=x,Y=y)$ , che associa ad ogni coppia $(x,y)$ la probabilità che $X=x$ e $Y=y$ (come si comportano insieme).

*Nota:* Se conosco le marginali non è detto che io possa dire nulla sulla congiunta.

Come si risolve questo problema?
Usando la regola del prodotto:
$$P((X,Y)=(x,y)) = P(X=x,Y=y)$$
$$ \implies P(X=x) P(Y=y|X=x)$$

---

## Formula di Bayes per Densità Continue

$$ P(X=x|Y=y) = \frac{P(X=x) P(Y=y|X=x)}{P(Y=y)}$$

ed è proporzionale a:
$$ \propto P(X=x) L(X=x,Y=y)$$

---

## INDICATORI CARATTERISTICI

### Funzione Cumulativa (CDF)

La funzione cumulativa di $X$ è definita come la funzione che ad ogni valore $ x |in \mathbb{R}$ associa la probabilità che $X\leq x$:  
$$ x \to CDF_X(x) = P(X \leq x | I) $$  

---

### Funzione di Sopravvivenza (SUR)

E' una funzione che ad ogni valore di $x \in \mathbb{R}$ associa la probabilità che $X \geq x$:
$$ x \to SUR_X(x) = P(X \geq x | I) $$

*Not:* CDF e SUR sono collegate dalla relazione:
$$CDF_X(x) + SUR_X(x) = 1$$

La CDF_X si ottiene sommando o integrando la densità su tutti i possibili valori di $X \leq x$:

- Discreta:  
$$ CDF_X(x) = \sum_{x_i \leq x} P(X=x_i|I) $$  

- Continua:  
$$ CDF_X(x) = \int_{-\infty}^{x} f(z) dz $$

La SUR_X si ottiene sommando o integrando la densità su tutti i possibili valori di $X \geq x$:

- Discreta:  
$$ SUR_X(x) = \sum_{x_i \geq x} P(X=x_i|I) $$

- Continua:  
$$ SUR_X(x) = \int_{x}^{+\infty} f(z) dz $$  

---

### Mediana

La mediana è definita come un valore $\bar{x} \in \mathbb{R}$ (se esiste) tale che:
$$ CDF_X(\bar{x}) = \frac{1}{2} $$

---

### Quantile

La funzione Quantile, è definita come: $\bar{x} = CDF_X^{-1}(\frac{1}{2})$ , il fatto che la $CDF_X$ non è invertibile fa introdurre il concetto di quantile di $X$ come:
$$ q_x : (0,1) \to \mathbb{R} $$
ed è una funzione che ad ogni possibile $\alpha \in (0,1)$ associa il valore:
$$ q_x(\alpha) = \min{x \in \mathbb{R} | (CDF_X(x) \geq \alpha)} $$
detto quantile di $X$ di livello $\alpha$, si può dimostrare che vale: $\forall \alpha \in (0,1)$ .  
Se $X$ ha densità continua: $CDF_X(q_x(\alpha)) = \alpha$ .

---

### Valor Medio

Il valor medio di una variabile aleatoria $X \in \mathbb{R}$ condizionato a un informazione nota $I$ rispetto alla quale $X$ ammette densità, è definito come:

- Discreta:

$$ E(X|I) = \sum_{x \in E} x P(X=x|I) $$

- Continua:

$$ E(X|I) = \int_{-\infty}^{+\infty} x f(x) dx $$

*Nota:* Supponiamo sempre che questi convetgano in modo assoluto.

---

### PROPRIETA' DEL VALOR MEDIO

---

#### Formula disintegrazione del valor medio

- Discreta:
$$ E[X|I] = \sum_{y \in E} E[X|I,Y=y] P(Y=y|I) $$

- Continua:
$$ E[X|I] = \int_{-\infty}^{+\infty} E[X|I,Y=y] P(Y=y|I) dy $$

---

#### Linearità del valor medio

$$ E[aX|I] = a E[X|I] $$
$$ E[X+Y|I] = E[X|I] + E[Y|I] $$

---

#### Monotonia del valor medio

$$ P(X \geq Y | I) = 1 \implies E[X|I] \geq E[Y|I] $$

---

#### Disuguaglianza di Markov

$$ P(X > c | I) \leq \frac{E[X|I]}{c}$$
Con $P(X|I)>0$ e $c>0$.

---

#### Valor Medio Variabile Composta

- Discreta:
$$ E[g(X)|I] = \sum_{x \in E} g(x) P(X=x|I) $$

- Continua:
$$ E[g(X)|I] = \int_{-\infty}^{+\infty} g(x) P(X=x|I) dx $$

Con base $X \in \mathbb{E}$ , $(E=\mathbb{R})$ e $(g: \mathbb{E} \to \mathbb{R})$.

---

### Varianza

Sia $X \in \mathbb{R}$ una variabile aleatoria con valor medio $E(X|I)$ , si definisce varianza:
$$ Var_x(X) = E[(X - E(X))^2] $$
Vale dunque l'identità:
$$ Var_x(X) = E(X^2) - (E(X))^2 $$

Usando la linearità del valor medio dopo aver sviluppato il quadrato della prima formula.

---

### Deviazione Standard

La deviazione standard di una variabile aleatoria $X$ è definita come la radice quadrata della varianza:
$$ \sigma_X = \sqrt{Var_X(X)} $$

---

### Covarianza

Date due variabili aleatorie $\in \mathbb{R}$ , si definisce covarianza tra esse:
$$ Cov(X,Y) = E[(X - E(X))(Y - E(Y))] $$
Formule alternative:

- $$ Var(X,Y)=Var(X)+Var(Y)+2Cov(X,Y) $$
- $$ Cov(X,Y) = E(XY) - E(X)E(Y) $$

Se le due variabili sono INDIPENDENTI allora:
$$ Cov(X,Y) = 0 $$

---

### Matrice delle Covarianze

$$ \sum_{(x,y)}= \begin{bmatrix}
Var(X) & Cov(X,Y) \\
Cov(X,Y) & Var(Y) \\
\end{bmatrix} $$

Ed è detto coefficiente di correlazione lineare tra $X$ e $Y$ la quantità:
$$ p_{(X,Y)} = \frac{cov(X,Y)}{\sigma_X \sigma_Y} $$

---

## Momenti
Sia $X \in \mathbb{R}$ una variabile aleatoria, $\forall k \in \mathbb{N}$ , si definisce momento di ordine $k$ di $X$ :
$$ \mu_k = E[X^k] $$
*Nota:* Momento secondo la formula della varianza: $E[X^2] = Var(X) + (E(X))^2$ .

---

## Funzione Generatrice dei Momenti (MGF)
Data $X \in \mathbb{R}$ una variabile aleatoria reale, si definisce funzione generatrice dei momenti di $X$ la funzione:
$$ MGF_x : \mathbb{R} \to [0,+\infty] $$
$$ t \to MGF_X(t) = E[e^{tX}] $$
+ Discreta:
$$ MGF_X(t) = \sum_{x \in R} e^{tx} P(X=x) $$
+ Continua:
$$ MGF_X(t) = \int_{x \in R } e^{tx} P(X=x) dx $$

*Nota:* L'integrale corrisponde alla trasformata di Laplace della: $x \to p(X=x)$

Sia $x \in \mathbb{R} / MGF_X(t) < +\infty, \forall t \in \mathbb{-\epsilon, +\epsilon}$ con $\epsilon >0$ , allora, per ogni $k \in \mathbb{N}$, $X$ ha momento di ordine $k$ ben definito e vale:
$$ \frac{d^k}{d^kt} MGF_X(0) = E[X^k] $$
Per calcolare il momento di ordine $k$ basta derivare $k$ volte la MGF e valutarla in $t=0$.

---
