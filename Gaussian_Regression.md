## Regression mit Gaussian Zufallsvariablen:

Man beobachte 10 Wertepaare $x_i,y_i$ und versucht f(x) = y zu finden, wobei man "vorgibt", dass y die Form $ \vec y = f(\vec x) = \vec \phi(x)^T *\vec w$ hat wobei es die Feature Funktion $\vec \phi_x^T$ hat und linear in $\vec w$ ist. 

Sei $\phi_i (x) = [1,x_i]^T$ für alle i. Daraus folgt
$$
\phi_X = \begin{vmatrix}
1&1&...&1\\
x_1&x_2&...&x_N\\
\end{vmatrix} \in \mathbf R^{F \times N}
$$
und mit


$$
f_x := f(x) \in \mathbf R
;
f_X := \phi_X^T* \vec w = 
\begin{bmatrix}
\phi_1(x_1) & \phi_2(x_1)\\
\phi_1(x_2) & \phi_2(x_2)\\
... & ...\\
\phi_1(x_N) & \phi_2(x_N)\\
\end{bmatrix} 
* 
\begin{vmatrix}
w_1\\
w_2\\
\end{vmatrix}
= 
\begin{vmatrix}
\phi_{x_1}^T \vec w\\
\phi_{x_2}^T \vec w\\
...\\
\phi_{x_N}^T \vec w\\
\end{vmatrix} 
= 
\begin{vmatrix}
f(x_1)\\
f(x_2)\\
...\\
f(x_N)\\
\end{vmatrix} 
\in \mathbf R^{N}
$$
Gaussian Process Regression können also durch Gaussian Inference die Optimalen $\vec{w}$ für die Linearkombination von Features finden als posterior über w  $p(w|y, \phi)$ bzw. $p(f_x|y,\phi)$ für f innerhalb eines Intervalls [$c_{min},c_{max}$] bei einem endlichen Datensatz 

## Gaussian Processes (nonparametric Regression)

Nun wählt man keine $\vec w$ mehr sondern wählt eine Kernel Funktion, die dazuführt, dass selbst unter unendlich vielen Features verteilt auf der x-Domain als dc das Integral im Kernel = $\phi(x_i)^T * \Sigma * \phi(x_j)$ konvergieren lässt. 

Kernel ist also kein Innerprodukt von Feature Vektoren mehr sondern bei geschickter Wahl eine Funktion, die nur noch für zwei gemessener Datenpunkte eine Zahl aka Ähmlichkeit ausgibt. Dies erzeugt dann also eine Kernel Matrix über alle Datenpunktpaare. Es ist ein Kernel oder Mercer kernel wenn für jede Auswahl von Datenpunkten die Kernel Matrix positive Semidefinite ist. 

Beispiele:

1. Mit der Stepfunktion $\phi_l(x) = \Theta(x-c_l)$ erhält man einen Random Walk/Wiener Process
2. Mit ReLU $\phi_l(x) = \Theta(x-c_l)(x-c_l)$ erhält man eine Smooth Kubik Spline Interpolation
3. Man kann aus bestehenden Kernels neue erzeugen
