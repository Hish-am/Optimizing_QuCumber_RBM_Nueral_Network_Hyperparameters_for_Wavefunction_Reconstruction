# Optimizing_QuCumber_RBM_Nueral_Network_Hyperparameters_for_Wavefunction_Reconstruction
In this short project I investigated the effect of Optimizing `QuCumber's` Hyperparameters on the Training of its `Restricted Boltzmann machine` Neural Network for Wavefunction Reconstruction. More specifically, using one of the datasets in QuCumber's documentation, I reconstruct a positive-real wavefunction by training QuCumber's *Restricted Boltzmann Machine* (RBM) neural network, however here, I used the `COBYLA algorithm` from `SciPy` to optimize the neural network's hyperparameters and compared it to the recommended list of hyperparamters in the tutorials found on the documentation page, followed by a comparison to the default parameters. The best performace was indeed found to be that of the optimized parameters. The Trace-based Metric I used also seemed to give a sharper contrast, compared to both `Fidelity` and `KL Divergence`, between reconstructed and true functions and one might find it advantageous for comparing closeness of states.  

NB: According to QuCUmber's online documentation page "The data used for training are <img src="https://render.githubusercontent.com/render/math?math=\sigma^{z}"> measurements from a one-dimensional transverse-field Ising model (TFIM) with 10 sites at its critical point."


### Steps:  
#### 1.0 Training:  

1.1. Importing the `QuCumber Library` and setting up the `training dataset`.  
1.2. Introducing the Hyperparameters.  
1.3. Defining our metric functions for quantizing the "distance" between generated and actual states.  
1.4. Constructing our `cost functions` for optimization based off of our metric function.  
1.5. `Optimization` of the `training hyperparameters`.  
  
#### 2.0 Evaluating the reconstruction results from the 3 cases, Default, Recommended and Optimized  

2.1. Preparing the training function for the three cases with appropriate parameters.  
2.2. Plotting and evaluating results and comparisons.  
2.3. `Saving the weights` determined by the training along with the hidden and visible biases as Torch tensors.  



The plots and data show that the recommended hyperparameters produced a fidelity of approximately `0.987`, while the default hyperparameters yield approximately `0.769`, and finally my optimized parameters yielded `0.995` but it still took longer to train, so the feasability of choosing to optimize might not be that great, I could further include running times in my optimization but that is something I leave for later.

<p align="center" width="100%">
<img src="https://github.com/Hish-am/Optimizing_QuCumber_RBM_Nueral_Network_Hyperparameters_for_Wavefunction_Reconstruction/blob/main/images/Graphs.png" width="550">

