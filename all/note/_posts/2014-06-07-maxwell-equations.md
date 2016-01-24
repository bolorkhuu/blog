---
published: true
layout: default
title: Максвеллын тэгшитгэл
---
<p class="publish_date"> 2014.06.07</p>


## Максвеллын тэгшитгэлүүд

Цахилгаан техникын онол байгаль дээр орших цахилгаан болон соронзон орны бүх үзэгдлийг суурь онолын болон хэрэглээний түшинд судалдаг. үүнд зѳвхѳн [Максвелл](http://en.wikipedia.org/wiki/Maxwell%27s_equations)ын 4 тэгшитгэлийн шийдийг олоход хангалттай. 

**материалийн тэгшитгэлүүд** нэгэн тѳрлийн цахилгаан соронзон оронд:
\begin{align}
\vec{D} &= \varepsilon_0 \vec{E} + \vec{P} = \varepsilon_0 \varepsilon_r \vec{E} \newline
\vec{B} &= \mu_0 \big(\vec{H} + \vec{M} \big) = \mu_0\mu_r \vec{H} \newline
\vec{J} &= \kappa \vec{E}
\end{align}

**Максвеллын тэгшитгэлүүд дифренциал хэлбэрт**:

\begin{align}
\text{rot}\,\vec{H} &= \vec{J} + \frac{\partial \vec{D}}{\partial t} \tag{1} \newline
\text{rot}\,\vec{E} &= -\frac{\partial \vec{B}}{\partial t} \tag{2} \newline
\text{div}\, \vec{D} &= \rho_{_V} \tag{3} \newline
\text{div}\, \vec{B} &= 0 \tag{4}
\end{align}


**Максвеллын тэгшитгэл интеграл хэлбэрт**:

интеграл хэлбэрт оруулхын тулд [Гаус](http://en.wikipedia.org/wiki/Divergence_theorem) болон [Стокс](http://en.wikipedia.org/wiki/Stokes%27_theorem)ын хуулиудийг ашиглагна. 

\begin{align}
\iint\limits_A^{} \text{rot}\,\vec{H} \mathrm{d} \vec{A} &= \oint\limits_r \vec{H} \mathrm{d}\vec{r} =  \iint\limits_{A}^{}  \Big(\vec{J} + \frac{\partial \vec{D}}{\partial t} \Big) \mathrm{d}\vec{A} \tag{1.0} \newline
\iint \limits_A^{} \text{rot } \vec{E} \mathrm{d}\vec{A} &= \oint \limits_r^{} \vec{E}\mathrm{d}\vec{r} = \iint \limits_A^{} \Big(-\frac{\partial \vec{B}}{\partial t} \Big)\mathrm{d}\vec{A} \tag{2.0} 
\end{align}

\begin{align}
\iiint\limits_V^{} \text{div } \vec{D} \mathrm{d}V &= \oint\limits_A^{} \vec{D} \mathrm{d} \vec{A} = \iiint \limits_V^{} \rho_{_V} dV = Q \tag{3.0} \newline
\iiint \limits_V^{} \text{div } \vec{B} \mathrm{d}V &= \oint\limits_A^{} \vec{B} \mathrm{d}\vec{A} = 0 \tag{4.0}
\end{align}


Максвеллын 4 хууль бол хүн төрөлхтий технологийн **дэвшилд** маш их тус болсон. мартаж болохгүй.