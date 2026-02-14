## Verteilungen

Verteilungen sind Zuordnungen von einem mehrdimensionalen Raum zu einem eindimensionalen Raum. Verteilungen können in ihrem Urbild sowie in dessen Bild diskret oder kontinuierlich sein. 

## Wahrscheinlichkeitsverteilungen

Wahrscheinlichkeitsverteilungen sind Zuordnungen von Zustandsvektoren $\vec x \in \mathbf R^n$ (von einer beliebigen Kombination unterschiedlicher Zufallsvariablen) auf dessen Wahrscheinlichkeit $p(\vec x) \in \mathbf R^1 \in [0,1]$

**Für diskrete Zufallsvariablen** kann man einem Zustand x eine Wahrscheinlichkeit zuordnen, sodass für alle Zustände $x \in \vec x$ einen Vektor (Liste) $p(\vec x)$ schreiben. Die Zuordnung p von $\vec x$  auf $p(\vec x)$ nennt man **probability mass funktion oder PMF**. Es werden "Massen" an Wahrscheinlichkeiten verteilt. 

**Für kontinuierliche Zufallsvariablen** kann man jedem infitisimalen Zustandsänderung $dx$ **eine Wahrscheinlichkeitsdichtenfunktion PDF** zugeordnet werden. Bei der PDF werden "Dichten" an Wahrscheinlichkeiten über infitisimale $dx$ beschrieben. Um die Wahrscheinlichkeit von x zu erreichen wird $p(x) = \int_{- \inf } ^x pdf(x) dx$ berechnet.

Sowohl diskrete als auch kontinuierliche Wahrscheinlichkeitsverteilungen haben **eine sog. cummultive Distribution Funktion CDF**, die die Wahrscheinlichkeiten für "alle vorherigen" und den aktuellen Zustand aufsummiert. Sie startet also mit dem "kleinsten" Zustand bei 0 und endet beim "größten" Zustand bei 1. Sie gibt also die Wahrscheinlichkeit an, für einen der "kleineren oder des gewählten Zustandes x" an. **Sie hängt also stark von der "Ordnung" der Zustände ab.**   

**Die Summe oder das Integral über alle Zustände der Zufallsvariable muss 1 ergeben und jede Einzelzustandsvariable muss größer gleich 0 sein.** 

## Erwartungswert und Varianzen

Der Erwartungswert einer Funktion f (oder auch Wahrscheinlichkeitsverteilung die eine Funktion ist) ist der wahrscheinlichkeits gewichter Wert der Funktion.

$\mathbf E(f) = \Sigma_x p(x)*f(x) $ oder kontinuierlich $= \int_x p(x)*f(x) dx$ 

Note: Für $\lim_{N \rightarrow \infin}: $$\mathbf E(f) = 1/N * \Sigma_{n=1}^N f(x_n)$

Geht auch natürlich für mehrdimensionale Funktionen, wobei die "marginalisierte" Variable angegeben werden muss.

$\mathbf E_x(f(x,y)) = g(y) $

Der Erwartungswert ist linear in Skalaren und unter Summen kombinierbar/dekombinierbar (1). 

Die Varianz innerhalb einer Variable ist definiert als 

$var(f) = \mathbf E[f(x)^2-\mathbf E(f(x)]^2 =^{1} \mathbf E[f(x)^2]-\mathbf E[(f(x)]^2 $

Die Covarianz zwischen 2 Variablen ist definiert als 

$cov(x,y) =\mathbf E_{x,y}[(x-\mathbf E(x))(y-\mathbf E(y))] = \mathbf E_{x,y}(x,y)-\mathbf E (x)*\mathbf E (y)$ gibt an in welcher Weise sich x und y zusammen verändern. 

Seien $\vec x$ und $\vec y$ Vektoren von Zuständen, so:

$cov(\vec x,\vec y) =\mathbf E_{\vec x,\vec y}[(\vec x-\mathbf E(x))(\vec y^T-\mathbf E(\vec y^T))] = \mathbf E_{\vec x,\vec y}(\vec x,\vec y^T)-\mathbf E (\vec x)*\mathbf E (\vec y^T)$ 
