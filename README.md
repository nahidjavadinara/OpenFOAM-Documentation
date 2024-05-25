# OpenFOAM-Documentation
 Installation and Regression Testing of OpenFOAM 

 OpenFOAM is a C++ toolbox for the development of customized numerical solvers, and pre-/post-processing utilities for the solution of continuum mechanics problems, most prominently including computational fluid dynamics (CFD). 
 
 **Scope** It is used in research organizations, academic institutes and across many types of industries, for example, automotive, manufacturing, process engineering and environmental engineering. 
 
**Purpose** The goals of this project are 1) to install recent versions of OpenFOAM on the Uni.lu HPC platform using EasyBuild, and 2) to set up a regression testing configuration for the installed OpenFOAM using ReFrame. 

# ** Running Test Examples for Post Processing Phase** 
  # **Verification and Validation Example with OpenFOAM v2312** 
   **Loading required modules** 
   ```bash
   module load tools/EasyBuild/4.9.1
   module use ~/.local/easyconfig/modules/all
   module use /work/projects/mhpc-softenv/easybuild/aion-epyc-prod-2023a/modules/all/
   export EASYBUILD_JOB_BACKEND='Slurm'
   export EASYBUILD_PREFIX=$HOME/easybuild
   export EASYBUILD_BUILDPATH=/dev/shm/$USER
  eb /home/users/$USER/.local/easybuild/software/EasyBuild/4.9.1/easybuild/easyconfigs/o/OpenFOAM/OpenFOAM-v2312-foss-2023a.eb --job --job-cores 32 --job-max-walltime 11 --robot --trace
   module use /home/users/$USER/easybuild/modules/all
   module load cae/OpenFOAM/v2312-foss-2023a
   ```
Now, we're gonna supposed to download tutorials of openfoam v2312, then upload them in openfoam directory that we have created for motorbike example: 
   ```bash
   wget https://develop.openfoam.com/Development/openfoam/-/archive/OpenFOAM-v2312/openfoam-OpenFOAM-v2312.zip?     path=tutorials/incompressible/simpleFoam -O openfoam-OpenFOAM-v2312-tutorials-incompressible-simpleFoam.zip
   mkdir -p $HOME/OpenFOAM
   scp openfoam-OpenFOAM-v2312-tutorials-incompressible-simpleFoam.zip $HOME/OpenFOAM
   unzip $HOME/OpenFOAM/openfoam-OpenFOAM-v2312-tutorials-incompressible-simpleFoam.zip -d $HOME/OpenFOAM
   cd $HOME/OpenFOAM/openfoam-OpenFOAM-v2312/tutorials/verificationAndValidation/turbulenceModels/planeChannel
  ```
Source the OpenFOAM Environment Setup

```bash
source /home/users/$USER/easybuild/software/OpenFOAM/v2312-foss-2023a/OpenFOAM-v2312/etc/bashrc
```
Verifying the Environment Variable 
```bash
echo $WM_PROJECT_DIR
```
Execution and running 
```bash
chmod +x Allrun
srun -n 1 -c 32 ./Allrun
./Allrun
```

![image](https://github.com/nahidjavadinara/OpenFOAM-Documentation/assets/161458338/3de03a1c-7e49-459a-a802-5a05b7f6ea08)
