# StatisticalTutorialATLASItalia17
Very short statistical tutorial (RooFit + RooStats) at ATLAS Italia 2017

## Setup

We are using lxplus to setup ROOT. Any other machine with a recent version of ROOT should work. We are using Jupyter notebook as interface.

    ssh lxplus
    mkdir stat-tutorial; cd stat-tutorial
    setupATLAS
    lsetup ROOT

If you have problem with setupATLAS it may be it is not defined for your account. In this case define it:

    export ATLAS_LOCAL_ROOT_BASE=/cvmfs/atlas.cern.ch/repo/ATLASLocalRootBase
    alias setupATLAS='source ${ATLAS_LOCAL_ROOT_BASE}/user/atlasLocalSetup.sh'
