# DFinder：A novel end-to-end graph embedding-based method to identify drug-food interactions

Drug-food interactions (DFIs) occur when some constituents of food affect the bioaccessibility or efficacy of the drug by involving in drug pharmacodynamic (PD) and/or pharmacokinetic (PK) processes. Many computational methods have achieved remarkable results in link prediction tasks between biological entities which show the potential of the computational methods in discovering novel DFIs. However, there are few computational approaches that pay attention to DFI identification. This is mainly due to the lack of drug-food interaction data. In addition, food is generally made up of a variety of chemical substances. The complexity of food makes it difficult to generate accurate feature representations for food. Therefore, it is urgent to develop effective computational approaches for learning the food feature representation and predicting drug-food interactions. In this paper, we first collect drug-food interaction data from DrugBank and PubMed respectively to construct two datasets, named DrugBank-DFI and PubMed-DFI. Based on these two datasets, two DFI networks are constructed. Then, we propose a novel end-to-end graph embedding-based method named DFinder to identify DFIs. DFinder combines node attribute features and topological structure features to learn the representations of drugs and food constituents. In topology space, we adopt a simplified graph convolution network-based method to learn the topological structure features. In feature space, we use a deep neural network to extract attribute features from the original node attributes. The evaluation results indicate that DFinder performs better than other baseline methods.
## Enviroment Requirement
`pip install -r requirements.txt`

## Dataset

We provide two processed datasets: drugbank-DFI and pubmed-DFI. See more in `data`

## An example to run DFinder

run DFinder on **drugbank-DFI** dataset:

* change directory

Change `ROOT_PATH` in `code/world.py`

* command

` cd code && python main.py --decay=1e-4 --lr=0.001 --layer=3 --seed=2020 --dataset="drugbank-DFI" --topks="[20]" --recdim=64`

*NOTE*:

* If you want to run pubmed-DFI dataset, you need to change the data storage directories in `code/model.py` and `code/dataloader.py`.
* If you want to run DFinder on your own dataset, you should go to dataloader.py, and implement a dataloader inherited from BasicDataset. Then register it in register.py.
* If you want to run your own models on the datasets we offer, you should go to model.py, and implement a model inherited from BasicModel. Then register it in register.py.

## Acknowledgments
We really thank Xiangnan He et al. open the source code of LightGCN at this [link](https://github.com/gusye1234/LightGCN-PyTorch). The LightGCN helps us to extract the topological structure features on the DFI network.
