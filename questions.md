Questions:

### Question 1 
$$
\mathbb{E}\left\|f-\hat{f}_h\right\|^2=\left\|f-f_h\right\|^2+\mathbb{E}\left\|f_h-\hat{f}_h\right\|^2=: b_h+v_h,
$$
Pourquoi notre critère est-il le risque (l'espérance de la l'intégrale) $\mathbb{E}\left\|f-\hat{f}_h\right\|^2$ et pas par exemple dans l'autre sens (l'intégrale des espérance) : $\int \mathbb{E}(f(x)-\hat{f}_h(x))^2 dx $ ?

### Question 2
$$
\mathbb{E}\left\|f-\hat{f}_h\right\|^2=\left\|f-f_h\right\|^2+\mathbb{E}\left\|f_h-\hat{f}_h\right\|^2=: b_h+v_h,
$$
Comment est-ce qu'on sépare les deux termes ?

Dans le cas d'une régression linéaire, la projection est orthogonale aux résidus. Ici, nous ne sommes pas dans le même cas exactement.
Nous avons vu qu'en développant finalement, cela semble fonctionner car il apparait des termes croisés qui sont nuls.

$$
\begin{aligned}
M S E=\mathrm{E}\left[(y-\hat{f})^2\right] & =\mathrm{E}\left[(f+\varepsilon-\hat{f})^2\right] \\
& =\mathrm{E}\left[(f+\varepsilon-\hat{f}+\mathrm{E}[\hat{f}]-\mathrm{E}[\hat{f}])^2\right] \\
& =\mathrm{E}\left[(f-\mathrm{E}[\hat{f}])^2\right]+\mathrm{E}\left[\varepsilon^2\right]+\mathrm{E}\left[(\mathrm{E}[\hat{f}]-\hat{f})^2\right]+2 \mathrm{E}[(f-\mathrm{E}[\hat{f}]) \varepsilon]+2 \mathrm{E}[\varepsilon(\mathrm{E}[\hat{f}]-\hat{f})]+2 \mathrm{E}[(\mathrm{E}[\hat{f}]-\hat{f})(f-\mathrm{E}[\hat{f}])] \\
& =(f-\mathrm{E}[\hat{f}])^2+\mathrm{E}\left[\varepsilon^2\right]+\mathrm{E}\left[(\mathrm{E}[\hat{f}]-\hat{f})^2\right]+2(f-\mathrm{E}[\hat{f}]) \mathrm{E}[\varepsilon]+2 \mathrm{E}[\varepsilon] \mathrm{E}[\mathrm{E}[\hat{f}]-\hat{f}]+2 \mathrm{E}[\mathrm{E}[\hat{f}]-\hat{f}](f-\mathrm{E}[\hat{f}]) \\
& =(f-\mathrm{E}[\hat{f}])^2+\mathrm{E}\left[\varepsilon^2\right]+\mathrm{E}\left[(\mathrm{E}[\hat{f}]-\hat{f})^2\right] \\
& =(f-\mathrm{E}[\hat{f}])^2+\operatorname{Var}[\varepsilon]+\operatorname{Var}[\hat{f}] \\
& =\operatorname{Bias}[\hat{f}]^2+\operatorname{Var}[\varepsilon]+\operatorname{Var}[\hat{f}] \\
& =\operatorname{Bias}[\hat{f}]^2+\sigma^2+\operatorname{Var}[\hat{f}] .
\end{aligned}
$$

### Question 3 
$$
b_h \approx\left\|f_{h_{\min }}-f_h\right\|^2 \approx\left\|\hat{f}_{h_{\min }}-\hat{f}_h\right\|^2-\frac{\left\|K_{h_{\min }}-K_h\right\|^2}{n}
$$
Pourquoi l'espérance sur le terme $\left\|\hat{f}_{h_{\min }}-\hat{f}_h\right\|^2 $ a disparu par rapport à la ligne précédente? 



### Question 4 
$$
\text { In this case } f_{h_{\min }}=K_{h_{\min }} \star f \text { is a good approximation of } f \text {, so that }\left\|f_{h_{\min }}-f_h\right\|^2 \text { is close to } b_h
$$
Pourquoi est-ce que l'on prend pas directement $f_{hmin}$ pour estimer f, si il s'agit d'un bon estimateur de f? 

Pourquoi ne pas prendre par exemple une gaussienne avec des paramètres mu et sigma (espérance et variance) estimés sur les données $X_i$ ? 

Quelles sont les similarités entre cette méthode, et celles qui utilisent du bootstrapping, ou de la cross validation? 

## 3.2 Oracle Inequality
What is the role played by the $\epsilon$ ? By the x ? Where does the intuition for setting these parameters come from ?

## 3.3 Minimum Penalty