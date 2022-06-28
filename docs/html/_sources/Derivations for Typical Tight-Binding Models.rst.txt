Derivations for Typical Tight-Binding Models
============================================

The study of solid state physics is based on the modeling of important and intertwined degrees of freedom. According to various materials and the focus of many research interests, different minimal model Hamiltonians can be examined to address various phenomena in quantum materials. In this chapter, a second-quantized model based on band theory is derived and discussed in detail as it relates to cuprate systems. In addition, other physical excitations including spin, orbital, phonon and exciton degrees of freedom are discussed.

A. Second Quantization in Solids
--------------------------------

Most of the physical properties in condensed matter lie in the electronic configurations, moving in the ion potential background through a Born-Oppenheimer approximation. Therefore, the solution of electrons under a special periodic potential or crystalline system is a minimal model for the discussion of solid states. This solution together with its second quantized form is derived in a non-interacting band theory and then extrapolated into generic electronic systems.

Electrons in solid system can be described by the Hamiltonian

.. math::

   \begin{aligned}
   \label{manybodyHam}
   H = \sum_i\left[\frac{\mathbf{p}_i^2}{2m_e} +V(r_i)\right] + \sum_{ij}U(r_i,r_j)\end{aligned}
   
Eq.(19)

where V (r) is the periodic ion potential and :math:`U (r_i, r_j)` is the electron-electron interactions. Since the first two terms in
square bracket is a simple summation of each electron energy, this part is usually called one-body terms. In contrast,
the :math:`U (r_i, r_j)` are many-body terms
In the non-interacting limit where :math:`U(r_i,r_j)\equiv 0`, the Hamiltonian can be written in a one-body form :math:`H = \sum_i \hat{h}_i` and with the one-body Hamiltonian :math:`h_i = \left[\frac{\mathbf{p}_i^2}{2m_e} +V(r_i)\right]`. Its eigenstates can be solved generically according to Bloch theorem

.. math::

   \begin{aligned}
   \label{Blochtheorem}
   \varphi_k^\alpha = e^{ik\cdot r} u_k^\alpha(r)\end{aligned}
   
Eq.(20)
   
with :math:`u_k^\alpha(r)` the same periodicity with :math:`V(r)` and :math:`\alpha` representing generic spin-orbital index. The characteristic number :math:`k` is quasi-momentum, which runs over all first Brillouin zone. Thus, the many-body equation can be reduced to a single-body problem

.. math::

   \begin{aligned}
   \label{singleBodySchrodinger}
   \hat{h}\varphi_k^\alpha(r) =\varepsilon_k^\alpha \varphi_k^\alpha(r).\end{aligned}

Eq.(21)
   
After applying fermionic permutation rule, the many-body wave-function can be expressed as the Slater determinant

.. math::

   \begin{aligned}
   \label{slaterDeterminant}
   \Psi_{k_1,\cdots,k_N}^{(\alpha_1,\cdots,\alpha_N)}(r_1,\cdots,r_N) =\frac1{\sqrt{N!}}\left|\begin{array}{cccc}
    \varphi_{k_1}^{(\alpha_1)}(r_1) & \varphi_{k_1}^{(\alpha_1)}(r_2) & \cdots & \varphi_{k_1}^{(\alpha_1)}(r_N) \\
     \varphi_{k_2}^{(\alpha_2)}(r_1) & \varphi_{k_2}^{(\alpha_2)}(r_2) & \cdots & \varphi_{k_2}^{(\alpha_2)}(r_N) \\
     \vdots & \vdots & \ddots & \vdots\\
   \varphi_{k_N}^{(\alpha_N)}(r_1) & \varphi_{k_N}^{(\alpha_N)}(r_2) & \cdots & \varphi_{k_N}^{(\alpha_N)}(r_N)
   \end{array}
    \right|\end{aligned}
	
Eq.(22)
	
with *N* the number of particles. 
In a bra-ket notation it can be simplified as

.. math::

   \begin{aligned}
   \label{braket}
   \big\langle r_1,\cdots,r_N \big|\{k_m\};\{\alpha_m\}\big\rangle = \Psi_{k_1,\cdots,k_N}^{(\alpha_1,\cdots,\alpha_N)}(r_1,\cdots,r_N). \end{aligned}

Eq.(23)

For convenience in the following text, we explicitly split the orbital
and spin degree of freedom. Then the Schrodinger Equation is solved as

.. math::

   \begin{aligned}
   \label{manyBodySchrodinger}
   H\big|\{k_m\};\{\sigma_m\};\{\alpha_m\}\big\rangle =\sum_m \varepsilon_{k_m}^{\alpha_m}\big|\{k_m\};\{\sigma_m\};\{\alpha_m\}\big\rangle.\end{aligned}

Eq.(24)

Second quantization lies on the definition the creation operators
:math:`c_{k\sigma}^{\alpha\dagger}` of a electron in Bloch state
:math:`\varphi_k^\alpha(r)` with spin :math:`\sigma`

.. math::

   \begin{aligned}
   c_{k\sigma}^{\alpha\dagger} \big|\{k_m\};\{\sigma_m\};\{\alpha_m\}\big\rangle =\prod_m \big(1-\delta_{k,k_m}\delta_{\sigma,\sigma_m}\delta_{\alpha,\alpha_m}\big) 
   \big|k,\{k_m\};\sigma,\{\sigma_m\};\alpha,\{\alpha_m\}\big\rangle\end{aligned}

Eq.(25)

or introducing its Fourier form

.. math::

   \begin{aligned}
   \label{secondquantK}
   c_{i\sigma}^{\alpha\dagger} = \frac1{\sqrt{L}}\sum_{k\sigma} e^{-ik\cdot R_i} c_{k\sigma}^{\alpha\dagger}.\end{aligned}

Eq.(26)

Here :math:`r_i` is the an lattice vector and the operators :math:`c_{i\sigma}^{\alpha\dagger}` are canonical fermion operators following :math:`\{c_{i\sigma}^{\alpha}, c_{j\sigma}^{\beta}\} =0` and :math:`\{c_{i\sigma}^{\alpha}, c_{j\sigma}^{\beta\dagger}\} =\delta_{ij}\delta_{\alpha\beta}`. The Wannier basis can be the rewritten as the span of :math:`\big|\{i_m\};\{\sigma_m\};\{\alpha_m\}\big\rangle = c_{i_{N-1}\sigma_{N-1}}^{(\alpha_{N-1})\dagger}\cdots c_{i_0\sigma_0}^{(\alpha_0)\dagger}|\,\rangle`. To distinguish from the number of particles, we use :math:`L` to denote the overall system size in this thesis.

For convenience of real-space representation, people introduced the Wannier function :math:`W^\alpha(r-R_i)=\frac1{\sqrt{L}} \sum_k \varphi_k^\alpha e^{-ik\cdot R_i}` and therefore, :math:`\varphi_k^\alpha = \frac1{\sqrt{L}} \sum_i e^{ik\cdot R_i}W^\alpha(r-R_i)`. Therefore we can write the field operator

.. math::

   \begin{aligned}
   \Psi_{\sigma}^{\dagger}(r) = \sum_{k\alpha}\varphi_k^{\alpha*}(r) c_{k\sigma}^{\alpha\dagger} = \sum_{i\alpha}W^{\alpha*}(r-r_i) c_{i\sigma}^{\alpha\dagger}.\end{aligned}

Eq.(27)

Based on this Wannier basis originating from the one-body part, the second quantized Hamiltonian of full electrons Eq. [19] becomes

.. math::

   \begin{aligned}
   H &=& \sum_\sigma\int\Psi_{\sigma}^{\dagger}(r) \hat{h} \Psi_{\sigma}(r) dr^3+\frac12 \sum_{\sigma_1\sigma_2}\iint\Psi_{\sigma_1}^{\dagger}(r_1)  \Psi_{\sigma_2}^{\dagger}(r_2)U(r_1,r_2) \Psi_{\sigma_2}(r_2) \Psi_{\sigma_1}(r_1)dr_1^3dr_2^3.\end{aligned}

Eq.(28)

Expanding in the Wannier basis,

.. math::

   \begin{aligned}
   \label{secQuantGeneric}
   H =\sum_{ij,\alpha\sigma} t_{ij}^\alpha c_{i\sigma}^{\alpha\dagger}c_{j\sigma}^{\alpha} +\sum_{ijl\mathbf{m}}\sum_{\alpha\beta\gamma\delta}\sum_{\sigma\sigma^\prime} U_{ijl\mathbf{m}}^{\alpha\beta\gamma\delta} c_{i\sigma}^{\alpha\dagger}c_{i\sigma^\prime}^{\beta\dagger}c_{l\sigma^\prime}^{(\gamma)}c_{\mathbf{m}\sigma}^{(\delta)}.\end{aligned}

Eq.(29)

Here we extracted the hopping matrix element

.. math::

   \begin{aligned}
   t_{ij}^\alpha = \int W^{\alpha*}(r-R_i) \hat{h} W^\alpha(r-R_j) dr^3\end{aligned}



and many-body interactions
.. container:: Eq.array*

   U\_ijl^ = W^(r-R_i)W^(r^-R_j) U(r,r^) W^()(r^-R_l)W^()(r-R\_m) dr^3
   dr^.

In real materials, the determination of either Bloch states :math:`\varepsilon_k^\alpha` or Wannier states :math:`W_\alpha` is highly non-trivial. Considering the Wannier wavefunction describes the electrons near a given ion site, it is convenient to use the linear combination of atomic wavefunctions as an approximation of Wannier function, which is called *tight-binding approximation*. A typical example is the Slater-Koster hopping matrix elements (Slater and Koster, 1954).

Under the tight-binding assumption, the matrix elements are calculated up to a few neighbors with decaying strength. In this thesis, we usually adopt the two-dimensional single-band square lattice, whose non-interacting representation is :math:`\mathcal{H}=\varepsilon_{k}n_{k}` where :math:`n_k= \sum_\sigma c_{k\sigma}^\dagger c_{k\sigma}` is the density operator and band dispersion

.. math::

   \begin{aligned}
   \label{chp1:eqBareBandStruc}
   \varepsilon_{k}=-2t\left[\cos(k_x)+\cos(k_y)\right]-4t^\prime\cos(k_x)\cos(k_y)-2t^{\prime\prime}\left[\cos(2k_x)+\cos(2k_y)\right].\end{aligned}
   
Eq.(30)

Reordering the second-quantized Hamiltonian Eq. (29)
according to various interaction forms, it can be expressed as

.. math::

   \begin{aligned}
   H = H_{kin} + H_U + H_{U^\prime} + H_J + H_{J^\prime}\end{aligned}
   
   

in which the :math:`H_{\rm kin}` is kinetic energy, :math:`H_U/H_{U^\prime}` are Coulomb interactions and :math:`H_J/H_{J^\prime}` are exchange interactions. The kinetic :math:`H_{kin}` includes all quadratic terms :math:`H_{kin} %&=& \sum_{\gamma\gamma^\prime}\sum_{i,\sigma} \left[ t^x_{\gamma\gamma^\prime} c^\dagger_{i+\hat{x},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^y_{\gamma\gamma^\prime} c^\dagger_{i+\hat{y},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^{xx}_{\gamma\gamma^\prime} c^\dagger_{i+2\hat{x},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^{xy}_{\gamma\gamma^\prime} c^\dagger_{i+\hat{x}+\hat{y},\gamma^\prime\sigma}c_{i,\gamma\sigma}\right.\\ &&\left. + t^{yy}_{\gamma\gamma^\prime} c^\dagger_{i+2\hat{x},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^{xxy}_{\gamma\gamma^\prime} c^\dagger_{i+2\hat{x}+\hat{y},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^{xyy}_{\gamma\gamma^\prime} c^\dagger_{i+\hat{x}+2\hat{y},\gamma^\prime\sigma}c_{i,\gamma\sigma} + t^{xxyy}_{\gamma\gamma^\prime} c^\dagger_{i+2\hat{x}+2\hat{y},\gamma^\prime\sigma}c_{i,\gamma\sigma}+h.c. \right]\\\ = \sum_{k\sigma}\sum_{\alpha\alpha^\prime} c^{(\alpha^\prime)\dagger}_{k\sigma}\xi_{\alpha\alpha^\prime}(k)c_{k\sigma}^\alpha` while the potential terms are defined as

*on-site Coulomb interaction*

.. math::

   \begin{aligned}
   H_U=\sum_\alpha U_\alpha\sum_{i}n_{i\uparrow}^\alpha n^\alpha_{i\downarrow}=\sum_\alpha \frac{U_\alpha}{L}\sum_{k_1,k_2,q}c^{\alpha\dagger}_{k_2+q,\uparrow}
   c^{\alpha\dagger}_{k_1-q,\downarrow}c^\alpha_{k_1,\downarrow}c^\alpha_{k_2,\uparrow},\end{aligned}

*inter-orbital interaction*

.. math::

   \begin{aligned}
   H_{U^\prime}=\sum_{\alpha\neq\alpha^\prime} \frac{U^\prime_{\alpha\alpha^\prime}}{2}\sum_{i,\sigma,
   \sigma^\prime}n^\alpha_{i\sigma}n^{(\alpha^\prime)}_{i\sigma^\prime}=\sum_{\alpha\neq\alpha^\prime} \frac{U^\prime_{\alpha\alpha^\prime}}{2L}\sum_{\sigma,
   \sigma^\prime}\sum_{k_1,k_2,q}c^{\alpha\dagger}_{k_2+q,\sigma}
   c^{(\alpha^\prime)\dagger}_{k_1-q,\sigma^\prime}c^{(\alpha^\prime)}_{k_1,\sigma^\prime}c^\alpha_{k_2\sigma},\end{aligned}

*orbital-flip terms*

.. math::

   \begin{aligned}
   H_J=\sum_{\alpha\neq\alpha^\prime}\frac{J_{\alpha\alpha^\prime}}{2}\sum_{i,\sigma,\sigma^\prime}
   c^{\alpha\dagger}_{i\sigma} 
   c^{(\alpha^\prime)\dagger}_{ i\sigma^\prime} 
   c^\alpha_{i\sigma^\prime}
   c^{(\alpha^\prime)}_{i\sigma}=\sum_{\alpha\neq\alpha^\prime} \frac{J_{\alpha\alpha^\prime}}{2L}\sum_{\sigma,
   \sigma^\prime}\sum_{k_1,k_2,q}
   c^{\alpha\dagger}_{k_2+q,\sigma}
   c^{(\alpha^\prime)\dagger}_{k_1-q,\sigma^\prime}
   c^\alpha_{k_1\sigma^\prime}
   c^{(\alpha^\prime)}_{k_2\sigma},\end{aligned}

and *pair-hopping terms*

.. math::

   \begin{aligned}
   H_{J^\prime}=\sum_{\alpha\neq\alpha^\prime} \frac{J^\prime_{\alpha\alpha^\prime}}{2}\sum_{i}\sum_{\sigma\neq
   \sigma^\prime}c^{\alpha\dagger}_{i\sigma} 
   c^{\alpha\dagger}_{i\sigma^\prime} 
   c^{(\alpha^\prime)}_{i\sigma^\prime}
   c^{(\alpha^\prime)}_{i\sigma}=\sum_{\alpha\neq\alpha^\prime} \frac{J^\prime_{\alpha\alpha^\prime}}{2L}\sum_{\sigma \neq
   \sigma^\prime}\sum_{k_1,k_2,q}
   c^{\alpha\dagger}_{k_2+q,\sigma}
   c^{\alpha\dagger}_{k_1-q,\sigma^\prime}
   c^{(\alpha^\prime)}_{k_1\sigma^\prime}
   c^{(\alpha^\prime)}_{k_2\sigma}.
   %&=&\sum_{\alpha\neq\alpha^\prime} \frac{J^\prime_{\alpha\alpha^\prime}}{L}\sum_{k_1,k_2,q} c^{\alpha\dagger}_{k_2+q,\uparrow} c^{\alpha\dagger}_{k_1-q,\downarrow}c^{(\alpha^\prime)}_{k_1\downarrow} c^{(\alpha^\prime)}_{k_2\uparrow} 
   \end{aligned}

B. Variants of the Hubbard Model
--------------------------------

While charge reservoir layers introduce doped carriers, the CuO\ :math:`_2` planes are believed to capture the strong correlations and interactions relevant to the cuprate phase diagram. Therefore, the electronic physics of cuprates is believed to lie in minimal copper-oxide models that represent the copper :math:`3d_{x^2-y^2}` and oxygen :math:`2p_{x/y}` valence orbitals.

A tight-binding model containing these orbitals and the strongcorrelations among them is called three-band Hubbardmodel:raw-latex:`\cite{mattheiss1987electronic, varma1987charge, emery1987theory}`, whose Hamiltonian reads

.. math::

   \begin{aligned}
   \label{chp1:realSpace3BH}
   \mathcal{H}=-\sum_{\langle i,j\rangle \sigma}t_{pd}^{ij}(d^{\dagger}_{i\sigma}p_{j\sigma}+h.c.)-\sum_{\langle j,j'\rangle \sigma}t_{pp}^{jj'}(p^{\dagger}_{j\sigma}p_{j'\sigma}+h.c.)+\sum_{i\sigma}\epsilon_dn^d_{i\sigma}+\sum_{j\sigma}\epsilon_pn^p_{j\sigma}+\sum_i U_dn^d_{i\uparrow}n^d_{i\downarrow}+\sum_{j\alpha} U_pn^p_{j\uparrow}n^p_{j\downarrow}\end{aligned}

Eq.(31)

where :math:`d^\dagger_{i\sigma}` (:math:`p^\dagger_{j\sigma}`) creates a hole with spin :math:`\sigma` at a copper site :math:`i` (oxygen site :math:`j`) and :math:`n^d_{i\sigma}` (:math:`n^p_{j\sigma}`) is the copper (oxygen) hole number operator.The first two terms of the Hamiltonian represent the nearest-neighborncopper-oxygen and oxygen-oxygen hybridization. The hopping integrals (:math:`t_{pd}^{ij}` and :math:`t_{pp}^{jj'}`) change sign with a :math:`d`-symmetry. The third term in the Hamiltonian represents the charge-transfer energy :math:`\Delta=\varepsilon_p-\varepsilon_d`, while the last two terms are the onsite Hubbard interactions on copper and oxygen, respectively.

**1. Three-Orbital Model in Momentum Space**

Considering the translational symmetry, it is usually convenient to write the model in momentum space. Defining the Fourier transform of fermionic operators

.. math::

   d^{\dagger}_k=\frac1{\sqrt{L}}\sum_i e^{ik\cdot r_i}d^{\dagger}_i\,,\quad
   p^{(x)\dagger}_{k}=\frac1{\sqrt{L}}\sum_{j} e^{ik\cdot r_j}p^{\dagger}_j,\quad\textrm{and}\quad
   p^{(y)\dagger}_{k}=\frac1{\sqrt{L}}\sum_{j^\prime} e^{ik\cdot r_{j^\prime}}p^{\dagger}_{j^\prime}.

Eq.(32)
   
Note the hopping integrals :math:`t_{pd}^{ij}` and :math:`t_{pp}^{jj^\prime}` follow :math:`d`-symmetry of :math:`i-j`. Therefore, the momentum-space representation reads

.. math::

   \begin{aligned}
   \mathcal{H}%&=&-\sum_{\langle i,j\rangle \sigma}t_{pd}^{ij}(d^{\dagger}_{i\sigma}p_{j\sigma}+h.c.)-\sum_{\langle j,j'\rangle \sigma}t_{pp}^{jj'}(p^{\dagger}_{j,x\sigma}p_{j',y\sigma}+h.c.)\nonumber\\
   %&&+\sum_{i\sigma}\epsilon_dn^d_{i\sigma}+\sum_{j\sigma}\epsilon_pn^p_{j\sigma} +\sum_i U_dn^d_{i\uparrow}n^d_{i\downarrow}+\sum_{j\alpha} U_pn^p_{j\uparrow}n^p_{j\downarrow}\nonumber\\
   %&=&\sum_{k\sigma}(\xi^{pdx}_k d^{\dagger}_{k\sigma}p_{k,x\sigma} +h.c.)+\sum_{k\sigma}(\xi^{pdy}_k d^{\dagger}_{k\sigma}p_{k,y\sigma} +h.c.) +\sum_{k\sigma}\xi^{pp}_k(p^{\dagger}_{k\sigma x}p_{k\sigma y}+h.c.)+\sum_{k\sigma}\epsilon_dn^d_{k\sigma}\nonumber\\
   %&&+\sum_{k'\sigma}\epsilon_pn^p_{k'\sigma}
   %+ \frac{U_d}{N}\sum_{k_1,k_2,q}d^{\dagger}_{k_2+q\uparrow}d^{\dagger}_{k_1-q\downarrow}d_{k_1\downarrow}d_{k_2\uparrow}
   %+\frac{U_p}{N}\sum_{\alpha=x,y}\sum_{k'_1,\k'_2,q}p^{\dagger}_{k'_2+q\,\alpha\uparrow}p^{\dagger}_{k'_1-q\,\alpha\downarrow}p_{k'_1\alpha\downarrow}p_{k'_2\alpha\uparrow}\nonumber\\
   &=&\sum_{k\sigma}(d^{\dagger}_{k\sigma},p^{(x)\dagger}_{k\sigma},p^{(y)\dagger}_{k\sigma})
   \left(
     \begin{array}{ccc}
       \epsilon_d & \xi^{pdx}_k & \xi^{pdy}_k \\
       -\xi^{pdx}_k & \epsilon_p & \xi^{pp}_k \\
       -\xi^{pdy}_k & \xi^{pp}_k & \epsilon_p \\
     \end{array}
   \right)
   \left(
     \begin{array}{c}
       d_{k\sigma} \\
       p^{(x)}_{k\sigma} \\
       p^{(y)}_{k\sigma} \\
     \end{array}
   \right)\\
   &&+ \frac{U_d}{L}\sum_{k_1,k_2,q}d^{\dagger}_{k_2+q\uparrow}d^{\dagger}_{k_1-q\downarrow}d_{k_1\downarrow}d_{k_2\uparrow}
   +\frac{U_p}{L}\sum_{\alpha=x,y}\sum_{k'_1,k'_2,q}p^{\alpha\dagger}_{k'_2+q\,\uparrow}p^{\alpha\dagger}_{k'_1-q\,\downarrow}p^\alpha_{k'_1\downarrow}p^\alpha_{k'_2\uparrow},\nonumber\end{aligned}

Eq. (33)

where :math:`\xi^{pdx}_k=2it_{pd}\sin(\frac{k_xa}{2})`, :math:`\xi^{pdy}_k=2it_{pd}\sin(\frac{k_ya}{2})` and :math:`\xi^{pp}_k=-4t_{pp}\sin(\frac{k_xa}{2})\sin(\frac{k_ya}{2})` set the single-body Hamiltonian matrix.

**2. The Single-Band Hubbard Model**

To simplify the three-band model, it was noted that the charge-transfer nature leads to the d − p bonding and antibonding states. Therefore, one can approximately define new Wannier orbitals forming the spin singlet or triplet pairs

.. math::

   \begin{aligned}
   c_{i\sigma}^{\pm}=\frac1{\sqrt{2}} \left( \tilde{p}_{i\bar{\sigma}}d_{i\sigma}\pm \tilde{p}_{i\sigma}d_{i\bar{\sigma}} \right).\end{aligned}

Eq. (34)

The low-energy physics lies in the spin singlet part :math:`c_{i\sigma}^{-}`, named Zhang-Rice singlet:raw-latex:`\cite{zhang1988effective}`. For simplicity, we write it :math:`c_{i\sigma}` without confusion. Under Zhang-Rice picture, the minimal physics of cuprates lies in the single-band Hubbard model:

.. math::

   \label{chp1:realspacehubbard}
   H_{\rm Hubbard} = -\sum_{ i,j, \sigma} t_{ij} \left( c^\dagger_{j\sigma} c_{i\sigma} +h.c.\right)  + U\sum_{i}n_{i\uparrow}n_{i\downarrow}

Eq. (35)

where :math:`U` is the on-site Coulomb repulsion and :math:`t_{ij}` is the hopping integral between site :math:`i` and :math:`j`. In a regular crystalline structure, :math:`t_{ij}` decays with the distance :math:`|i -j|`. Thus, it is usually truncated to nearest neighbor hopping :math:`t`, next-nearest neighbor hopping :math:`t^\prime`.

For convenience, the momentum representation of single-band Hubbard model is frequently used

.. math::

   \label{chp1:kspacehubbard}
   H_{\rm Hubbard} = \sum_{ k, \sigma}\varepsilon_{k} c^\dagger_{k\sigma} c_{k\sigma}  + \frac{U}{L}\sum_{k_1,k_2,q}c^{\dagger}_{k_2+q\uparrow}
   c^{\dagger}_{k_1-q\downarrow}c_{k_1\downarrow}c_{k_2\uparrow}.

Eq. (36)

Here all the kinetic information is included in the band structure :math:`\varepsilon_{k}`.

The complexity of Hubbard model is highly dependent on its spatial dimension and parameters. What is more interesting is U >> t as a prototype of correlated electrons.

Symmetries and conserved quantities are significant in solving and analyzing the physical properties of a system, especially the low-temperature or ground state behavior. In most spin-1/2 tight-binding models, the Hamiltonian possesses at least :math:`U(1)\times U(1)` symmetry. This comes from particle :math:`\hat{N}` and spin :math:`S_z` conservation. Consider the :math:`U(1)` transformation :math:`c_{i\sigma} \rightarrow c_{i\sigma}e^{i\theta}` and :math:`c_{i\sigma}^\dagger \rightarrow c_{i\sigma}^\dagger e^{-i\theta}`. It is easy to show that the fermion-paired Hamiltonian :math:`H` is symmetric under this :math:`U(1)` transformation, which is equivalent to a conservation of particle number :math:`[H, \hat{N}] = 0` where :math:`\hat{N} = \sum_{i} (c_{i\uparrow}^\dagger c_{i\uparrow}+c_{i\downarrow}^\dagger c_{i\downarrow})`. Similarly, under a :math:`c_{i\sigma} \rightarrow c_{i\sigma}e^{i\sigma\theta}` which is isomorphic to :math:`U(1)`, we found another symmetry, indicating the conservation of :math:`\hat{S}_z = \sum_{i} (c_{i\uparrow}^\dagger c_{i\uparrow}-c_{i\downarrow}^\dagger c_{i\downarrow})`. These conservations are generic and not restricted to Hubbard model.

Without external field, the single-band Hubbard model usually has more spin symmetry than :math:`U(1)`. One can easily verify that the total spin operator :math:`\vec{S} = \frac12\sum_{i}\sum_{a,b\in\{\uparrow,\downarrow\}} c_{i a}^\dagger \vec{\sigma}_{ab}  c_{i b}` commutes with the Hubbard Hamiltonian. Thus, the symmetry of :math:`H_{\rm Hubbard}` in Eq. (35) is increased to :math:`U(1)\times SU(2)`. Furthermore, the charge conservation can be replaced by the particle-hole symmetry in a bipartite lattice for the Hubbard model with only nearest neighbor hopping, leading to a :math:`SU(2)\times SU(2)=SO(4)`.

Also as what has been used in the previous sections, the Hamiltonian has a geometric translational symmetry :math:`\big[H,\mathcal{T}\big]=0` in an infinite plane (or equivalently with periodic boundary conditions). Other geometric symmetries such as rotation, reflection, and inversion are also usually considered to simplify the problem.

**3. The Extended Hubbard Model**

In the projection into single-band models, there exist some other interaction terms which are not typically considered. In some special situations discussing, for example, interaction-induced phase transitions, an extended Hubbard model may be considered. Beyond the on-site Coulomb repulsion, the density interaction between neighbors and next neighbors are sometimes considered as a simple way to drive charge-density-wave (CDW) orders. This includes

.. math::

   \begin{aligned}
   H_{\rm ex-Hubbard} = H_{\rm Hubbard} + V\sum_{\langle i,j\rangle\atop \sigma\sigma^\prime} c_{i\sigma}^\dagger c_{j\sigma^\prime}^\dagger c_{j\sigma^\prime}c_{i\sigma}
   + V^\prime\sum_{\langle\!\langle i,j\rangle\!\rangle\atop \sigma\sigma^\prime} c_{i\sigma}^\dagger c_{j\sigma^\prime}^\dagger c_{j\sigma^\prime}c_{i\sigma}.\end{aligned}

Eq. (37)

C. Spin Models
--------------

Although the zeroth order or atomic limit Hubbard model displays a Mott gap, the physics inside upper or lower Hubbard band is attractive as it determines the dynamics in the vicinity of half-filling. Therefore, by projecting out the double occupancies, the low-energy physics of Hubbard model can be well approximated by spin models.

Let :math:`D = \sum_{i}n_{i\uparrow}n_{i\downarrow}`,
then the Hubbard model can be written as

.. math::

   \begin{aligned}
   H_{\rm Hubbard} = H_{KE} + UD .\end{aligned}
   
   
   
According to the commutation with :math:`D`, the :math:`H_{KE}` can be divided into three parts :math:`H_{KE} = \mathcal{T}_0 + \mathcal{T}_+ + \mathcal{T}_-`, in which

.. math::

   \begin{aligned}
   \mathcal{T}_- = -t\sum_{\langle i,j\rangle\sigma} \left(1-n_{i\bar{\sigma}}\right)c_{i\sigma}^\dagger c_{j\sigma} n_{j\bar{\sigma}},\quad
   \mathcal{T}_+ = -t\sum_{\langle i,j\rangle\sigma} n_{j\bar{\sigma}} c_{j\sigma}^\dagger c_{i\sigma}\left(1-n_{i\bar{\sigma}}\right)\end{aligned}

Eq. (38)

and

.. math::

   \begin{aligned}
   \mathcal{T}_0 = -t\sum_{\langle i,j\rangle\sigma} \left[\left(1-n_{i\bar{\sigma}}\right)c_{i\sigma}^\dagger c_{j\sigma} \left(1-n_{j\bar{\sigma}}\right) + n_{j\bar{\sigma}} c_{j\sigma}^\dagger c_{i\sigma}n_{i\bar{\sigma}}\right]\end{aligned}

Eq. (39)

They follow the relation

.. math::

   \begin{aligned}
   \left\{\begin{array}{l}
   \left[D, \mathcal{T}_0 \right] = 0\\
   \left[D, \mathcal{T}_\pm \right] = \pm\mathcal{T}_\pm
   \end{array}\right.\end{aligned}
   
Eq. (40)
   
Note the operator :math:`\mathcal{T}_+` (:math:`\mathcal{T}_-`) creates (annihilates) doublons, while :math:`\mathcal{T}_0` (:math:`D`) projects into single (double) occupied subspace. Making use of this property, one could design the canonical transformation perturbatively decoupling these two subspaces by eliminating :math:`\mathcal{T}_+` and :math:`\mathcal{T}_-`. Assume :math:`S = \frac{t}{U}S_1 + \frac{t^2}{U^2} S_2 + O\left(\frac{t^3}{U^3}\right)`, then

.. math::

   \begin{aligned}
   e^{iS}H_{\rm Hubbard} e^{-iS} = H_{\rm Hubbard} + i\left[S,H_{\rm Hubbard}\right] - \frac12\big[S, \left[S,H_{\rm Hubbard}\right]\big] + O(S^3).\end{aligned}

Eq. (41)

The zeroth order expansion reads

.. math::

   \begin{aligned}
   \textrm{zeroth order}=\mathcal{T}_0 + \mathcal{T}_+ + \mathcal{T}_- + UD + i\left[\frac{t}{U}S_1,UD\right] \Rightarrow\ \  i\left[tS_1,D\right] = - \mathcal{T}_+ -\mathcal{T}_-,\end{aligned}

of which simplest solution is :math:`S_1 = \frac1{it} \left(\mathcal{T}_+ -\mathcal{T}_-\right)`.

Similarly, the first order reads

.. math::

   \begin{aligned}
   \textrm{first order}=i\left[\frac{t}{U}S_1,\mathcal{T}_0 + \mathcal{T}_+ + \mathcal{T}_-\right] +i\left[\frac{t^2}{U^2}S_2, UD\right]-\frac12\left[\frac{t}{U}S_1,\left[\frac{t}{U}S_1,UD\right]\right]=\frac1{U} \left[\mathcal{T}_+,\mathcal{T}_-\right]\end{aligned}

The last step is obtained by selecting :math:`S_2` so that :math:`t\left[S_2,D\right]= -\left[S_1,\mathcal{T}_0\right]`. In fact, this has to be satisfied since both terms contribute nothing to the subspace-invariant operators.

Thus, the first-order perturbation theory projects the Hubbard model in to single- and double-occupied subspaces:

.. math::

   \begin{aligned}
   \label{chp1:effHamtJ}
   H_{\rm eff}\approx e^{iS}H_{\rm Hubbard} e^{-iS}=\mathcal{T}_0 + UD + \frac1{U} \left[\mathcal{T}_+,\mathcal{T}_-\right].\end{aligned}

Eq.(42)

According to the canonical decomposition in Eq. (42), the effective Hamiltonian approximately lies in the eigenspace of :math:`D`. Since we are most interested in the low-energy physics, let us consider its projection into :math:`D =0` subspace by :math:`\mathcal{P}_0`

.. math::

   \begin{aligned}
   \label{chp1:tJHam1}
   \mathcal{P}_0H_{\rm eff}\mathcal{P}_0 &\approx &\mathcal{P}_0\mathcal{T}_0\mathcal{P}_0 - \frac1{U} \mathcal{P}_0\mathcal{T}_-\mathcal{T}_+\mathcal{P}_0\nonumber\\
   &=& -t\sum_{\langle i,j\rangle\sigma} \tilde{c}_{i\sigma}^\dagger \tilde{c}_{j\sigma}-\frac{t^2}{U}\sum_{\langle\textbf{m}ij\rangle\atop\sigma}\left[
            \tilde{c}^\dagger_{\textbf{m}\sigma} \tilde{n}_{i\bar{\sigma}}
            \tilde{c}_{j\sigma}
       -    \tilde{c}^\dagger_{\textbf{m}\bar{\sigma}}
               \tilde{c}^\dagger_{i\sigma}\tilde{c}_{i\bar{\sigma}}
            \tilde{c}_{j\sigma}
            \right].\end{aligned}
			
Eq. (43)


Here, we define the correlated annihilation operator :math:`\tilde{c}_{i\sigma}  = c_{i\sigma} \left(1- n_{i\bar{\sigma}}\right)`. If we ignore those :math:`\textbf{m} \neq j` terms which vanish at half-filling, assuming :math:`\textbf{m} = j`, the formula can be further simplified using spin operators

.. math::

   \begin{aligned}
   S_{i}^{z}  = \frac12 \left(\tilde{n}_{i\uparrow}-\tilde{n}_{i\downarrow}\right),\quad
   S_{i}^{+}  = \tilde{c}_{i\uparrow}^\dagger \tilde{c}_{i\downarrow},\quad
   S_{i}^{-}  = \tilde{c}_{i\downarrow}^\dagger \tilde{c}_{i\uparrow}\,.\end{aligned}

Eq. (44)

Therefore, we obtain the :math:`t-J` model

.. math::

   \begin{aligned}
   \label{chp1:tJHam2}
   H_{t-J} = -t\sum_{\langle i,j\rangle\sigma} \tilde{c}_{i\sigma}^\dagger \tilde{c}_{j\sigma}+J\sum_{\langle ij\rangle}\left[
            \mathbf{S}_i\cdot \mathbf{S}_j - \frac14\tilde{n}_i\tilde{n}_j\right]\end{aligned}

Eq. (45)

with :math:`J= 4t^2/U`. While :math:`t-J` model is widely used in describing the antiferromagnetism (Chao et al., 1977, 1978; Belinicher and Chernyshev, 1994; Belinicher et al., 1994), the full expression of the second-order perturbative Hamiltonian further includes the *three-site terms*

.. math::

   \begin{aligned}
   \label{chp1:tJ3sHam}
   H_{t-J-3s} = H_{t-J}
            -\frac{J}{4}\sum_{\langle\textbf{m}i\rangle,\langle ij\rangle\atop\textbf{m}\neq j,\sigma}\left[
            \tilde{c}^\dagger_{\textbf{m}\sigma} \tilde{n}_{i\bar{\sigma}}
            \tilde{c}_{j\sigma}
       -    \tilde{c}^\dagger_{\textbf{m}\bar{\sigma}}
               \tilde{c}^\dagger_{i\sigma}\tilde{c}_{i\bar{\sigma}}
            \tilde{c}_{j\sigma}
            \right].\end{aligned}
			
Eq. (46)

These extra terms reflect a correlated hopping mechanisms through three continuous sites, with the help of an intermediate spin (Belinicher and Chernyshev, 1994; Belinicher et al., 1994; Stephan and Horsch, 1992; Jefferson et al.,
1992; Bala et al., 1995; Spalek, 1988; von Szczepanski et al., 1990; Eskes and Ole ́s, 1994; Eskes et al., 1994; Belinicher
et al., 1996a,b; Psaltakis, 1992; Eskes and Eder, 1996; Daghofer et al., 2008; Wohlfeld et al., 2008; Kuz’min et al.,
2014).

D. Phonon and Electron-Phonon Coupling
--------------------------------------

The generic electron-phonon coupling can be written as

.. math::

   \begin{aligned}
   \label{chp1:eqGeneraleph}
   H_{}
   =-\frac1{\sqrt{L}} \sum_{k,q,\nu} g_\nu(k,q) c_{k+q}^\dagger c_{k}\left(a_q+a^\dagger_{-q}\right)+\sum_{q,\nu}\Omega_\nu(q) a_q^\dagger a_q.\end{aligned}

Eq. (47)

Inside the sum, the :math:`\nu` branch phonon scatters an electron at momentum :math:`k` into :math:`k+q` with amplitude :math:`g_\nu(k,q)`. Here we omit the orbital indices of the electron to simplify our discussion. The phonon branches can be acoustic or various optical types depending on the form of vibrations, which determines both the dispersion :math:`\Omega_\nu(q)` and the coupling vertex :math:`g_\nu(k,q)`.

**1. The Holstein Model**

The Holstein phonon assumes exclusively local  with Einstein dispersion. In momentum representation, it requires :math:`g_{(\rm Holstein)}(k,q)\equiv g`. The Holstein model reads

.. math::

   \begin{aligned}
   H^{\rm (Holstein)}_{}= -g\sum_j c_j^\dagger c_j (a_j+a_j^\dagger)+\Omega_0 \sum_j a_j^\dagger a_j=-\frac{g}{\sqrt{L}} \sum_{k,q}(c_k^\dagger c_{k-q} a_q+c_k^\dagger c_{k+q} a^\dagger_q)+\Omega_0 \sum_k a^\dagger a_k.\end{aligned}

Eq. (48)

Here, each site is assigned an independent phonon mode and :math:`e-ph` couplings are treated locally. The phonon energy is estimated as Einstein model to mimic optic phonons with no dispersion.

When considering inelastic electron-phonon coupling, the second order electron-phonon term can be included

.. math::

   \begin{aligned}
   H^{\rm (Holstein)}_{e-2ph}&=& -g_2\sum_j n_j \left(a_j+a_j^\dagger\right)^2\\
   %&=&-\frac{g_2}{L^2} \sum_j\sum_{k_1 k_2 q_1 q_2}e^{-i(k_1-k_2)\cdot j}c_{k_1}^\dagger c_{k_2}\left(a_{q_1}e^{iq_1\cdot j}+h.c.\right)\left(a_{q_2}e^{iq_2\cdotj}+h.c.\right)\\
   &=&-\frac{g_2}{L} \sum_{k,q_1,q_2}\left[
   c_{k+q_1+q_2}^\dagger c_{k}a_{q_1}a_{q_2}
   +c_{k+q_1-q_2}^\dagger c_{k}a_{q_1}a^\dagger_{q_2}\right.\nonumber\\
   &&\left.
   +c_{k-q_1+q_2}^\dagger c_{k}a_{q_1}^\dagger a_{q_2}
   +c_{k-q_1-q_2}^\dagger c_{k}a_{q_1}^\dagger a^\dagger_{q_2}\right].\end{aligned}

Note, with the existence of second-order couplings, the quadratic phonon potential can be not sufficient to support a bound state. In this case, the anharmonicity of phonon energy also has to be considered. The discussion of non-linear coupling anharmonicity is beyond the scope of this thesis, but is an important extension for further studies.

**2. Bond-Phonon Peierls Model**

At half-filled electronic states, the coupling near nesting momentum
:math:`q_{\rm nest}` usually dominates the underlying order.
Therefore, we introduce the Peierls bond-phonon model, which simplifies
the lattice degrees of freedom to a uniform dimerization. In momentum
representation,
:math:`g_{(\rm Peierls)}(k,q)= \frac{g}{\sqrt{L}}\delta_{q,q_{\rm nest}}`.
In 1D system, such a nesting momentum is :math:`q_{\rm nest} = \pi`.
Therefore, the :math:`e-ph` part of Hamiltonian reads:

.. math::

   \label{chp1:eqPeierlsHubbard}
   \mathcal{H}^{\rm (Peierls)}_{}=-\frac{g}{\sqrt{L}}(b^\dagger +b)\sum_{i,\sigma}(-1)^in_{i\sigma}+\Omega_0\, b^\dagger b,

Eq. (49)

where :math:`b^\dagger` and :math:`b` are the phonon creation and annihilation operator, respectively. Such a phonon mode is highly nonlocal, coupling to a overall charge order at the nesting momentum.

Extending into 2D systems with bipartite geometry, the nesting momentum lies in the boundary of first Brillouin zone (BZ). Typically in a square lattice, the :math:`e-ph` part of Hamiltonian reads:

.. math::

   \label{chp1:eqPeierlsHubbard2D}
   \mathcal{H}^{\rm (Peierls)}_{}=-\frac{g}{\sqrt{L}}(b^\dagger +b)\sum_{i,\sigma}(-1)^{i_x+i_y}n_{i\sigma}+\Omega_0\, b^\dagger b.

Eq. (50)

**3. Forward Scattering**

In contrast to the localized Holstein coupling and nested Peierls coupling, the small-:math:`q` or so-called forward scattering sometimes play more significant role in describing the coupling between electrons with optical phonons. To describe this type of coupling mechanism at the surface or interface solid states, two models are used in this thesis.

The Thomas-Fermi model describes the linear screening of an impurity in a free electron gas. The screened Coulomb potential is described by

.. math::

   \begin{aligned}
   \left[\nabla^2-q_{\rm TF}^2\right] V(r) = 4\pi e \rho_{\rm imp}(r),\end{aligned}
   
Eq. (51)

where :math:`q_{\rm TF} = \sqrt{6\pi e^2 n_0/E_F}` with :math:`n_0` the average electron density and :math:`E_F` Fermi level. The model results in a exponential spatial screening of a point charge :math:`V(r) = - {eQ_{\rm imp}}e^{-q_{\rm TF} |r|}/|r|`. Applied to the electron-phonon coupling, the Thomas-Fermi scattering vertex is

.. math::

   \begin{aligned}
   \label{chp1:eqTFephCoupling}
   g_{(\rm Thomas-Fermi)}(k,q)= \frac{4\pi g_0}{1+|q|^2/q_{\rm TF}^2}.\end{aligned}

Eq. (52)

However, the power-law decay in momentum space is still quasi-local interactions. To depicts the forward scattering at 2D surface or interface, an exponential coupling vertex is required

.. math::

   \begin{aligned}
   \label{chp1:eqExpCoupling}
   g_{(\rm Exp)}(k,q)= g_0 \exp\left(-|q|/q_0\right).\end{aligned}
   
Eq. (53)

This type of coupling can better describe the electronic structure at surface states such as SrTiO3(Lee et al., 2014; Wang et al., 2016a,b).

**4. Lang-Firsov Transfromation**

The zeroth order behavior of forward scattering can be approximately estimated by assuming the momentum scale :math:`q_0` or :math:`q_{\rm TF}` goes to zero. Under this assumption, the canonical second quantized Hamiltonian for :math:`q=0`  coupling reads

.. math::

   \begin{aligned}
   \label{chp1:eqLangFirsov}
   H=\sum_{k} \varepsilon_k c^\dagger_k c_k -g_0(a^\dagger +a)\sum_k c^\dagger_k c_k  +\Omega_0 a^\dagger a\end{aligned}

Eq. (54)

with :math:`\sum_{k} c^\dagger_k c_k =N_e` in canonical ensemble. Define :math:`\lambda={g_0N_e}/{\omega_0}` and another bosonic operator :math:`b=a-\lambda`, then the Hamiltonian becomes :math:`H=\sum_{k} \varepsilon_k c^\dagger_k c_k  +\Omega_0 b^\dagger b -\omega_0\lambda^2` whose ground state is phonon vacuum in :math:`b` basis, therefore a coherent state with :math:`a` phonon

.. math::

   \begin{aligned}
   |G\rangle =  \prod_{|k|<k_F}c_k^\dagger e^{-|\lambda|^2/2} e^{\lambda a^\dagger}|0\rangle.\end{aligned}

Eq. (55)

After some algebra, one can get the spectral function displaying *phonon
shake-off*

.. math::

   \begin{aligned}
   A(k, w) = -\frac1{\pi}\textrm{Im} G^h(k, w+i\Gamma) \rightarrow \sum_{m}\delta\left(\omega-E_m\right)\left|\mathcal{A}_k^{(m)}\right|^2\end{aligned}

Eq. (56)

where
:math:`E_m=\varepsilon_k -m\omega_0 - \frac{2g_0^2}{\omega_0}N_e` and
the intensity follows Poisson distribution

.. math::

   \begin{aligned}
   \label{chp1:eqLangFirsovWeights}
   \left|\mathcal{A}_k^{(m)}\right|^2 = e^{-g_0^2/\omega_0^2}\frac{(g_0^2/\omega_0^2)^m}{m!}.\end{aligned}

Eq. (57)

