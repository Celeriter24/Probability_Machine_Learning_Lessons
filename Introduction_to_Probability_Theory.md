## Einfuehrung in Wahrscheinlichkeitstheorie:

Wahrscheinlichkeiten erweitern die binäre Logik (True or False), um den Begriff der **Sicherheit oder Unsicherheit** einer Aussage. Sicherheit oder Unsicherheit stellt den Zusammenhang dar, wie oft **bei unendlichen vielen Ereignissen, ein gewisser Zustand** erreicht wird. 

Wir koennten jetzt ueber die Sigma Algebra Definition kommen, aber wir merken uns einfacher: 

Eine **Zufallsvariable** ist Obermenge von einem Set an Ereignissen, die die Zufallsvariable annehmen kann. Dabei ist wichtig, dass **jeder Zustand disjunkt** (also klar von den anderen Zustaenden abgrenzbar ist) und diese diskjunkten Zustaende von der Zustandsvariable angenommen werden kann. Zufallsvariablen die nur 2 Zustände haben nennt man binäre Zufallsvariablen.

Dadurch kann man **Wahrscheinlichkeiten über die Zustände einer Zufallsvariable** beschreiben. Die Wahrscheinlichkeiten muessen alle groesser oder gleich 0 sein und die Summe ueber die Wahrscheinlichkeiten aller jeweiligen Zustaende muss 1 ergeben. 
**Die Wahrscheinlichkeit eines Zustandes von 1 bedeutet, dass der Zustand immer eintrifft. 0 ist dass er gar nicht eintrifft** (auch bei unendlich vielen Ereignissen).

**Beispiel fuer eine Zustandsvariable**: 

- X = Augenzahl bei einem Wuerfelwurf (mit den gleich wahrscheinlichen Zustaenden 1,2....6) oder 
- Y = Anzahl bei zwei Wuerfelwuerfen (mit den ungleichverteilten Wahrscheinlichkeiten von 2...12).

**Die Gesamt-Wahrscheinlichkeit von 1 wird also über den Zustandsraum der Zufallsvariable "verteilt"!**

Man schreibt z.B. $p(X=1) = 1/6$ oder $p(Y=5) = 4/36$. (Wie man auf die Zahlenwerte kommt, später mehr)

Wenn man untersuchen will, wie wahrscheinlich ist, dass 2 Ereignisse zweier Zufallsvariablen zusammen auftreten, verwendet man die **sog. joint probability mit $p(x_1,x_2)$.**

## Unabhängigkeit

Um diese berechnen zu können müssen wir allerdings zuerst den **Begriff der Abhängigkeit bzw. Unabhängigkeit** beschreiben:

1. Wenn der Zustand einer Zufallsvariable **im Allgemeinen keine** Informationen über den Zustand der anderen Zufallsvariable verrät, dann sind die 2 Zufallssvariablen **unabhängig** voneinander. Bei mehr als 2 Zustandsvariablen muss diese bedingung unter allen möglichen Paaren gelten, damit alle unabhängig sind.
2. Wenn der Zustand einer Zufallsvariable **im Allgemeinen tatsächlich** Informationen über den Zustand der anderen Zufallsvariable verrät, dann sind die 2 Zufallssvariablen **abhängig** voneinander.
3. Gegeben einer 3. und bekannten Zufallsvariable (man kennt also dessen Zustand): Wenn der Zustand einer Zufallsvariable **keine** Informationen über den Zustand der anderen Zufallsvariable verrät, dann sind die 2 Zufallssvariablen **konditioniert unabhängig** voneinander.
4. Gegeben einer 3. und bekannten Zufallsvariable (man kennt also dessen Zustand): Wenn der Zustand einer Zufallsvariable **tatsächlich** Informationen über den Zustand der anderen Zufallsvariable verrät, dann sind die 2 Zufallssvariablen **konditioniert abhängig** voneinander.

Es kann also sein bei den Zufallsvariablen X,Y,Z, dass

1. Im Allgemeinen: $X {\perp\!\!\!\perp} Y$: Unabhängig 
2. Im Allgemeinen:$X {\not\!\perp\!\!\!\perp} Y$: Abhängig
3. Unter bekannter Z:$X {\perp\!\!\!\perp} Y | Z$: Bedingt unabhängig
4. Unter bekannter Z:$X {\not\!\perp\!\!\!\perp} Y | Z$: Bedingt abhängig

Wenn etwas allgemein gilt, dann gilt es auch unter Bedingungen, d.h. es könnten folgende Zusammenhänge zwischen X und Y **nicht** bestehen bzw. sind zu vereinfachen:

- Fall 1: $X {\perp\!\!\!\perp} Y$ und $X {\perp\!\!\!\perp} Y | Z$ wird zu einfach:$X {\perp\!\!\!\perp} Y$
- Fall 2:$X {\not\!\perp\!\!\!\perp} Y$ und $X {\not\!\perp\!\!\!\perp} Y | Z$ wird zu einfach:$X {\not\!\perp\!\!\!\perp} Y$

Aber jedoch gibt es folgende Zusammenhänge, die zusätzliche Informationen durch die Konditionierung geben (als 2. Zusammenhang):

- Fall 3: $X {\not\!\perp\!\!\!\perp} Y$ aber $X {\perp\!\!\!\perp} Y | Z$: Zu lesen als: Im Allgemeinen sind X und Y abhängig, aber unter Betrachtung von Z sind sie unabhängig. Beispiel: **X: Rasen ist nass, Y: Sprengler ist aus (wenn es regnet) Z: Es regnet**. Kausale Struktur $X \leftarrow Z \rightarrow Y$: Gabel-Struktur von der Bedingung/Beobachtung als gemeinsame Ursache. 

  Wenn der Rasen nass ist, erhöht sich die Vermutung, dass es geregnet hat, was wiederum bedeutet, das der Spregler vermutlich aus ist. Rasennässe und Spreglerzustand sind also abhängig. Wenn man sieht dass es regnet, gibt X keine Infos über Y mehr frei oder andersrum.

  **Intuition**: Z ist die einzige Brücke zwischen X und Y. Kennt man Z, zerfällt die Scheinkorrelation zwischen X und Y vollständig.

- Fall 4: $X {\perp\!\!\!\perp} Y$ aber $X {\not\!\perp\!\!\!\perp} Y | Z$: Zu lesen als: Im Allgemeinen sind X und Y unabhängig, aber unter Betrachtung von Z sind sie abhängig. Beispiel: **X: Es regnet, Y: Sprenger an, Z: Rasen ist nass**. Kausale Struktur $X \rightarrow Z \leftarrow Y$, Kollider auf die Bedingung/Beobachtung als gemeinsame Wirkung, 

  Regen und Spregler sind theoretisch unabhängig. Jedoch, wenn man weiß, dass der Rasen Nass ist: Dann wirkt sich Wissen von X auf Y aus und umgekehrt. 

  **Intuition**: Das Beobachten/Konditionieren auf den Kollider (als gemeinsame Wirkung) öffnet einen Informationsfluss zwischen den beiden Ursachen X und Y, der vorher nicht existierte.

**Wichtig: Abhängigkeiten und Unabhängigkeiten muss man entweder nachweisen oder setzt sie als Modellvoraussetzung. Es gibt genau diese 4 Fälle für die eine feste Kombination von X,Y,Z. Falls man ein anderes** $\boldsymbol Z_1$ **wählt, hat man 4 weitere Möglichkeiten der Beziehungen von X,Y,Z_1**. s. auch D-Seperation von Bayes Netzwerken.

Zurück zu joint probabilites:

- Für Fall 1: Im Allgemeinen: $X {\perp\!\!\!\perp} Y$: Unabhängig: $p(X,Y) = p(X) * p(Y)$
- Für Fall 2: Im Allgemeinen:$X {\not\!\perp\!\!\!\perp} Y$: Abhängig: $p(X,Y)$ kann nicht in Einzelteile faktorisiert werden!
- Für Fall 3 (Gabel):  $X {\not\!\perp\!\!\!\perp} Y$ aber $X {\perp\!\!\!\perp} Y | Z$: $p(X,Y,Z) = p(X|Z)*p(Y|Z)*p(Z)$, Marginalisierbar über Z zu $p(X,Y) = \Sigma_z p(X|Z)*p(Y|Z)*p(Z)$ mit $p(X,Y) \not = p(X) * p(Y)$, da marginal abhängig, jedoch $p(X,Y|Z)  = p(X|Z) * p(Y|Z)$ $\rightarrow$ Konditioniert faktorisierbar, da konditioniert unabhängig
- Für Fall 4 (Kollider):  $X {\perp\!\!\!\perp} Y$ aber $X {\not\!\perp\!\!\!\perp} Y | Z$:  $p(X,Y,Z) = p(Z|X,Y)*p(X,Y)$ und $p(X,Y)=p(X)*p(Y)$ [Beweisbar durch Marginalisierung von p(X,Y,Z) über Z], da marginal unabhängig, jedoch $p(Z|X,Y) \not = p(Z|X) * p(Z|Y)$ $\rightarrow$ Marginal faktorisierbar, da marginal unabhängig

## Sonstige Rechenregeln und Notationen:

Ein Komma in den Argumenten einer Wahrscheinlichkeit gelten immer als Schnitt: Also beide Argumente müssen erfüllt sein!

1. **Summenregel: Marginalisierung durch Summe oder Integral:**

   $p(x_1) = \Sigma_{x_2} p(x_1,x_2) = \int_{x_2} p(x_1,x_2) dx_2$

2. **Produktregel (Definition der bedingten Wahrscheinlichkeit)**

   $p(A,B) = p(A|B) * P(B)$ symmetrisch auch $p(A,B) = p(B|A) * P(A)$

3. **Kettenregel (Mehrfache Anwendung der Produktregel)**

   Allgemein für n Ereignisse $p(A_1,...A_n) = \prod_{i=1}^n p(A_i|A_{i+1}...A_n)$  (jede Reihenfolge ist erlaubt)

4. **Aus der symmetrie der Produktregel, um Konditionierungen umzukehren: Bayes Theorem**

   $p(A|B) = \frac {p(A,B)}{p(B)} = \frac {p(B|A) * P(A)}{p(B)}$, wobei $p(A|B)$ posterior Wahrscheinlichkeit (nach Beobachtung), $p(B|A)$ likelyhood (wie gut beschreiben die Daten B die Hypothesen A) und $P(A)$ Prior

5. **Oder-Regel:** 

   p(A oder B) = p(A) + p(B) - p(A,B) (Mengenlehre/Venndiagramm)
