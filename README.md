# dpmd_data
We provied the deep potential model and training data for LYC/LYBC system in our publication: xxxxxxx

The frozen_model.pb are the trained model using the Deepmd_kit (v2.0) based on the training database in the same folder. More details about the Deepmd_kit methods could be found here: https://github.com/deepmodeling/deepmd-kit

Using the trained potental to run an MD simulation with LAMMPS is simple. In the LAMMPS input file, one needs to specify the pair style as follows

pair_style     deepmd frozen_model.pb
pair_coeff     * *

where frozen_model.pb is the file name of the frozen model. It should be noted that LAMMPS counts atom types starting from 1, therefore, all LAMMPS atom types will be firstly subtracted by 1, and then passed into the DeePMD-kit engine to compute the interactions.
