Input Files
===========

A. General Options
------------------
option.config gives the global program options, including bottom-level matrix format, progress control and
alternative input file names

**Configuration and option file (option.config)**

::

	ProgControl= Write
	HamiltonianSplitDiag: Yes
	#########
	Parameter input file: model_params2.in
	HilbertSpaceParameter input file: hilb.in
	#########
	Spectra input file: spec_params.in


|
	

B. Input Files for Models
-------------------------
**1. Hilbert-Space Configuration**

The Hilbert-space parameter input file (usually named as hilbertspace params.in) sets the basic information
about cluster shape, size, dimension, boundary condition, spatial representation, filling and addition restrictions.

The Hilbert space input file contain many aspects of information
- Cluster – cluster size and name (required). It specifies the system size and geometry. The cluster name follows Beth clusters.
- ElectronicSiteNumber or Orbital number. It specifies the total size × orbital number, or orbital number separately. For example, setting ElectronicSiteNumber :16 above is equivalent to setting Orbital: 2.
- Dimension – the system dimension, 1D or 2D.
- Boundary – boundary condition.
- Representation – whether the many-body state is written in real or reciprocal space. It can be ‘Momentum‘ only when ‘Boundary‘ is ‘Periodic‘.
- Momentum specifies the total momentum of the system. It can only be specified when ‘Boundary‘ is ‘Periodic‘.
- Occupancy specifies the total electron occupation. The spin up and down occupations can be further specified, e.g. Occupancy: 8(3,5).

**Hilbert space input file**
	.. container:: leftside

		::
		
			Cluster: 8A
			ElectronicSiteNumber: 8
			Dimension: 2D
			Boundary: Periodic
			Representation: Momentum
			Momentum: 0
			Occupancy: 8

	.. container:: rightside

		| cluster size and name: the Betts 8A cluster
		| total size × orbital number = 8 (orbital number = 1)
		| the system is 2D
		| periodic boundary condition
		| momentum-space representation
		| total momentum is restricted to the zeroth one in the cluster
		| total 8 electron occupation
		

	
|

Below is an example for a single-band system with open boundary and no double occupation (usually for the
t − J-like spin models).

**Hilbert space input file**
	.. container:: leftside

		::
		
			Cluster: 16
			ElectronicSiteNumber: 16
			Dimension: 1D
			Boundary: Open
			Representation: Real
			#Momentum: 0
			Occupancy: 14(8,6)
			Restrictions: NoDouble

	.. container:: rightside

		| cluster size and name:16-site chain
		| total size × orbital number = 16 (orbital number = 1)
		| the system is 1D
		| open boundary condition
		| real-space representation
		| the # comments out unused options
		| total 14 electron occupation, with 8 up and 6 down
		| restricted to be no doubly occupied
		

|

Below is an example for a two-orbital system with (single-mode) phonons.

**Hilbert space input file**
	.. container:: leftside

		::
		
			Cluster: 8
			ElectronicSiteNumber: 16
			Dimension: 1D
			Boundary: Periodic
			Representation: Momentum
			Occupancy: 14(8,6)
			MaxPhononNumber: 500
			PhononModeNumber: 1
			PhononMomenta: 0
			

	.. container:: rightside

		| cluster size and name: 8-site chain
		| total size × orbital number = 16 (orbital number = 2)
		| the system is 1D
		| periodic boundary condition
		| momentum-space representation (without specifying momentum)
		| total 8 electron occupation, with 8 up and 0 down
		| maximal phonon number
		| only a single mode of phonon is included
		| this phonon has momentum 0
		

|

Below is an example for a multi-orbital system with one orbital set to be idle (usually used to representing the
x-ray core-level).

**Hilbert space input file**
	.. container:: leftside

		::
		
			Cluster: 8A
			ElectronicSiteNumber: 32
			Dimension: 2D
			Boundary: Periodic
			Representation: Momentum
			Occupancy: 39
			Conservations: orbital 3[0]
			

	.. container:: rightside

		| cluster size and name: 8A Betts cluster
		| total size × orbital number = 32 (orbital number = 4)
		| the system is 2D
		| periodic boundary condition
		| momentum-space representation
		| total 39 electron occupation
		| the orbital #3 has zero electron
				



|

**2. Model Hamiltonian Parameters**

The model parameter input file (usually named as model params.in) sets the overall model parameters in the
following format


**Model parameter input file**
	.. container:: leftside

		::
		
			Hubbard
			U= 8 V= 0
			t= 1 t’= -0.3 t’’= 0.2
			

	.. container:: rightside

		| the name of the model (giving some default settings)
		| Hubbard U and extended Hubbard interaction V
		| hoppings, nearest-neighbor t and longer-range t′ and t''
				




|

.. image:: /Graphics/Fig_BettsCluster.png
  :width: 800
  :alt: Alternative text
  
FIG. 2 Typical Betts supported in the calculation.


**Model parameter input file**
	.. container:: leftside

		::
		
			Hubbard[2band]
			Es[]=
			      -1.8  3.1
			tx[]=
			      -0.75 0
			       0    0.9
			txx[]=
			      -0.15 0
			       0 0.45
			txxx[]=
			      -0.05 0
			       0    0.3
			g[]=
			       0.0 -0.02
			      -0.02 0
			W[]=
			       0   0.008
			       0.008 0
			

	.. container:: rightside

		| the name of the model (band number should be specified)
		| site-energy Es for two bands
		| 
		| x-direction intra- and inter-band nearest-neigbhor hopping
		| 
		| x-direction intra- and inter-band next-nearest hopping
		| 
		| x-direction intra- and inter-band next-next-nearest hopping
		| 
		| electron-phonon coupling (to a single phonon mode)
		| 
		| phonon energy
					
  
	

|




.. raw:: html

	<embed>
	<table>
	<table border="1">
	<colgroup>
		<col/>
		<col/>
		<col/>
		<col/>
		<col/>
		<col/>
		<col/>
	</colgroup>
	<thead>
	<tr class="header">
	</tr>
	</thead>
	<tbody>
	<tr class="odd">
		<th></th>
		<th>Symbol</th>
		<th>Option</th>
		<th>Index</th>
		<th>Physical Meaning</th>
		<th>Real</th> 
		<th>Reciprocal</th>
		<th>Expression</th>
	</tr>
	<tr class="even">	
		<td rowspan="8">Global Properties</td>
		<td>Sz</td>
		<td></td>
		<td></td>
		<td>net spin</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>&#8721;<sub>i</sub> (n<sub>i&#8593;</sub> - n<sub>i&#8595;</sub>)</td>
	</tr>
	<tr class="odd">	
		<td>N</td>
		<td></td>
		<td></td>
		<td>Electron Occupation</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>&#8721;<sub>i</sub> (n<sub>i&#8593;</sub> + n<sub>i&#8595;</sub>)</td>
	</tr>
	<tr class="even">	
		<td>Mz2</td>
		<td></td>
		<td></td>
		<td>local moment</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>&#8721;<sub>i</sub> (n<sub>i&#8593;</sub> - n<sub>i&#8595;</sub>))<sup>2</sup>/N</td>
	</tr>
	<tr class="odd">	
		<td>N2</td>
		<td></td>
		<td></td>
		<td>double occupation</td>
		<td>&#x2611</td>
		<td></td>
		<td>&#8721;<sub>i</sub> (n<sub>i&#8593;</sub> n<sub>i&#8595;</sub>))</td>
	</tr>
	<tr class="even">	
		<td>PhnNum</td>
		<td></td>
		<td></td>
		<td>phonon occupation</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>&#8721;<sub>i</sub> (a<sub>i</sub><sup>†</sup> a<sub>i</sub>))</td>
	</tr>
	<tr class="odd">	
		<td>Current</td>
		<td>x,y</td>
		<td></td>
		<td>current</td>
		<td></td>
		<td>&#x2611</td>
		<td>&#8721;<sub>k</sub> n<sub>k</sub> cos (k<sub>x/y</sub> - a<sub>x/y</sub>))</td>
	</tr>
	<tr class="even">	
		<td>CurrentPara</td>
		<td>x,y</td>
		<td></td>
		<td>paramagnetic current</td>
		<td></td>
		<td>&#x2611</td>
		<td>&#8721;<sub>k</sub> n<sub>k</sub> cos (k<sub>x/y</sub>))</td>
	</tr>
	<tr class="odd">	
		<td>Enrg</td>
		<td></td>
		<td></td>
		<td>total energy</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>H</td>
	</tr>
	
	
	
	<tr class="even">	
		<td rowspan="6">Single-point</td>
		<td>Sz</td>
		<td></td>
		<td>i/k</td>
		<td>net spin (at site i)</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>n<sub>i&#8593</sub>; - n<sub>i&#8595;</sub></td>
	</tr>
	<tr class="odd">
		<td>N</td>
		<td></td>
		<td>i/k</td>
		<td>electron occupation (at site i)</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td>n<sub>i&#8593</sub>; + n<sub>i&#8595;</sub></td>
	</tr>
	<tr class="even">	
		<td>Nh</td>
		<td></td>
		<td>i</td>
		<td>hole density (at site i)</td>
		<td>&#x2611</td>
		<td></td>
		<td>(1 - n<sub>i&#8593;</sub>)(1 - n<sub>i&#8595;</sub>)</td>
	</tr>
	<tr class="odd">	
		<td>Ns</td>
		<td></td>
		<td>i</td>
		<td>singlon density (at site i)</td>
		<td>&#x2611</td>
		<td></td>
		<td>&#8721;<sub>σ</sub>(1-n<sub>iσ</sub>)n<sub>iσ-bar</sub></td>
	</tr>
	<tr class="even">	
		<td>Nd</td>
		<td></td>
		<td>i</td>
		<td>doubloon density (at site i)</td>
		<td>&#x2611</td>
		<td></td>
		<td> n<sub>i&#8593</sub>; n<sub>i&#8595;</sub></td>
	</tr>
	<tr class="odd">	
		<td>PhnNum</td>
		<td></td>
		<td>i/k</td>
		<td>phonon occupation (at site i)</td>
		<td>&#x2611</td>
		<td>&#x2611</td>
		<td> a<sub>i</sub><sup>†</sup> a<sub>i</sub> </td>
	</tr>
	
	
	
	<tr class="even">	
		<td rowspan="10">Two-point</td>
		<td>SzSz</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>&#8721;<sub>j</sub> S<sub>j</sub><sup>z</sup>S<sub>j+i</sub><sup>z</sup> / N </td>
	</tr>
	<tr class="odd">	
		<td>SzSz+x</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
		<tr class="even">	
		<td>SzSz+y</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j</sub><sup>z</sup>S<sub>j + y&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="odd">	
		<td>SzSz+xy</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j</sub><sup>z</sup>S<sub>j + x&#770 + y&#770</sub><sup>z</sup></td>
	</tr>
		<tr class="even">	
		<td>SzSz+yx</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j</sub><sup>z</sup> S<sub>j + x&#770 - y&#770</sub><sup>z</sup></td>
	</tr>	
	<tr class="odd">	
		<td>Sz-xSz+x</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j  + x&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
		<tr class="even">	
		<td>Sz-ySz+y</td>
		<td></td>
		<td>i</td>
		<td>spin-spin correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>S<sub>j  + y&#770</sub><sup>z</sup>S<sub>j + y&#770</sub><sup>z</sup></td>
	</tr>	
	<tr class="odd">	
		<td>NrNr</td>
		<td></td>
		<td>i</td>
		<td>density-density correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>&#8721;<sub>j</sub> n<sub>j</sub>n<sub>j+i</sub> / N</td>
	</tr>
		<tr class="even">	
		<td>NrNr+x</td>
		<td></td>
		<td>i</td>
		<td>density-density correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>n<sub>i</sub>n<sub>i + x&#770 </sub></td>
	</tr>	
	<tr class="odd">	
		<td>NrNr+y</td>
		<td></td>
		<td>i</td>
		<td>density-density correlation</td>
		<td>&#x2611</td>
		<td></td>
		<td>n<sub>i</sub>n<sub>i + y&#770 </sub></td>
	</tr>
	
	
	
	<tr class="even">	
		<td rowspan=8>Three-point</td>
		<td>NhSz-xSz+x</td>
		<td></td>
		<td>i</td>
		<td>local hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>i</sub>S<sub>j  - x&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="odd">	
		<td>NhSz-ySz+y</td>
		<td></td>
		<td>i</td>
		<td>local hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>i</sub>S<sub>j  - y&#770</sub><sup>z</sup>S<sub>j + y&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="even">	
		<td>NhSz+ySz+x</td>
		<td></td>
		<td>i</td>
		<td>local hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>i</sub>S<sub>j  + y&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="odd">	
		<td>NhSz-ySz+x</td>
		<td></td>
		<td>i</td>
		<td>local hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>i</sub>S<sub>j  - y&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="even">	
		<td>Nh|Sz-xSz+x</td>
		<td></td>
		<td>i</td>
		<td>hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>0</sub>S<sub>j  - x&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="odd">	
		<td>Nh|Sz-ySz+y</td>
		<td></td>
		<td>i</td>
		<td>hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>0</sub>S<sub>j  - y&#770</sub><sup>z</sup>S<sub>j + y&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="even">	
		<td>Nh|Sz+ySz+x</td>
		<td></td>
		<td>i</td>
		<td>hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>0</sub>S<sub>j  + y&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	<tr class="odd">	
		<td>Nh|Sz-ySz+x</td>
		<td></td>
		<td>i</td>
		<td>hole-spin-spin</td>
		<td>&#x2611</td>
		<td></td>
		<td>h<sub>0</sub>S<sub>j  - y&#770</sub><sup>z</sup>S<sub>j + x&#770</sub><sup>z</sup></td>
	</tr>
	</tbody>
	</table>
	</embed>




TABLE I List of supported static observables.


**Model parameter input file**
	.. container:: leftside

		::
		
			Hubbard-Holstein
			U= 8 t= 1 t’= -0.3
			g= 0.1 W= 0.05
			averagedGaugeNum= 10
			

	.. container:: rightside

		| the name of the model (giving some default settings)
		| Hubbard U and the band parameters
		| Holstein-type e-ph coupling g and the phonon energy ω
		| requested number of gauges to average (can be a 2D vector)



|

**Model parameter input file**
	.. container:: leftside

		::
		
			Hubbard-Holstein
			U= 8 t= 1 t’= -0.3
			g= 0.1 W= 0.05
			guage= 0.05 0.01
			

	.. container:: rightside

		| the name of the model (giving some default settings)
		| Hubbard U and the band parameters
		| Holstein-type e-ph coupling g and the phonon energy ω
		| a specific gauge field (with period 2π)


|

Both input files are required to define the model where the calculations was performed. They are called by all
programs.




C. Input Files for Specific Measurements
----------------------------------------


**1. Static Observables**

The observable input file (usally named as ‘obs params.in‘) defines the requested observables in an equilibrium or
nonequilibrium calculation

**Observable input file**
::
	
	ObsType: Mz2 Sz[all] NrNr[0] Nh|SzSz+x[All]

|



One can enumerate all requested static observables here. The square bracket specifies the index. When the index is set
to ‘all‘, it means all symmetrically independent indices (the symmetry is analyzed automatically for different clusters
and calculations). When the index is set to ‘All‘, it means all allowed indices. This input file is required for equilibrium
and pump-probe observable calculations, i.e. ED GROUND OBS, NGSED GROUND OBS, and TDED DYNM.

**2. Spectroscopies**

The spectroscopy input file (usally named as ‘spec params.in‘) defines the requested spectral calculation and
relevant parameters in the follow format

**Spectroscopy input file**
::
	
	SpecType: Sqw N(q,w) Raman[B1g]
	Frequencies: wMin= -5 wMax= 5 wDelta= 0.005

|



Alternatively, for resonant spectrum, one gives more information

**Spectroscopy input file**

	.. container:: leftside

		::
		
			SpecType: RIXS[indir]
			Frequencies: [-20:0.05:20]
			Momentum: 1
			Krylov-subspace: 20
			broadening: 1
			Resonance: omegaIn= -13.5 inverseLifeTime= 2
			PropagatorSolver: KrylovDim= 1000 tol= 1E-6
			

	.. container:: rightside

		| spectral type: indirect RIXS
		| frequency (energy loss) range
		| requested momentum index
		| dimension of continued fraction expansion
		| spectral broadening (energy loss)
		| requested incident energy and inverse lifetime
		| BiCGSTAB parameters

|

The incident energy can be given in a vector form (make sure to check the memory cost). For example,


**Spectroscopy input file**

	.. container:: leftside

		::
		
			SpecType: ResRaman[B1g]
			Frequencies: [-5:0.05:20]
			Krylov-subspace: 20
			broadening: 1
			Resonance: omegaIn= [0:0.2:10] inverseLifeTime= 1
			PropagatorSolver: KrylovDim= 1000 tol= 1E-6
			

	.. container:: rightside

		| spectral type: B1g resonant Raman
		| frequency (energy loss) range
		| dimension of continued fraction expansion
		| spectral broadening (energy loss)
		| incident energies and inverse lifetime
		| BiCGSTAB parameters

|


This input file is required for equilibrium and pump-probe spectral calculations, i.e. CPT GROUND SPEC and TDED TDSPEC.
Attached is a table for all the spectral calculations

**3. Time-Domain Parameters**

The time-evolution input file (usually named as ‘timeparams.in‘) sets the parameters of non-equilibrium dynamics and spectral calculation. It specifies the time discretization (start, end, and interval), pump conditions (gauge field),


  
.. raw:: html

	<embed>
	<table border="1">
	<colgroup>
	<col/>
	<col/>
	<col/>
	<col/>
	<col/>
	</colgroup>
	<thead>
	<tr class="header">
	<th>Spectral Type</th>
	<th>Input Name</th>
	<th>Option</th>
	<th>Index</th>
	<th>Operator O</th>
	</tr>
	<tr class="even">
		<th>charge structure factor N(q,w)</th>
		<th>N(q,w)</th>
		<th>-</th>
		<th>q</th>
		<th>&#8721;<sub>k</sub>c<sub>k+q,&#963;</sub><sup>†</sup>c<sub>kq&#963;</sub></th>
	</tr>
		
	<tr class="odd">
		<th>spin structure factor S(q, ω) </th>
		<th>S(q,w)</th>
		<th>-</th>
		<th>q</th>
		<th>&#8721;<sub>k</sub>&#963;c<sub>k+q,&#963;</sub><sup>†</sup>c<sub>kq&#963;</sub></th>
	</tr>
	
	<tr class="even">
		<th>spectral function A(k, ω)−</th>
		<th>A(k,w)-</th>
		<th>-</th>
		<th>k</th>
		<th>c<sub>k↑</sub><sup>†</sup>c<sub></th>
	</tr>
		
	<tr class="odd">
		<th>inverse spectral function A(k, ω)+</th>
		<th>A(q,w)+</th>
		<th>-</th>
		<th>k</th>
		<th>c<sub>k↑</sub><sup>†</sup></th>
	</tr>
	
	<tr class="even">
		<th>pairing correlation P (q, ω)− </th>
		<th>P(q,w)-</th>
		<th>s, px, d, s+</th>
		<th>q</th>
		<th>&#8721;<sub>k</sub>c<sub>k↑</sub>c<sub>q-k↑</sub></th>
	</tr>
		
	<tr class="odd">
		<th>pairing correlation P (q, ω)+ </th>
		<th>P(q,w)+</th>
		<th>s, px, d, s+</th>
		<th>q</th>
		<th>&#8721;<sub>k</sub>c<sub>q-k ↓ </sub><sup>†</sup>c<sub>k↑</sub><sup>†</sup></th>
	</tr>
	
	<tr class="even">
		<th>coincidence ARPES cA(k, ω)− </th>
		<th>cA(k,w)-</th>
		<th>-</th>
		<th>k</th>
		<th>c<sub>k↑</sub>c<sub>-k↓</sub></th>
	</tr>
		
	<tr class="odd">
		<th>coincidence ARPES cA(k, ω)+</th>
		<th>cA(k,w)+</th>
		<th>-</th>
		<th>k</th>
		<th>c<sub>-k↓</sub><sup>†</sup>c<sub>k↑</sub><sup>†</sup></th>
	</tr>
	
	<tr class="even">
		<th>Raman spectrum R(ω)</th>
		<th>Rm(w)</th>
		<th>A1g, B1g, B2g</th>
		<th>-</th>
		<th>&#8721;<sub>k</sub>   γ(k)n<sub>k</sub></th>
	</tr>
		
	<tr class="odd">
		<th>optical conductivity σ(ω)</th>
		<th>Sig(w)</th>
		<th>x, y</th>
		<th>-</th>
		<th>&#8721;<sub>k</sub>   j(k)n<sub>k</sub></th>
	</tr>

	<tr class="even">
		<th>x-ray absorption I(ω)</th>
		<th>XAS(w)</th>
		<th>dir, indir</th>
		<th>-</th>
		<th>&#8721;<sub>k</sub> c<sub>k↑</sub><sup>†</sup>   p<sub>k↑</sub></th>
	</tr>
		
	</table>
	</embed>


|

TABLE II The supported Lehmann spectral types.

|

.. raw:: html

	<embed>
	<table border="1">
	<colgroup>
	<col/>
	<col/>
	<col/>
	<col/>
	<col/>
	<col/>
	</colgroup>
	<thead>
	<tr class="header">
	<th>Spectral Type</th>
	<th>Input Name</th>
	<th>Option</th>
	<th>Index</th>
	<th>Operator1 O<sub>1</sub></th>
	<th>Operator2 O<sub>2</sub></th>
	</tr>
		<tr class="odd">
		<th>resonant inelastic x-ray scattering I(q, ωin, ω)</th>
		<th>RIXS(q,w,win)</th>
		<th>dir, indir, spin-flip</th>
		<th>q</th>
		<th>&#8721;<sub>k</sub> c<sub>k↑</sub><sup>†</sup>   p<sub>k↑</sub></th>
	</tr>

	<tr class="even">
		<th>resonant Raman scattering R(ωin, ω)</th>
		<th>ResRaman(w,win</th>
		<th>A1g, A2g, B1g, B2g</th>
		<th>-</th>
		<th>&#8721;<sub>k</sub> c<sub>k↑</sub><sup>†</sup>   p<sub>k↑</sub></th>
	</tr>

	<tr class="odd">
		<th>coincidence ARPES cA(k, ωin, ω)</th>
		<th>cARPES(k,k,w,w)</th>
		<th>-</th>
		<th>k</th>
		<th>&#8721;<sub>k</sub> c<sub>k↑</sub><sup>†</sup>   p<sub>k↑</sub></th>
	</tr>
	</table>
	</embed>

|
  
TABLE III The supported Kramers-Heisenberg spectral types.

|
  
parameters modulations (quench or continous modulation), and probe conditions. A typical time-domain input file is in the follow format
  
**Time evolution input file**

	.. container:: leftside

		::
		
			Time: start= 0.05 end= 60 dt= 0.05
			Pump: A0= 1.2 w0= 4.4 sigma= 3.0 t0= 19.0
			Polarization: x= 1 y= 1
			

	.. container:: rightside

		| time discretization
		| pump field A(t) (vector potential)
		| polarization of pump field A(t)


|

This input file is required for the dynamics and pump-probe spectral calculations, i.e. TDED DYNM and TDED TDSPEC. The pump field is represented in an oscillatory Gaussian pulse, with central frequency “w0”, central time “t0”, width (standard deviation) “sigma”, and the peak amplitude “A0”. The polarization of pump pulse is specified in ”Polarization” by its 2D coordinates. Note, for linear polarization, this vector will be normalized. 
There can be multiple pump pulses, to mimic sequential pump conditions. And phase-averaged pump conditions can be specified by giving the number of phases. For example,

**Time evolution input file**

	.. container:: leftside

		::
		
			Time: start= 0.05 end= 100 dt= 0.05
			Pump: A0= 0.4 w0= 5 sigma= 3 t0= 20 Polarization: circular+
			Pump: A0= 0.3 w0= 4 sigma= 3 t0= 40 Polarization: circular-
			PhaseAverage: 10
			

	.. container:: rightside

		| time discretization
		| pump field #1
		| pump field #2
		| phase average number

|

Apart from the realistic pump in terms of the gauge field, some studies require quantum quench or time-dependent modulation of model parameters. This can also be specified in the input field, with or without the pump field. For example,

**Time evolution input file**

	.. container:: leftside

		::
		
			Time: start= 0.05 end= 60 dt= 0.05
			Quench: U[5] t0= 10
			ParamModulation: t centralVal= 1 amp= 0.5 freq= 0.3 sigma= 10 t0= 20
			

	.. container:: rightside

		| time discretization
		| quenching U to 5 at t0 = 10
		| varying t in time

|

The parameter modulation is defined as an oscillatory Gaussian with a central time and central frequency, similar to
the pump field.
The calculation of pump-probe spectroscopies (i.e. TDED TDSPEC) requires an additional line in the input file, specifying the probe conditions.

**Time evolution input file**

	.. container:: leftside

		::
		
			Time: start= 0.05 end= 60 dt= 0.05
			Pump: A0= 1.2 w0= 4.4 sigma= 3.0 t0= 19.0
			Polarization: x= 1 y= 1
			Probe: sigma= 2.0
			

	.. container:: rightside

		| time discretization
		| pump field A(t) (vector potential)
		| polarization of pump field A(t)
		| probe condition (probe width)
				
|

Note, the probe type and frequencies for pump-probe calculations are set in ‘spec params.in‘.

**4. Ensemble Parameters**

The ensemble input file (usually named as ‘ensembleparams.in‘) defines the requested finite-temperature, grand-canonical (unconserved particle numbers), or magnetic field (unconserved total spin) ensembles, in the follow format

**Ensemble input file**

	.. container:: leftside

		::
		
			Temperature= [0:0.02:1]
			ChemPot= [-1:0.05:1]
			NumberOfStates= 100
			
	.. container:: rightside

		| temperature list
		| chemical potential list
		| number of states kept in each sector

|

This input file is required for ED-based equilibrium calculations, i.e. ED GROUND OBS and ED GROUND SPEC. Note, when this input file is missing, the programs will perform ground-state calculations. Technically, ensemble calculations can be supported by the NGSED and CPT methods, but they are to be implemented.

**5. CPT Parameters**

The cluster perturbation theory (CPT) input file (usually named as ‘cpt params.in‘) defines requested CPT calculations in the follow format

**Cluster perturbation theory input file**

	.. container:: leftside

		::
		
			Doping: -4/64
			MomentumDensity: 100
			requestedBZRegion: HighSymmLines
			FermiSurfaceThickness: 0.05
			

	.. container:: rightside

		| percentage of doping (in a supercluster)
		| momentum discretization
		| requested region of BZ
		| integrated thickness for Fermi surface


|

This input file is called only by CPT GROUND SPEC. The standard CPT calculation applies to the single-particle spectral function A(k, ω). However, it can also apply to the two-particle dynamical structure factors, with appropriate adjustment of the vertex. These options should be specified in the spectroscopy input file.
