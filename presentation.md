% Title Presentation
% Jakob Schwerter
% Whatever, Tilburg University


Hallo
================
- Why do I not enjoy the sun? Because I have to work. Because I have an aim I follow and there is not much which can actually distract me from that aim
- I do allow social life to make me happy, and make my social life happy.
- This is not a contradiction
- $x+1 = y$

Heading 1
================

a
----------

<span>eststo: reg lnc lnp lny, cluster(state)</span>\
Results can be seen in Table 1

--------

b 
-

<span>quietly tab year, gen(period)</span>\
<span>eststo: xtreg lnc lnp lny period\*,fe cluster(state)</span>\
<span>eststo: reg d.lnc d.lnp d.lny d.period\*, cluster(state)</span>\
<span>xtserial lnc lnp lny</span>\
$$\begin{align*}
lnC_{it}= \alpha + \beta_{1}lnP_{it} + \beta_{2}lnY_{it} + \gamma_{2} D_{2i}+... + \gamma_{46} D_{46i}+ \delta_{1} T1_{t} + ...+ \delta_{29} T29_{t}+u_{it}\end{align*}$$

--------

In order to account for time effects dummy variables (T1-T29) for each
but one year are included. To include state effects there are several
options. Firstly dummy variables (D2-D46) for each state can be added to
the regression. Equivalently, a fixed effect within transformation can
be applied to get rid of unobserved state-specific effects. If the
state-specific effects can be argued to be uncorrelated with the
included regressors, a random effects model can be estimated. In fact,
the Hausmann test does no reject the RE model. Since the RE model yields
very similar estimates we will stick with the FE model for comparative
purposes.

--------

Given that smoking is an addiction it is plausible that there might be
serial correlation, which is confirmed by a test for serial correlation
in the residuals obtained from the FD regression. Given substantial
serial correlation, the FD regression should generally be preferred.

--------

Heading 2
==========

a - some math
----------

$$\begin{align*}
lnC_{it}= \alpha + \beta_{1}lnP_{it} + \beta_{2}lnY_{it} + \gamma_{2} D_{2i}+... + \gamma_{46} D_{46i}+ \delta_{1} T1_{t} + ...+ \delta_{29} T29_{t}+u_{it}\end{align*}$$

----------------

$$\begin{align*}
& E[y_{i} | a^{l}_{i}=0, s_{i}=0] = \alpha - \gamma \frac{\pi_{0}}{\pi_{2}}\\
& E[y_{i} | a^{l}_{i}=0, s_{i}=1] = \alpha - \gamma \frac{\pi_{0}}{\pi_{2}} + \beta - \frac{1}{\pi_{2}} (\gamma \pi_{1} + \tau (\pi_{0}+\pi_{1}) ) \\
& E[y_{i} | a^{l}_{i}=1, s_{i}=0] = \alpha - \gamma \frac{\pi_{0}}{\pi_{2}}+\frac{\gamma}{\pi_{2}}\\
& E[y_{i} | a^{l}_{i}=1, s_{i}=1] = \alpha + \beta - \frac{1}{\pi_{2}}(\gamma (\pi_{0}+(\pi_{1}-1)+\tau(\pi_{0}+\pi_{1}-1))\\
\end{align*}$$

b - even mor math
--------------

$$\begin{align*}
& E[y_{i} | a^{l}_{i}=0, s_{i}=1] - E[y_{i} | a^{1}_{i}=0, s_{i}=0]  = \beta - \gamma \frac{\pi_{1}}{\pi_{2}}-\frac{\tau}{\pi_{2}}(\pi_{0}+\pi_{1}) \\
& \text{If }\pi_{0} = \pi_{1} = 0, \\
& E[y_{i} | a^{l}_{i}=0, s_{i}=1] - E[y_{i} | a^{1}_{i}=0, s_{i}=0]  = \beta - \gamma \frac{0}{\pi_{2}}-\frac{\tau}{\pi_{2}}(0+0) = \beta \\
\end{align*}$$

New Heading 3
================
Just a bit of math
-----------

Partial derivatives of the expenditure function with respect to prices\
$$\begin{align*}
&h_{1}(p,u) = \frac{{\partial}e(p,w)}{{\partial}{p_{1}}} = \frac{u}{2} \\
&h_{2}(p,u) = \frac{{\partial}e(p,w)}{{\partial}{p_{2}}} = u \\
&\rightarrow  h(p,u) = \left(\begin{array}{c}  \frac{u}{2} \\ u \end{array} \right)\end{align*}$$

-----------------


Figures
=================


![](images/quality1.png)

--------------


![](images/gr_1.png)

---------

- we can also do a figure from the web
	- But I actually prefer a funny meme
		- Because I like them
- Cool, different types of points for nested bullets

---------


![A nice woooooow meme](http://pl.memgenerator.pl/mem-image/wooooooow-pl-ffffff-2)





Conclusion
----------

I hope we did not have contruct a presentaiton which makes completely sense

- to get the html, type the following on one line:

```
pandoc -s --mathjax --slide-level 2 --toc --toc-depth=1 -t revealjs presentation.md -V theme=solarized -o presentation.html
```
- if you want a beamer/latex pdf, type:

```
pandoc --slide-level 2 --toc --toc-depth=1 -t beamer presentation.md -V theme:Montpellier -o presentation.pdf
```
