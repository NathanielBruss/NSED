Simplifications
===============

The non-equilibrium spectrum can be simplified using the fact that

.. math::

   \begin{aligned}
       \langle \hat{O}^\dagger(t_2) \hat{O}(t_1)\rangle = \left[\langle \hat{O}^\dagger(t_1) \hat{O}(t_2)\rangle\right]^*\end{aligned}

eqn(12)

Then the S(ω, t) in Eq. (8) (In Formlas and Examples) can be simplified as

.. math::

   \begin{aligned}
        &&\frac{\sigma_{\rm pr}}{\sqrt{\pi}} \iint_{t_1<t_2}\!dt_2 dt_1 e^{i\omega(t_1-t_2)} g(t_1;t)g(t_2;t)\langle \hat{O}^\dagger(t_1) \hat{O}(t_2)\rangle\nonumber\\
       &&+\frac{\sigma_{\rm pr}}{\sqrt{\pi}} \iint_{t_1>t_2}\!dt_2 dt_1 e^{i\omega(t_1-t_2)} g(t_1;t)g(t_2;t)\langle \hat{O}^\dagger(t_1) \hat{O}(t_2)\rangle\nonumber\\
       &=&\! \frac{\sigma_{\rm pr}}{\sqrt{\pi}} \iint_{t_1<t_2}\!dt_2 dt_1  g(t_1;t)g(t_2;t)\nonumber\\
       &&\left[e^{i\omega(t_1-t_2)}\langle \hat{O}^\dagger(t_1) \hat{O}(t_2)\rangle\right.\left.+ e^{i\omega(t_2-t_1)} \langle \hat{O}^\dagger(t_2) \hat{O}(t_1)\rangle\right]\nonumber\\
       &=&\! \frac{2\sigma_{\rm pr}}{\sqrt{\pi}}\! \iint_{t_1<t_2}\!dt_2 dt_1  g(t_1;t)g(t_2;t)\mathrm{Re}\!\left[e^{i\omega(t_1-t_2)}\langle \hat{O}^\dagger(t_1) \hat{O}(t_2)\rangle\right]\nonumber\\\end{aligned}

eqn(13)

Note that for the discrete time axis used in numerics, one should add the t1 = t2 zero-measure part

.. math::

   \begin{aligned}
        \frac{\sigma_{\rm pr}}{\sqrt{\pi}}\! \int_{t_1}\! dt_1  g(t_1;t)^2\mathrm{Re}\!\left[\langle \hat{O}^\dagger(t_1) \hat{O}(t_1)\rangle\right]\end{aligned}


eqn(14)

Similarly, the four-time correlation function

.. math::

   \begin{aligned}
   \big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0 = \left[\big\langle \hat{\mathcal{D}}^\dagger(t_1)\hat{\mathcal{D}}(t_1^\prime) \hat{\mathcal{D}}^\dagger(t_2^\prime)   \hat{\mathcal{D}}(t_2)  \big\rangle_0\right]^*\end{aligned}

eqn(15)

Therefore, the trRIXS cross-section can be simplified as

.. math::

   \begin{aligned}
   &&\mathcal{I}(q_i,q_s,\omega_{in},\omega_s;\epsilon_i,\epsilon_s)(t)\!\nonumber\\
   &=&\! \iint\!dt_1dt_2 
   e^{i\omega(t_2-t_1)} 
    g(t_1,t)g(t_2,t) C(t_1,t_2; \omega_s)\end{aligned}

eqn(16)

where the effective two-time correlation takes

.. math::

   \begin{aligned}
   C(t_1,t_2; \omega_s)\!&=&\!  \iint dt_1^\prime dt_2^\prime e^{-i\omega_s(t_2^\prime-t_1^\prime)}  l(t_1,t_1^\prime)l(t_2,t_2^\prime)\times\nonumber\\
   &&\!\big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0\nonumber\\
   &=&\iint_{t_1^\prime < t_2^\prime} dt_1^\prime dt_2^\prime e^{-i\omega_s(t_2^\prime-t_1^\prime)}  l(t_1,t_1^\prime)l(t_2,t_2^\prime)\nonumber\\
   &&\!\big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0\nonumber\\
   &&+\iint_{t_1^\prime > t_2^\prime} dt_1^\prime dt_2^\prime e^{-i\omega_s(t_2^\prime-t_1^\prime)}  l(t_1,t_1^\prime)l(t_2,t_2^\prime)\nonumber\\
   &&\!\big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0\nonumber\\
   &=&\iint_{t_1^\prime < t_2^\prime} dt_1^\prime dt_2^\prime \Big[e^{-i\omega_s(t_2^\prime-t_1^\prime)}  l(t_1,t_1^\prime)l(t_2,t_2^\prime)\nonumber\\
   &&\!\big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0+ e^{i\omega_s(t_2^\prime-t_1^\prime)}\nonumber\\
   &&  l(t_1,t_2^\prime)l(t_2,t_1^\prime)\big\langle \hat{\mathcal{D}}^\dagger(t_1) \hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_2) \big\rangle_0^*\Big]\nonumber\\\end{aligned}
   
eqn(17)  

Easy to show that
   
.. math::

   \begin{aligned}
   C(t_1,t_2; \omega_s)^*\!&=&\! \iint_{t_1^\prime < t_2^\prime} dt_1^\prime dt_2^\prime \Big[e^{i\omega_s(t_2^\prime-t_1^\prime)}  l(t_1,t_1^\prime)l(t_2,t_2^\prime)\nonumber\\
   &&\!\big\langle \hat{\mathcal{D}}^\dagger(t_2)\hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_1)  \big\rangle_0^*+ e^{-i\omega_s(t_2^\prime-t_1^\prime)}\nonumber\\
   &&  l(t_1,t_2^\prime)l(t_2,t_1^\prime)\big\langle \hat{\mathcal{D}}^\dagger(t_1) \hat{\mathcal{D}}(t_2^\prime) \hat{\mathcal{D}}^\dagger(t_1^\prime)   \hat{\mathcal{D}}(t_2) \big\rangle_0\Big]\nonumber\\
   &=& C(t_2,t_1; \omega_s)\end{aligned}

eqn(18)
   