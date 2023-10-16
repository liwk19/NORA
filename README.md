Fast Inference of Removal-Based Node Influence (NORA)

How to reproduce our results


1, Train the GNN model

- Planetoid dataset (Cora, Citeseer, PubMed):

cd planetoid

Node classification task: python train.py --model GCN/GraphSAGE/GAT --dataset Cora/CiteSeer/Pubmed

Link prediction task (only support GCN model): python train_link.py --model GCN --dataset Cora/CiteSeer/Pubmed

If you have a specific requiremend of the hidden size, use the argument "--hidden_size".

- ogbn-arxiv dataset

GCN & GraphSAGE models: cd arxiv/simple

Node classification task: python gnn.py --model GCN/GraphSAGE

Link prediction task (only support GCN model): python gnn_link.py --model GCN

obgn-arxiv model: Node classification task: cd arxiv/ogbn-arxiv

./run.sh

- Twitter datasets

cd TIMME/code

python main.py --data P50/P_20_50 --task TIMME --cycle 0/1/2/3/4

The model can jointly learn the node classification and link prediction tasks. Please traverse 0~4 as the cycle, so that you can complete the five experiments which cycle around the data split.

But for evaluating node removal's influence on the link prediction task: python sample_triplet.py


2, Choose a method to approximate the node removal influence, and evaluate the approximation results

- NORA: Choose the desired dataset and model in "nora.sh"

- CF-GNNExplainer': Choose the desired dataset and model in "cf.sh"

- LARA-N: Choose the desired dataset and model in "lara_n.sh"

- LARA-E: Choose the desired dataset and model in "lara_e.sh"
