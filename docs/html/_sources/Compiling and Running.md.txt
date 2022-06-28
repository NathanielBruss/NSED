Compiling and Running
=====================

A. Compile the code
---------------------

The compilation is automated in the Makefile:
***

make EXECUTABLE

***

where the “EXECUTABLE” is the target program defined above.

For different machines, one shoud change the definition of compilers and flags. For example, in NERSC where
environment has been predefined, one can call “CC“ as an abstract compiler

***

CXX = CC #-std=c++14
FLAGS = -O3 -no-prec-div -static -fp-model fast=2 -xHost -openmp

***

Instead, in TACC one should use specific MPI compiler and “static“ does not work

***

CXX = mpicxx
FLAGS = -O3 -no-prec-div -fp-model fast=2 -xHost -openmp

***

B. Dependent Libraries
----------------------

Most of the program is based on Eigen data structure. The ground state calculation (diagonalization) lies in
PARPACK dynamic libaray, though an alternative Lanczos class is also provided. The solution of PDE depends on
the Odeint libaray in boost.

To compile the code, one should provide the path for Eigen and Boost in the Makefile, together with the link to
the dynamics libaray of PARPACK and ARPACK.

Typically, both Eigen and Boost are modules in a supercomputer. One should “module load eigen“ and “module
load boost“ before compiling the code. These paths should be provided in the Makefile as

***

HEADERLIBS = $(EIGEN3)/eigen3 -I$(BOOST_DIR)/include

***

The expansion of these paths read as

***

-I/global/common/cori/software/eigen3/3.3.3/include/eigen3
-I/usr/common/software/boost/1.67.0/intel/haswell/include

***

in NERSC (Cori). In contrast, the PARPACK is not necessarily capsulated as a module. If a “parpack“ module is
availabe, one can “module load parpack“ before compiling the code, and include the paths as

***

OBJLIBS = $(PARPACK)

***

The path reads as

***

-L/usr/common/software/parpack/3.2.0/hsw/intel/lib -larpack -lparpack
in NERSC (Cori).

***

C. Run in a supercomputer cluster
---------------------------------


A hybrid MPI + OpenMP parallelization has been implemented in the program. To run a hybrid code, please
read the instruction of your supercomputer. A typical “SLURM“submission script looks like (here is the script for
NERSC)

***
Batch Script
***
#!/bin/sh  
#SBATCH -J JOBNAME  
#SBATCH -p debug  
#SBATCH --nodes=10  
#SBATCH -t 00:15:00  
#SBATCH --tasks-per-node=8  
#SBATCH --cpus-per-task=8  
#SBATCH --constraint=haswell  
#SBATCH -e job.err  
#SBATCH -o job.out  
#SBATCH -V   

cd $SLURM_SUBMIT_DIR  
rm job.*  
rm *.txt  

export OMP_PROC_BIND=true  
export OMP_PLACES=threads  
export OMP_NUM_THREADS=4  
srun ./testNonEquilibriumDynamics >& mylog  

***

It is highly recommended to test the parallelization configurations before heavy batch submissions. Timing is
embedded in the code, convenient for such test. The MPI communication overhead is typically larger than the
shared-memory OpenMP, therefore, maximizing OMP NUM THREADS is recommended for small problems. However, for
the construction of Hilbert space, sparse matrix and some observable evaluations, the read/write overhead is also
obvious for the shared-memory scheme. A typical choice of OMP NUM THREADS is about 4-12.