# dpmd_data
We provied the deep potential model and training data for LYC/LYBC system in our publication: xxxxxxx

The frozen_model.pb are the trained model using the Deepmd_kit (v2.0) based on the training database in the same folder. More details about the Deepmd_kit methods could be found here: https://github.com/deepmodeling/deepmd-kit

Using the trained potental to run an MD simulation with LAMMPS is simple. In the LAMMPS input file, one needs to specify the pair style as follows

<img width="322" alt="image" src="https://user-images.githubusercontent.com/43861983/210843997-98ef469d-8a92-4f65-bb88-f3003c3ce13d.png">

where frozen_model.pb is the file name of the frozen model. It should be noted that LAMMPS counts atom types starting from 1, therefore, all LAMMPS atom types will be firstly subtracted by 1, and then passed into the DeePMD-kit engine to compute the interactions.
