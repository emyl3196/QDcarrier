# QDcarrier

This repository contains a kinetic monte carlo (KMC) code for simulating carrier transport in a 3-D quantum dot (QD) assembly in the case of QDs with symmetric valence and conduction band alignment.

The authors request that all published work which utilizes this KMC code include the following citation:

	Rachel H. Gilmore, Elizabeth M. Y. Lee, Mark C. Weidman, Adam P. Willard, and William A. Tisdale. "Charge Carrier Hopping Dynamics in Homogeneously Broadened PbS Quantum Dot Solids" Nano Letters, vol. 17, pp. 893-901 (2017).

------------------------------------------------

#input files: 

input_ma

start.inpt

------------------------------------------------

#Run command:

	./ma_hop_bcc_2 < input_ma [QD index] > out_[QD index]

where [QD index] is the initial carrier site (i.e. index of the quantum dot in which carrier is localized)

e.g. to do carrier transport simulation starting from carrier initialized at QD index 10:

	./ma_hop_bcc_2 < input_ma 10 > out_10

------------------------------------------------

#Format of "input_ma" file

column 1: QD index

column 2: QD band gap energy

columns 3 to 5: QD coordinate (x,y,z)

------------------------------------------------

#Format of "start.inpt" file

line 1: total number of QDs

line 2: total number of monte carlo trajectories starting with carrier initialized at the input QD index

line 3: interparticle spacing (QD center to center spacing) [nanometer]

lines 4 through 6: periodic box dimension in x,y,z [nanometer]

line 7: nearest-neighbor hopping time prefactor [picoseconds]

line 8: KMC simulation end time [picoseconds]

line 9: QD radius [nanometer]

line 10: cutoff reduced radius (distance/interparticle spacing) for the KMC simulation to speed up the rate matrix calculation 
      *need to be greater than 1.0 in the case of non-nearest neighbor calculation or a disordered lattice
      

