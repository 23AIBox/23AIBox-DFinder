* dataloader.py  
  This file loads the divided test and training data, and builds a bipartite graph of drug-food ingredient interactions based on the training data.

* parse.py  
  This file parses the parameters entered by the user when running the code.

* world.py  
  This file defines the path of data and code. In addition, this file will record the parsed parameters so that subsequent code can use the input parameters.

* model.py  
  This file is the model implementation of DFinder. In topological space, we follow the framework of LightGCN and use a simplified graph convolution neural network to propagate node features. In the feature space, we use a three-layer depth neural network to extract node attribute features, and then concatenate the two features together as the final representation of the node.

* utils.py  
  This file mainly implements minibatch and functions for calculating evaluation indicators, such as Recall, Precision, AUC, AUPR.

* Procedure.py  
  This file mainly implements the calculation function of BPR loss function and two functions to evaluate the test data.
 