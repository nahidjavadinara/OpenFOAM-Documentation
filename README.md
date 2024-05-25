# OpenFOAM-Documentation
 Installation and Regression Testing of OpenFOAM 

 OpenFOAM is a C++ toolbox for the development of customized numerical solvers, and pre-/post-processing utilities for the solution of continuum mechanics problems, most prominently including computational fluid dynamics (CFD). 
 
 **Scope** It is used in research organizations, academic institutes and across many types of industries, for example, automotive, manufacturing, process engineering and environmental engineering. 
 
**Purpose** The goals of this project are 1) to install recent versions of OpenFOAM on the Uni.lu HPC platform using EasyBuild, and 2) to set up a regression testing configuration for the installed OpenFOAM using ReFrame. 

# ** Running Test Examples for Post Processing Phase** 
  # **simpleCar Example with OpenFOAM v2312** 
   **Loading modules** 
   ```bash
   module load tools/EasyBuild/4.9.1
   module use ~/.local/easyconfig/modules/all
   module load cae/OpenFOAM/v2312-foss-2023a
   ```
Now, we're gonna supposed to download tutorials of openfoam v2312, then put them in openfoam directory that we have created for motorbike example: 
   ```bash
   wget https://develop.openfoam.com/Development/openfoam/-/archive/OpenFOAM-v2312/openfoam-OpenFOAM-v2312.zip?     path=tutorials/incompressible/simpleFoam -O openfoam-OpenFOAM-v2312-tutorials-incompressible-simpleFoam.zip
  ```

   
  