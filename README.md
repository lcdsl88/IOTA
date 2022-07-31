# IOTA Simulation using OMNeT++

This git is a decentralized simulation of [IOTA](https://www.iota.org/) which is a crypto-currency using [OMNeT++](https://omnetpp.org/). It implements two kind of modules : the malicious ones that can launch an attack and the honest ones representing the regular user. For better performance, the simulation uses OpenMP for multithreading.

This simulation can use several topologies:

- **Complete graph**
- **2D grid**
- **Torus**
- **Watts-Strogatz**

As the simulation is handling two types of modules and the .NED format is very restrictive, you have to use the **topologies** folder which contains the **GenTopo.py** script allowing to generate the wanted topology. The simulation will then read the .csv created by the script to build the network (this part is done by the **ConfiguratorModule**). It is also necessary to install the **networkx and the matplotlib modules.**

The **data** folder contains all the tracking files allowing to:

- generate an image of the Tangle using the script **TangleGen.py** (you need however to install the **graphviz** module). The SVG figure will then be saved in the **image** folder.
- compute an average of the **number of tips** at the end of each simulation and the simulation **execution time** using the **Stats.py** script (**glob** module needed).

The simulation implements three different **TSA** (Tips Selection Algorithm):

- **IOTA**: www.descryptions.com/Iota.pdf
- **G-IOTA**: <https://ieeexplore.ieee.org/document/8845163>
- **E-IOTA**: <https://ieeexplore.ieee.org/document/9223294>

And two types of **attacks** explained in the IOTA [paper](www.descryptions.com/Iota.pdf):

- **Splitting Attack**
- **Parasite Chain Attack**

To evaluate the success of each of these attacks, the simulation can compute and export the following data in the tracking folder:

- the **percentage difference** in size between the two branches (splitting attack)
- the **number** of transactions that are part of the parasite chain (parasite chain attack)

## Credit

I did this project while I was an intern at [LIP6](https://www.lip6.fr/), so I want to thank all its team.  

Special thank to **Richard Gardner** ([@richardg93](https://github.com/richardg93)) who helped me a lot during the beginning thanks to his [git](https://github.com/richardg93/TangleSim) but also to **Gewu Bu** ([@GewuBU](https://github.com/GewuBU)) who guided me during my internship.
