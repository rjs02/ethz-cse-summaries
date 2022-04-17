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
# fontfamily: sans
---


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
  Jeder messbaren physikalischen Eigenschaft eines Systems entspricht ein selbstadjungierter, linearer Operator $\hat A$. Dieser physikalischen Eigenschaft kann nur dann ein Wewrt zugeorndnet werden, wenn der Zustandsvektor $\Psi$ des Systems ein Eigenvektor von $\hat A$ ist, d.h. $\Psi = \varphi_n$ mit $\hat A \varphi_n = a_n \varphi_n$, wobei $a_n$ dann der Wert dieser Eigenschaft ist.
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