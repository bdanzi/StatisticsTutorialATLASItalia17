# StatisticalTutorialATLASItalia17
Very short statistical tutorial (RooFit + RooStats) at ATLAS Italia 2017

## Setup

We are using lxplus to setup ROOT. Any other machine with a recent version of ROOT should work. We are using Jupyter notebook as interface.

    ssh lxplus
    setupATLAS
    lsetup ROOT
    lsetup git

If you have problem with `setupATLAS` it may be it is not defined for your account. In this case define it:

    export ATLAS_LOCAL_ROOT_BASE=/cvmfs/atlas.cern.ch/repo/ATLASLocalRootBase
    alias setupATLAS='source ${ATLAS_LOCAL_ROOT_BASE}/user/atlasLocalSetup.sh'

Then clone this git repository, you can use the folder as working directory

    git clone git@github.com:wiso/StatisticalTutorialATLASItalia17.git
    cd StatisticalTutorialATLASItalia17

Now let setup additional software as jupyter. We are doing it with a virtualenv, just copy and paste:

    virtualenv -p `which python` venv
    source venv/bin/activate
    pip install --upgrade pip
    pip install --upgrade setuptools
    export CC=`which gcc`
    pip install ipython jupyter

This should take a couple of minutes.

### Create tunnel to your machine

We are not using X-redirection, but Jupyter notebook. Just copy and paste these commands:



## What to do when relogin

If you close the lxplus session, if you want to relogin you just need to do:

    ssh lxplus
    setupATLAS
    lsetup ROOT
    lsetup git
    cd StatisticalTutorialATLASItalia17
    source venv/bin/activate

and then recreate the tunnel. Very important: the number here represent a port which should not be used by others (it is quite usual to find collision), so *use a random number of four digits different from the one here*:

    ./notebook.sh 7695

If a collission happens you will find a message as "The port 7695 is already in use, trying another port." It is ok, but take note ok the alternative port used in the message as

    Copy/paste this URL into your browser when you connect for the first time, to login with a token:
        http://127.0.0.1:7696/?token=30c3334279e1fbafe2780fd5570081f7131339fa645be274

Then open a new console on your machine (not lxplus) and run the command suggested by the output of the previous commands, but change the port in case of collision, as:

   ssh -N -f -L 7696:localhost:7696 lxplus085.cern.ch

Here 7696 is used instead of 7695 because of a collision. The name of machine is different from you, use the one in the output of the command. Answer 'yes' if a question is prompted. The asked password is the lxplus one.

Open a browser from your machine and connect to url suggest by the output as (the token is a sort of password and different for everybody, as the port)

    http://127.0.0.1:7696/?token=30c3334279e1fbafe2780fd5570081f7131339fa645be274

Then just clic on the right: new -> python2.