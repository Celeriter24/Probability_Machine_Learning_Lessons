## Gaussche Normalverteilung

Die Gaussche Normalverteilung ist eine um den Mode symetrische kontinuierliche Wahrscheinlichkeitsverteilung, die von 2 Parametern mean und Varianz abhängt:

Für **einen Zustand x einer Zufallsvariable X** :

$p(x) = \mathcal N(x;\mu,\sigma^2) = \frac {1}{\sqrt{(2\pi\sigma^2)}} * \exp {-\frac {(x-\mu)^2}{2\sigma^2}}$ 

Für **einen Zustandsvektor $x_{1...n} =\vec x$ aus der Sammlung von Zufallsvariablen $X_{1...n} = \vec X$ **mit $x_i \in X_i$ für alle $i \in 1...n$. Diese Gaussverteilung wird auch **multivariante Gaussverteilung** mit dem Mean und der Kovarianzmatrix $\Sigma$, die auf der Hauptdiagonalen die Varianzen und auf den Off-Diagonalen die Covarianzen der jeweiligen Zufallsvariablen hat. Die Joint Probability Distribution für alle Zufallsvariablen für einen Zustandsvector $\vec x$ ist also

$p(\vec x) = \mathcal N(x;\vec\mu,\Sigma) = \frac {1}{{(2\pi)^{n/2}\sqrt{|\Sigma|})}} * \exp {-\frac {1}{2}*(\vec x-\vec \mu)^T * \Sigma^{-1} * (\vec x-\vec \mu)}$

Besonderheiten für die multivarianten Gaussverteilung:

Sie stellt die Joint Probability der Zufallsvariablen korrekt dar, wenn man annimmt, dass diese einzeln Gaussche Normalverteilungen sind. Es ist egal ob sie Abhängig oder nicht oder conditional Abhängig oder nicht, denn 

- **aus $\Sigma$ kann man marginale Unabhängigkeiten ablesen**, wenn $\Sigma_{i,j} = 0 \iff x_i {\perp\!\!\!\perp} x_j $ und 
- **aus $\Lambda = \Sigma^{-1}$ kann man bedingte Unabhängigkeiten gegeben allen anderen Variablen ablesen**, wenn $\Lambda_{i,j} = 0 \iff x_i {\perp\!\!\!\perp} x_j | \vec x_{ ohne (i,j)}$

Der Exponent heißt Mahalanobis Distanz und misst den Abstand zum Mean, skaliert durch die "Hauptrichtungen" von $\Sigma$.

Marginalisierungen für eine bleibende Variable $x_i$ ist einfach die eindimensionale $\mathcal N(x_i;\mu_i,\sigma^2_{ii})$

Bedingte Verteilungen sind auch Gaußisch:

$x_i|x_j \sim \mathcal N(μ_i+Σ_{ij} Σ_{jj}^{−1}(x_j−μ_j),Σ_{ii}−Σ_{ij}*Σ_{jj}^{−1} * Σ_{ji}))$

## Exkurs: Unabhängig vs. Unkorreliert:

Aus Unabhängig folgt Unkorreliertheit aber nicht vice versa. Korrekation ist "nur" wenn $\mathbf E[X,Y] = \mathbf E[X]*\mathbf E[Y] \iff  Cov(X,Y) = \mathbf E[(x-\mu_x)*(y-\mu_y)] = 0 \iff $Off-Diagonalen der $\Sigma$ sind 0.

 


