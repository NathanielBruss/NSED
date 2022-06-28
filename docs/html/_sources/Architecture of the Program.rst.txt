Architecture of the Program
===========================

The general architecture is reflected in the folders.
The Util folder contains all global functions, including global classes (MPI related), math functions, string
operations and timer. The LinearAlgebra folder contains fundamental MPI-based algebra, including the MPI vector
operations, MPI eigen-problem solver, MPI linear problem solver, and the Krylov-subspace exponential solver. Both
folders are generically designed without physical purposes.
The PhysDataStruct folder contains the elementary data structures constitude the exact diagonalization
calculation. The main data structures are:

- Cluster Classes (including ClusterReal and ClusterReciprocal) define the geometric relation, size, dimention and symmetries;
- Hilbert Space Class (including the basis element BasisState and the entire Hilbert-space class HilbertSpace) defines the many-body basis, relevant Fock-space operations, and the space-level operations;
- Hamiltonian Matrix Class – template HamiltonianMatrix, consists of the bottom-level matrix decomposition and matrix-vector product, as well as the high-level matrix construction based on Hamiltonian terms;
- Many-Body State and Operations (including ManyBodyState, ManyBodyOperator and VariationalState) define the wavefunctions and many-body operations.

The MeasureEngines folder contains high-level exact diagonalization calculations of observables, spectroscopies and
dynamics. These classes are directly called by the main function to realize (separately or jointly) a physical purpose.

The main data structures are:

- Equilibrium Engine (including pure ED EquilibriumEngine and variational + ED ‘EquilibriumVariationalEngine‘) sets up the calculation for ground state and low excited states.
- Equilibrium Spectroscopy Engine (including EqSpectrum and CPTSpectrum) sets up the calculation of spectroscopies at equilibrium. It relies on SpectraParams as an input of spectral type and energy/momentum range.
- Nonequilibrium Dynamics Engine – NonEqTimeEvolution calculates the time evolution of an initial wave function after applying a pump field. Observable engine is embedded to measure the instantaneous properties.
- Nonequilibrium Spectroscopy Engine – NonEqSpectrum measures the time-dependent pump-probe spectroscopies. As an extension of both spectroscopy and nonequilibrium dynamics, it takes the input from both wavefunction dynamics and spectral parameters.

Apart from these four main data structures, there are two measurement engines which does not work separately and is embedded in other engines

- Observable Engine – ObservableEngine defines all single-time measurements based on any given wavefunctions. The input/output and reduction operations are embedded in this class. The observable engine is called in other measurement engines.
- Ensemble Engine (including EnsembleParams and EnsembleTransformer) measures ensemble-based properties using multiple excited states.

