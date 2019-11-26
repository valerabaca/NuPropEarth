# PropEarth
Module to simulation the propagation of neutrinos through the Earth.

These are the main dependencies:

- GENIE3 (w/ HEDIS)
- TAUOLA++

Then GENIE3 (w/ HEDIS) requires several external packages:

- ROOT6
- PYTHIA6
- LHAPDF6
- APFEL


## HOW TO USE IT FIRST TIME

1. Install all the external packages: PYTHIA6,TAUOLA,LHAPDF6,APFEL,ROOT6

2. Download NuPropEarth module on your machine 

```
git clone https://github.com/pochoarus/NuPropEarth.git
cd NuPropEarth
```

3. Define the envioroment in which you will work in source.sh (for instance GENIE,NUEARTHPROP,etc.)

```
source setup.sh
```

4. Install this version of [GENIE3 (w/ HEDIS)](https://https://github.com/pochoarus/GENIE-HEDIS/tree/apfel)

```
git clone https://github.com/pochoarus/GENIE-HEDIS.git $GENIE
cd $GENIE
./configure --enable-lhapdf6 --enable-apfel
make
```

5. Install NuPropEarth in your machine

```
cd ${NUPROPEARTH}
make
```

6. To compute the attenuation you just have to run

```
TUNE=GHE19_00a_00_000 #GHE19_00a_00_000=BGR18(member=0), GHE19_00b_00_000=CSMS11(member=0)
ComputeAttenuation -n NUMBEROFEVENTS -t COSTHETA -p NUPDG --cross-sections $GENIE/genie_xsec/${TUNE}_dx0.01dy0.01_n200_nuall_nucleon_noglres.xml --event-generator-list HEDIS --tune ${TUNE}
```



