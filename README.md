# Radiative-Transfer-
# Radiative Transfer — Course Assignments

This repository contains assignment solutions for the **Radiative Transfer** course I took at **IISc Bangalore**.
The course was taught by Kartick C. Sarkar

# Methodology — Key equations 

## Assignment 1 — Radiative transfer through a spherical cloud & adiabatic sphere

**Radiative transfer (frequency ν)**  

$$\frac{dI_{\nu}}{ds} = -\kappa_{\nu} I_{\nu} + j_{\nu},$$

with optical depth

$$\tau_{\nu}(s)=\int_{s_0}^{s}\kappa_{\nu}(s')\,ds'$$

Formal solution along a ray (impact parameter $b$):

$$
I_{\nu}(b)=I_{\nu}^{\rm in} e^{-\tau_{\nu,\rm tot}(b)}+\int_{\text{chord}} S_{\nu}(s)\,e^{-[\tau_{\nu}(s_{\rm out})-\tau_{\nu}(s)]}\,\kappa_{\nu}(s)\,ds,
$$

where $S_{\nu}=j_{\nu}/\kappa_{\nu}$ and for thermal emissivity $S_{\nu}=B_{\nu}(T)$.

**Absorption / opacity (neutral H)**  
$$\kappa_{\nu}(r)=n_H(r)\,\sigma_H(\nu),\qquad \sigma_H(E)=10^{-18}\left(\frac{E}{13.6\ \mathrm{eV}}\right)^{-3.5}\ \mathrm{cm^2}.$$

**Specific-intensity for 5000 Å as function of impact parameter $b$** (integral form):

$$
I_{5000}(b)=\int_{-s_{\max}}^{s_{\max}} B_{5000}(T(r))\,\kappa_{5000}(r)\,\exp\!\Big(-\int_{s}^{s_{\max}}\kappa_{5000}(r')\,ds'\Big)\,ds,
$$

with $r=\sqrt{b^2+s^2}$ and $s_{\max}=\sqrt{R_c^2-b^2}$.

**Observed blackbody temperature** (invert Planck at frequency $\nu$):

$$
I_{\nu}(b)=B_{\nu}\big(T_{\rm obs}(b)\big)\quad\Rightarrow\quad
T_{\rm obs}(b)=B_{\nu}^{-1}\!\big(I_{\nu}(b)\big)
=\frac{h\nu}{k}\Big[\ln\!\Big(1+\frac{2h\nu^3}{c^2 I_{\nu}(b)}\Big)\Big]^{-1}.
$$

**Adiabatic expansion of a blackbody-filled sphere**  

If linear scale increases by factor $(1+\beta)$ then photon energies scale $\propto(1+\beta)^{-1}$ and

$$u\propto(1+\beta)^{-4}\Rightarrow T_f=\frac{T_i}{1+\beta}.$$

---

## Assignment 2 — Strömgren sphere (smooth edge) & ionization balance

**Notation:** $x(r)=n_{H^0}(r)/n_H$ (neutral fraction), $y(r)=1-x(r)$ (ionized fraction). Star luminosity per Hz:

$$L_{\nu}=4\pi^2 R_\star^2 B_{\nu}(T_\star).$$

**Frequency-dependent optical depth**

$$
\tau_{\nu}(r)=n_H\int_0^{r} x(r')\,\sigma_{\nu}\,dr'.
$$

**Attenuated specific flux**

$$
F_{\nu}(r)=\frac{L_{\nu}}{4\pi r^2}\,e^{-\tau_{\nu}(r)}.
$$

**Photoionization rate per neutral atom**

$$
\Gamma(r)=\int_{\nu_0}^{\infty}\frac{F_{\nu}(r)}{h\nu}\,\sigma_{\nu}\,d\nu.
$$

**Local ionization equilibrium (steady state)**

$$
n_H x(r)\,\Gamma(r)=n_H^2\,\alpha(T_s)\,(1-x(r))^2.
$$

Divide by $n_H$ and write $y=1-x$ to get the quadratic solved pointwise:

$$
n_H\alpha\,y^2+\Gamma\,y-\Gamma=0
\quad\Rightarrow\quad
y(r)=\frac{-\Gamma(r)+\sqrt{\Gamma(r)^2+4n_H\alpha\,\Gamma(r)}}{2n_H\alpha},
$$

so $x(r)=1-y(r)$.

**Recombination coefficients used**

$$
\alpha_A=4.13\times10^{-13}\,T_4^{-0.713}\ \mathrm{cm^3\,s^{-1}},\qquad
\alpha_B=2.56\times10^{-13}\,T_4^{-0.82}\ \mathrm{cm^3\,s^{-1}},
$$

with $T_4=T_s/10^4$ and $T_s=1.5\times10^4\,$K.

**Reference Strömgren radius**

$$
r_{\rm st}=\Big(\frac{3Q_H}{4\pi\alpha_B n_H^2}\Big)^{1/3},\qquad
Q_H=\int_{\nu_0}^{\infty}\frac{L_{\nu}}{h\nu}\,d\nu.
$$

**Band flux to plot (13.6–20 eV)**

$$
F_{\rm band}(r)\simeq\int_{E_1}^{E_2} F_E(r)\,dE \approx \sum_{E_j\in[13.6,20]\,{\rm eV}} F_{E_j}(r)\,\Delta E_j.
$$

---

## Assignment (Carbon ionization equilibrium) — main equations

For sequential ion stages $i\to i+1$ with collisional ionization coefficients $\xi_i$ and recombination coefficients $\alpha_i$:

**Steady-state rate equations**

$$
\xi_{i-1} f_{i-1} + \alpha_{i+1} f_{i+1} = (\xi_i+\alpha_i)\,f_i,\qquad i=1,\dots,N-1,
$$

with boundary forms at $i=0,N$.

**Recurrence (compact)**

$$
\frac{f_{i+1}}{f_i}=\frac{\xi_i}{\alpha_{i+1}}\quad\Rightarrow\quad
f_i=f_0\prod_{k=0}^{i-1}\frac{\xi_k}{\alpha_{k+1}}.
$$

**Normalization**

$$
f_0=\Big(1+\sum_{i=1}^{N}\prod_{k=0}^{i-1}\frac{\xi_k}{\alpha_{k+1}}\Big)^{-1}.
$$

---




    
