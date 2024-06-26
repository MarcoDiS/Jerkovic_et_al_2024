

+-----------------------+-+
|                       | |
| Current version: pipeline_v0.1.0  |
|                       | |
+-----------------------+-+


TADphys.

Documentation
*************

**Create TADphys conda enviroment**
To use TADphys, we recommend to insatll the package manager conda from 'https://conda.io/projects/conda/en/latest/user-guide/install/index.html'.
Next, you can use the provided TADphys.yml to create the TADphys enviroment (Execution time ~30 minutes)
   | conda env create -f TADphys.yml

**Install LAMMPS as a shared library**
   | 1 - Download lammps
   | git clone -b stable https://github.com/lammps/lammps.git mylammps
   
   | 2 - Install lammps as a shared library
   | cd ../../src/
   | include "-DLAMMPS_EXCEPTIONS" in the LMP_INC line in src/MAKE/Makefile.mpi
   | make yes-molecule
   | make mpi mode=shlib
   | make install-python

   | cd ../../

**Install TADphys**
   | 1 - Download TADphys from the Github repository
   | git clone https://github.com/MarcoDiS/TADphys.git -b TADphys TADphys

   | 2 - Install TADphys
   | cd TADphys
   | python setup.py install
   | cd ..

Citation
********
Please, cite this article if you use TADphys.

Ivana Jerković, Marco Di Stefano, Hadrien Reboul, Michael F Szalay,  Davide Normanno, Giorgio L Papadopoulos, Frederic Bantignies, Giacomo Cavalli.
**A Scaffolding Element Rewires Local 3D Chromatin Architecture During Differentiation.**
*bioRxiv* 642009; `doi.org/10.1101/2024.05.23.595561`_

Methods implemented in TADphys
-----------------------------
In the actual implementation, TADphys relies on TADdyn [DiStefano]_ and TADbit [Serra]_ for the general structure of the package and LAMMPS [Plimpton]_ for the implementation of the simulations.

Bibliography
************

.. [DiStefano] Di Stefano, M. et al. Transcriptional activation during cell reprogramming correlates with the formation of 3D open chromatin hubs. Nature communications 11 (1), 1-12 (2020).
	       
.. [Serra] Serra, F. et al. Automatic analysis and 3D-modelling of Hi-C data using TADbit reveals structural features of the fly chromatin colors. PLoS Comp Biol 1005665 (2017).
	   
.. [Plimpton] Plimpton, S. Fast Parallel Algorithms for Short-Range Molecular Dynamics. J Comp Phys 117, 1-19 (1995).


