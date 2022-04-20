---
title: Physikalische Chemie III - Molekulare Quantenmechanik
author: Robin Sieber
date: Frühlingssemester 2022
header-includes: |
    \usepackage{physics}
    \usepackage[most]{tcolorbox}
margin-top:    2cm
margin-bottom: 2cm
margin-left:   1.5cm
margin-right:  1.5cm
papersize: a4
pagestyle: empty
fontfamily: sans
---

\newpage
# Mathematische Grundlagen

## Skalarprodukt
* Zweier Vektoren $\va*{y}, \va*{z} \in \mathbb C$: $$\ip{\va*{y}}{\va*{z}} = \sum_{k=1}^{n} y_k^* z_k$$
* Zweier (komplexwertigen) Funktionen $\Psi_1, \Psi_2$: $$\ip{\Psi_1}{\Psi_2} = \int_{-\infty}^{\infty} \Psi_1^* \Psi_2 \dd{x}$$
* Eine komplexe Funktion ist _quadratisch integrierbar_, wenn $\ip{\Psi} < \infty$ gilt.
* Funktionen sind _normiert_ wenn, $\ip{\Psi} = 1$ gilt.
* Zwei Funktionen sind _orthonormiert_, wenn $\ip{\Psi_m}{\Psi_n} = \delta_{mn} = \begin{cases} 1 & n=m \\ 0 & n\neq m \end{cases}$ gilt.

## Operatoren
* Ein Operator $\hat A$ ist eine Rechenvorschrift (Ableitung, Multiplikation etc.), die auf eine Funktion wirkt.
* Der _Kommutator_ zweier Operatoren ist folgendermassen definiert: $$\qty[\hat A, \hat B] = \hat A \hat B - \hat B \hat A$$
* Für Kommutatoren gelten folgende Rechenregeln:
    * $\qty[\hat A \hat B, \hat C] = \hat A\qty[\hat B, \hat C] + \qty[\hat A, \hat C] \hat B$
    * $\qty[\hat A, \hat B \hat C] =  \qty[\hat A, \hat B] \hat C + \hat B\qty[\hat A, \hat C]$
    * $\qty[\hat A \hat B, \hat C \hat D] = \hat A \qty[\hat B, \hat C] \hat D + \hat A \hat C \qty[\hat B, \hat D] + \qty[\hat A, \hat C] \hat D \hat B +  \hat C \qty[\hat A, \hat D] \hat B$
* Der Kommutator ist selbst ein Operator.

## Matrizen
* Die adjungierte Matrix $A^\dagger$ ist die Transponierte der komplex konjugierten Matrix $A$.
* $A$ ist _selbstadjungiert_, wenn $\qty(A^\dagger)_{ij} = \qty(A)^*_{ji}$ gilt.

# Kapitel 1
nichts

# Kapitel 2: Schrödinger-Gleichung
In der Quantenmechanik werden messbare physikalische Grössen als Obsverablen bezeichnet und durch Operatoren oder Matrizen dargestellt. 

* Ortsoperator $\hat x = x$
* Impulsoperator $\hat p_x = -i\hbar\dv{x}$
* $\qty[\hat x, \hat p_x] = i\hbar$

## Korrespondenzprinzip
Um die Schrödinger-Gleichung eines beliebigen Systems aufzustellen, verwenden wir das folgende Rezept:

1. Die klassische Energie des Systems als Funktion der Ortskoordinaten $(x, y, z)$ und der Impulskoordinaten $(p_x, p_y, p_z)$ ausdrücken.
2. Orts- und Impulskoordinaten durch Orts- und Impulsoperatoren ersetzen, um den _Hamilton-Operator_ $\hat H$ zu erhalten.
3. _Schrödinger-Gleichung_ $\hat H \Psi = E \Psi$ aufstellen.

Nicht die ganze QM kann durch dieses Prinzip hergeleitet werden, da es auch rein quantenmechanische Erscheinungen, wie z.B. den Spin gibt.

## Eine erste Skizze der Quantenmechanik
* In der QM werden Teilchen durch (i. Allg. komplexwertige) Wellenfunktionen dargestellt.
* Messgrössen/Observablen werden durch Operatoren oder Matrizen dargestellt und sind i. Allg. komplexwertig.
* Die experimentellen Messwerte einer Observablen sind die Eigenwerte der Eigenwertgleichung $\hat A \Psi_n = a_n \Psi_n$, wobei $\Psi_n$ eine Eigenfunktion und $a_n$ ein Eigenwert von $\hat A$ ist.


# Kapitel 3: Postulate und Theoreme der Quantenmechanik
\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat 1,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black} ]
  In der Quantenmechanik wird ein abgeschlossenes System durch seinen Hamilton Operator $\hat H$ vollständig charakterisiert.
\end{tcolorbox}

* Den Hamilton Operator erhält man gemäss Korrespondenzprinzip.
* Abgeschlossene Systeme sind eine Idealisierung. Messungen sind immer eine Verletzung dieser Isoliertheit.
* Bei der Aufstellung des Hamilton-Operators müssen alle Beiträge berücksichtigt werden, die für die Problemstellung relevant sind.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat 2,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black} ]
  Der Vektorraum der Eigenfunktionen $\varphi_n$ des Hamilton-Operators $\hat H$ ist ein Hilbert-Raum mit Skalarprodukt definiert in Kapitel 1. \\
  Die Gesamtheit aller (i. Allg. komplexen) orthonormalen (d.h. $\braket{m}{n} = \delta_{mn}$) Eigenfunktionen bildet eine Basis des Hilbert-Raums. Jede beliebige Zustandsfunktion $\Psi$ in diesem Raum kann als Linearkombination der Basisfunktionen $\varphi_n$ dargestellt werden. $$\Psi = \sum_n c_n \varphi_n.$$ \\
  Jeder messbaren physikalischen Eigenschaft eines Systems entspricht ein selbstadjungierter, linearer Operator $\hat A$. Dieser physikalischen Eigenschaft kann nur dann ein Wert zugeorndnet werden, wenn der Zustandsvektor $\Psi$ des Systems ein Eigenvektor von $\hat A$ ist, d.h. $\Psi = \varphi_n$ mit $\hat A \varphi_n = a_n \varphi_n$, wobei $a_n$ dann der Wert dieser Eigenschaft ist.
\end{tcolorbox}

* Ist das System im Zustand $\varphi_n$, ergibt eine Messung von $A$ den Wert $a_n$ und das System bleibt unverändert.
* Ist das System eine Superposition $\Psi = \sum_n c_n \varphi_n$, dann entspricht die Messung von $A$ einer immer nicht-deterministischen Projektion von $\Psi$ auf eine Eigenfunktion $\varphi_n$ mit Wahrscheinlichkeit $c_n^* c_n = \abs{c_n}^2$ und ergibt den Wert $a_n$.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat 3,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black} ]
  Der Erwartungswert $\ev{\hat A}_\Psi$ einer Observablen $\hat A$ für ein System mit normierter Zustandsfunktion $\Psi$ ist gegeben durch $$\ev{\hat A}_\Psi = \int \Psi^* \hat A \Psi \dd{\tau}.$$
  Wenn $\Psi$ nicht normiert ist, ist der Erwartungswert gegeben durch $$\ev{\hat A}_\Psi = \dfrac{\int \Psi* \hat A \Psi \dd{\tau}}{\int \Psi^* \Psi \dd{\tau}}.$$
\end{tcolorbox}

* Der Erwartungswert wird interpretiert als arithmetischer Mittelwert der Messwerte von $\hat A$ an einer grossen Anzahl gleichartiger Systeme mit gleicher Zustandsfunktion $\Psi$.
* In der Dirac'schen Bra-Ket-Notation kann man der Erwartungswert schreiben als $\ev{\hat A}_\Psi = \int \Psi^* \hat A \Psi \dd{\tau} = \sum_n \sum_m c_n^* c_m \mel{n}{\hat A}{m} = \sum_n \sum_m c_n^* c_m a_m \ip{n}{m} = \sum_n \abs{c_n}^2 a_n$.

## Matrixdarstellung von Operatoren
Sei $\qty{\varphi_n}$ eine vollständige, orthonormierte Basis von Eigenfunktionen des Operators $\hat A$. $\hat A$ kann äquivalent als Matrix dargestellt werden, wobei für die Elemente der Matrix $$A_{nm} = \int \varphi_n^* \hat A \varphi_m \dd{\tau} = \mel{n}{\hat A}{m}$$ gilt.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=orange,colbacktitle=orange,
  title=Theorem 1,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=orange} ]
  Selbstadjungierte, lineare Operatoren haben reelle Eigenwerte.
\end{tcolorbox}

* Laut Postulat 2 erhält man bei einer Messung immer einen Eigenwert des Operators. Da diese immer reell sind, müssen quantenmechanische Operatoren demnach selbstadjungiert sein.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=orange,colbacktitle=orange,
  title=Theorem 2,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=orange} ]
  Eigenfunktionen von selbstadjungierten Operatoren sind orthogonal, wenn sie verschiedene Eigenwerte haben.
\end{tcolorbox}

* Wenn zwei oder mehrere Eigenfunktionen denselben Eigenwert haben, sind sie nicht automatisch orthogonal. Sie können aber immer orthogonal gewählt werden (mit Gram-Schmidt).

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=orange,colbacktitle=orange,
  title=Theorem 3,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=orange} ]
  Wenn zwei Operatoren $\hat A$ und $\hat B$ eine gemeinsame (vollständige) Basis von Eigenfunktionen $\varphi_i$ haben, dann kommutieren die Operatoren.
\end{tcolorbox}

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=orange,colbacktitle=orange,
  title=Theorem 4,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=orange} ]
  Wenn zwei Operatoren kommutieren, dann kann man eine gemeinsame (vollständige) Basis von Eigenfunktionen der beiden Operatoren ermitteln.
\end{tcolorbox}


## Bedingungen für Wellenfunktionen
1. $\Psi$ muss quadratisch integrierbar sein.
  Diese Bedingung gilt nur für gebundene Systeme. Nicht gebundene Systeme (z.B. freies Teilchen) lassen sich nicht einfach normieren.

2. $\Psi$ muss eindeutig definiert sein (single-valued).

3. $\Psi$ muss stetig sein

4. $\dv{\Psi}{x}$ muss differenzierbar sein (also $\Psi$ zweimal diff'bar), und ist im Allgemeinen, aber nicht immer, stetig.


## Heisenbergsche Unbestimmtheitsrelation
Der Operator $\Delta \hat A = \hat A - \ev{\hat A}$ gibt die Abweichung der Messwerte der Observablen $\hat A$ vom Erwartungswert $\ev{\hat A}$ an. Die Streuung (Dispersion) der Messwerte für ein System mit $\Psi$ als Anfangszustand ist somit gegeben durch $$ \sigma_{A, \Psi}^2 = \ev{\qty(\hat A - \ev{\hat A})^2} = \ev{\hat A^2} - \ev{\hat A}^2 = \qty(\Delta A)^2$$
Wichtig: Beachte Unterschied zwischen $\Delta\hat A$ und $\Delta A$! $\Delta A = \sqrt{\ev{\hat{A}^2}}$ ist eine Zahl, die als statistische Unbestimmtheit (Streuung) einer Observablen interpretiert werden kann und $\Delta \hat A$ ist ein Operator.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat 4,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black} ]
  Die Zeitevolution eines abgeschlossenen Systems mit zeitunabhängigem Hamilton-Operator wird durch die zeitabhängige Schrödinger-Gleichung beschrieben:
  $$i\hbar\dfrac{\dd{\Psi(q_i,t)}}{\dd{t}} = \hat H \Psi(q_i,t)$$
  wobei $\Psi$ von den Ortskoordinaten und der Zeit abhängt. Ausserdem muss eine Anfangsbedingung $\Psi_0$ gegeben sein.
\end{tcolorbox}


## Erhaltungssätze
* Erhaltungssätze der klassischen Physik sind (mit Anpassungen) auch in der QM gültig.
* In der QM gelten die Erhaltugnssätze nur in Bezug auf Erwartungswerte.
* Hat eine Observable $\hat A$ einen konstanten Erwartungswert (d.h. unabhängig von der Zeitentwicklung des Systems), dann ist sie eine sog. _Erhaltungsgrösse_.
* Die Zeitabhängigkeit des Erwartungswertes von $\hat A$ ist proportional zum Erwartungswert des Kommutators von $\hat A$ und $\hat H$: $$\dv{t} \ev{\hat A} = \dfrac{i}{\hbar} \ev{\qty[\hat H, \hat A]}$$
* **$\hat A$ ist eine Erhaltungsgrösse, wenn $\hat A$ mit $\hat H$ kommutiert.**

### Zusammenfassung Erhaltungsgrössen
Erhaltungsgrössen $\hat A$ $\left(\qty[\hat A, \hat H]\right)$ sind besonders wichtig in der QM, weil

* $\hat A$ und $\hat H$ eine gemeinsame Basis vollständige Basis von Eigenfunktionen haben (Thm. 3 & 4)
* stationäre Zustände $\varphi_n$ mit $\hat H \varphi_n = E_n \varphi_n$ einen definierten Wert $a_n$ für die physikalische Grösse $\hat A$ haben (Postulat 3)
* der Erwartungswert $\ev{\hat A}$ bezüglich einer _beliebigen_ Zustandsfunktion $\Psi$ unter der Zeitentwicklung des Systems erhalten bleibt. 


### Bahn-, Spin und Gesamtdrehimpuls

Da der freie Raum isotrop ist, muss der Gesamtdrehimpuls $\vec J$ erhalten bleiben. Experimente zeigen, dass in Atomen der Bahndrehimpuls $\vec L$ nicht erhalten bleibt.

\begin{tcolorbox}[enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat 5,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black} ]
  Der Spinfreshimpuls $\vec{S}$ eines abgeschlossenen Systems ist der Anteil des Gesamtdrehimpulses, der nicht auf einen Bahndrehimpuls zurückzuführen ist: $$\hat{\vec{S}} = \hat{\vec{J}} - \hat{\vec{L}}$$
  Spins kommen in der relativistischen Formulierung der Quantenmechanik vor. Die Existenz des Spins muss aber im Rahmen einer nicht-relativistischen Theorie postuliert werden.
\end{tcolorbox}

### Seperabilität der Schrödinger-Gleichung
Besteht der Hamilton-Operator $\hat H$ eines abgeschlossenen Systems aus zwei oder mehreren Operatoren ($\hat H_a, \hat H_b$), die sich auf separate Variablenräume auswirken, ist die entsprechende Schrödinger-Gleichung separabel. Es gilt:
<!-- $$ \hat H \qty(\hat{\vec{p_i}}) $$ -->


<!-- \newtcolorbox{postulat}[1] {
    enhanced,attach boxed title to top center={yshift=-3mm,yshifttext=-1mm},
  colback=lime!10!white,colframe=lime!75!black,colbacktitle=lime!75!black,
  title=Postulat #1,fonttitle=\bfseries\sffamily,
  boxed title style={size=small,colframe=lime!75!black}
}

\begin{postulat}{23}
    snags ansgasd lsdf $asdf$
    $$ \hat H \Psi = E \Psi $$
\end{postulat} -->