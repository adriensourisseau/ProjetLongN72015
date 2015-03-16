# ProjetLongN72015

This repository provides the frameworks MoMA and
Pinocchio updated for the benchmarking of both 
analytical and numerical method. 

In order to set up properly the provided package, 
you need first to install urdfdom and urdfdom_header-master
to, then, install pinocchio. After that you can install MoMA. 

The set up instructions come as follow for all the provided packages. 

Setup
-----

To compile all provided packages, it is recommended to create 
a separate build (every build already exist but are empty) directory:

    mkdir _build
    cd _build
    cmake [OPTIONS] ..
    make install


###### MoMA ########
The integration of the Pinocchio library is made in 
the makefile of psf-amc. At this occasion, a folder 
in psf-amc/include/solver_numeric has been created to 
support the pinocchio standard on the benchmark platform. 

The src file tripeptide_ik.cpp contains 
a class named solve_numerique which : 

-Call to the numerical solver : amc_Tripeptide::solve_numerique
--> Perform the transformation model associated to the 
given suchain to be computable by the numerical solver

- Processing data from both solver : amc_Tripeptide::sort_solution_IK6R_VS_NumericalSolver
--> Generate a file which compare all the returned solution from both solver : 
      > The distance between the non-perturbed configuration and all the returned solutions.
      > The distance between the closest solution (from the analytical method) and all the returned solutions.
    > Take into account time execution, number of iteration of the numerical solver.

- Generate .pdb file from both solver : amc_Tripeptide::generate_pdb_file



