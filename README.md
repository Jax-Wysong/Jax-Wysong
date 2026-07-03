# Hi, I'm Jax Wysong

I am currently pursuing a PhD at Michigan State University in computational math, science, and engineering (CMSE) and physics. I have degrees in Physics (BS) and Math (MS) from South Dakota State University (SDSU). At MSU, I work under advisors Brian O'Shea and Andrew Christlieb in the HighZ group ([HighZ-Center](https://highz-fic.github.io/)), where I am developing high-order finite volume methods for magnetohydrodynamics modeling.

My current work focuses on:
1. Implementing constrained transport (CT) into AthenaPK ([athenaPK](https://github.com/parthenon-hpc-lab/athenapk))
    - AthenaPK is a performance-portable, adaptive mesh refinement code used to develop (magneto)hydrodynamics simulations for astrophysical applications
        - Based on Athena++, Parthenon, and Kokkos
    - Solving the MHD equations requires that the $\nabla \cdot \mathbf{B} = 0$ constraint be numerically satisfied
        - One method of enforcing this is called constrained transport, which involves updating the magnetic fields according to the EMF defined on grid corners
    - Some studies indicate that CT is a more robust scheme when compared to other methods handling the divergence-free constraint
2. Numerical investigations of ghost field dynamics ([arxiv](https://arxiv.org/abs/2604.25635))
    - Klein-Gordon equation with a ghost field and nonlinear potential
    - Spacetime FEM for discretization
    - PETSc (DMDA, SNES) for parallelism and nonlinear solvers
    - Map out regions of stability for ghost-systems with varying initial conditions
3. Development/study of time-parallel additive Schwarz preconditioners
    - Scalar advection equation and wave equation discretized via the spacetime FEM
    - PETSC (DMDA, KSP, PC) for parallelism, linear solvers, and user-defined preconditioning implementation
    - Implement a time-domain decomposition additive Schwarz scheme to precondition GMRES
        - Find that a physics-informed-Krylov interface-condition provides a consistent speed-up in GMRES convergence (manuscript draft in progress)
4. Mentoring REU student at SDSU
     - Spacetime FEM numerical method development to solve the inviscid Burger's equations


In the past, I worked on  
- Plasma physics & magnetic reconnection (LANL Computational Physics Workshop)
- Magnetic materials and Heusler alloys (undergraduate experimental materials science)

## Publications
- Numerical Investigations of Stable Dynamics in the Presence of Ghosts ([Arxiv-Version](https://arxiv.org/abs/2604.25635))
- Multiple publications on Heusler alloys
*(See full list of publications and presentations in my CV)*

## Featured Repositories
- **[FVM-(magneto)hydrodynamics](https://github.com/Jax-Wysong/FVM-Hydro_MHD)** - Python-based finite volume solvers for many problems
  - **Scalar advection, inviscid Burgers, 1- and 2D Euler's**
    - following Mike Zingale's *Introduction to Computational Astrophysical Hydrodynamics*
  - 1- and 2D Ideal MHD
    - HLL and HLLD Riemann solvers
    - PCM, PLM, and PPM interface reconstruction (characteristic slope projection in PLM - 2D MHD code)
    - CT with SSPRK2 for time integration for 2D Ideal MHD
    - Brio-Wu shocktube, and Dai-woodward problem for 1D code verification
    - Field loop advection and smooth MHD vortex convergence testing for 2D code verification
- **[Parallel Spacetime FEM Solver (1+1 and 2+1)](https://github.com/Jax-Wysong/Space-Time-FEM-public)** - PETSc-based linear and nonlinear PDE solver  
  - **Ghost Field Numerical Experiments** – code used to investigate how different initial conditions and potentials effect a nonlinear ghost system of 2 scalar fields
  - **Linear Heat and Wave Eqn Problems** - linear problems used to test and understand numerical and parallel implementation
  - **Time-Parallel Preconditioning** - development/study of time domain decompositon restricted additive Schwarz preconditioning


## Technical
C • Python • PETSc • HPC clusters • FEM • FVM • Numerical Methods • (Magneto)hydrodynamics • MATLAB 

## Contact/Links
Email: wysongj2@msu.edu

CV: [CV (PDF)](./WysongJax_CV.pdf)

LinkedIn: [LinkedIn](https://www.linkedin.com/in/jax-wysong-008051221)


