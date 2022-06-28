Important Observables
=====================

Many observables reflect the underlying collective orders or excitation, which are usually measurable in solid states.
In a system with translational symmetry, these observables are convenient to be written in momentum space through
Eq. (26) (In Derivations for Typical Tight-binding Models). This section lists a few frequently used observable expressions and derivations, which are referenced in the
following chapters.

A. Charge Operators
-----------------------

Let us first define the (charge) density operator in momentum space

.. math::

   \begin{aligned}
   \label{chp1:obsdefCharge}
   \rho_q	=\sum_{i,\sigma}n_{i\sigma}e^{iq\cdot r_i} = \sum_{k,\sigma} c_{k+q,\sigma}^\dagger c_{k\sigma}.\end{aligned}

eqn(58)

It describes a overall charge modulation with momentum q. Similarly, the charge structure factor N (q) = 〈ρ−qρq〉
describes the fluctuation of corresponding charge modulation. To distinguish from the spin operator, the charge
density is usually written as :math:`\rho_q^c` in this thesis.

.. math::

   \begin{aligned}
   \mathcal{D}_q=\sum_i e^{iq\cdot r_i}n_{i\uparrow}n_{i\downarrow} %&=&\frac1{L^2} \sum_i \sum_{k_1k_2 k_3k_4} c^\dagger_{k_1\uparrow} c_{k_2\uparrow} c^\dagger_{k_3\downarrow} c_{k_4\downarrow} e^{-i(k_1-k_2+k_3-k_4-q)\cdotr_i}\\
   =\frac1L\sum_{k_1,k_2,k^\prime}c^{\dagger}_{k_2+k^\prime+q\uparrow}
   c^{\dagger}_{k_1-k^\prime\downarrow}c_{k_1\downarrow}c_{k_2\uparrow}.\end{aligned}
   
eqn(59)

The double occupancy term in Hubbard model is :math:`\mathcal{D}=\mathcal{D}_q=0`

B. Spin operators
---------------------


Similarly, the spin operator describing spin modulation with momentum **q** is defined as

.. math::

   \begin{aligned}
   \label{chp1:obsdefSpin}
   \rho_q^{(s)}=\sum_{i,\sigma}s_{i\sigma}e^{iq\cdot r_i} = \sum_{k,\sigma} \sigma c_{k+q,\sigma}^\dagger c_{k\sigma}\end{aligned}

eqn(60)

and the spin structure factor :math:`S(q)=\left\langle \rho_{-q}^{(s)} \rho_q^{(s)}\right\rangle` describes the spin fluctuation.
By summing over either the real- or momentum-space spin correlations, the local moment

.. math::

   \begin{aligned}
   \label{chp1:eqMz2}
   m_z^2 = \sum_i \big(c_{i\uparrow}^\dagger c_{i\uparrow} - c_{i\downarrow}^\dagger c_{i\downarrow}\big)^2    = \sum_q S(q)\end{aligned}

eqn(61)

depicts the overall magnetization. Here we adopt the convention without a spin quantum number prefactor. That means a pure magnetic (either FM or AFM) state possesses a :math:`m_z^2\equiv 1` while a disordered stated displays :math:`\langle m_z^2\rangle=0.5`.

C. Superconductivity Pairing Correlations
------------------------------------------


The pairing correlations is defined generically

.. math::

   \label{chp1:eqPairingCorr}
       P^{(\zeta)}(q) = \frac1{L}\sum_{i j} e^{iq\cdot(r_i-r_j)} P^{(\zeta)}_{ij}
       = \frac1{L}\sum_{ij} e^{iq\cdot(r_i-r_j)} \left\langle \Delta^{(\zeta)\dagger}_{i} \Delta^{(\zeta)}_{j}\right\rangle

eqn(62)

where

.. math:: \Delta^{(\zeta)}_i = \sum_{j} \gamma^{(\zeta)}_{ij} c_{i\uparrow}c_{j\downarrow}

eqn(63)

Here ζ represents the symmetry and :math:`\gamma^{\zeta}_{ij}` is the symmetry vertex.
Usually only the uniform pairing correlation :math:`P^(ζ)=P^(ζ)(q=0)=(\frac1{L} \angle\langle \delta_i^{(ζ)\dagger}\delta_j^(ζ)) \angle\rangle` matters, in which ∆(ζ) = ∑i ∆(ζ)i.
For s-wave pairing, :math:`γ^(s)_ij = δ_i,j` and

.. math::

   \begin{aligned}
   \label{chp1:eqDelS}
   \Delta^{(s)} = \sum_{i} \Delta^{(s)}_i
    = \sum_i c_{i\uparrow}c_{i\downarrow}
    = \sum_k c_{k\uparrow}c_{-k\downarrow}.\end{aligned}
	
eqn(64)

Similarly, the d-wave pairing reads :math:`\gamma^{(d)}_{ij} = \delta_{i\pm \hat{x},j}-\delta_{i\pm \hat{y},j}`

.. math::

   \begin{aligned}
   \label{chp1:eqDelD}
   \Delta^{(d)} %&=& \sum_i \gamma^{(\zeta)}_{ij} c_{i\uparrow}c_{j\downarrow}\\
   &=& \frac1{L} \sum_{kk^\prime} \sum_{ij}
   \left(\delta_{i\pm \hat{x},j}-\delta_{i\pm \hat{y},j}\right)
   e^{i(k\cdot r_i+k^\prime\cdot r_j)}
   c_{k\uparrow}c_{k^\prime\downarrow} \\
    &=& 2\sum_k c_{k\uparrow}c_{-k\downarrow}\left(\cos k_x-\cos k_y\right).\end{aligned}
	
eqn(65 and 66)

Also the extended s-wave reads :math:`\gamma^{(\textrm{ex}-s)}_{ij} = \delta_{i\pm \hat{x},j}+\delta_{i\pm \hat{y},j}` and

.. math::

   \begin{aligned}
   \label{chp1:eqDelEXS}
       \Delta^{(\textrm{ex}-s)} = 2\sum_k c_{k\uparrow}c_{-k\downarrow}\left(\cos k_x+\cos k_y\right).\end{aligned}
	   
eqn(67)

**1. Bare bubble contributions**

In the correlated system, one usually cares particularly the part of superconductivity pairing induced exclusively
by the correlation effect. Therefore, the bare bubble contributions are usually subtracted off.
In the s-wave channel, the bare bubble reads

.. math::

   \begin{aligned}
   \left\langle \Delta^{(s)\dagger}\Delta^{(s)} \right\rangle_0 
   = \sum_{kk^\prime} \left\langle c_{-k^\prime\downarrow}^\dagger c_{k^\prime\uparrow}^\dagger c_{k\uparrow}c_{-k\downarrow}\right\rangle_0 
   = \sum_{kk^\prime} \left\langle c_{-k^\prime\downarrow}^\dagger c_{-k\downarrow}\right\rangle \left\langle c_{k^\prime\uparrow}^\dagger c_{k\uparrow}\right\rangle =  \sum_{k} \left\langle n_{-k\downarrow}\right\rangle \left\langle n_{k\uparrow}\right\rangle\end{aligned}

in the last step, translational and U (1) × U (1) symmetry is assumes. Generically, the bare bubble contribution of
ζ-symmetry pairing correlation concludes

.. math::

   \begin{aligned}
   \label{chp1:eqPairingBare1BD}
   %\left\langle \Delta^{(\zeta)\dagger}\Delta^{(\zeta)} \right\rangle_0 
   P^{(\zeta)}_0
   = \frac1{L}\sum_{k} \left|\gamma^{(\zeta)}(k)\right|^2 \left\langle n_{-k\downarrow}\right\rangle \left\langle n_{k\uparrow}\right\rangle.\end{aligned}

eqn(68)

This can also be extended into multi-orbital scenario

.. math::

   \begin{aligned}
   \label{chp1:eqPairingBareMultiBD}
   %\left\langle \Delta^{(\zeta)\dagger}\Delta^{(\zeta)} \right\rangle_0 
   P^{(\zeta)}_0
   = \frac1{L}\sum_{k}\sum_{ab\atop cd} 
   \left\langle c_{-k\downarrow}^{(a)\dagger} c_{-k\downarrow}^{(d)}\right\rangle 
   \left\langle c_{k\uparrow}^{(b)\dagger} c_{k\uparrow}^{(c)}\right\rangle \gamma^{(\zeta)}_{ab}(k)\gamma^{(\zeta)}_{cd}(k).\end{aligned}

eqn(69)

In the study of correlation induced superconducting pairing, Eq. (68) or (68) is usually subtracted off from the overall
pairing susceptibility(Guo et al., 2017).
