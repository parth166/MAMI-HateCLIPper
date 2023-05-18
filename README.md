# SemEval2022-Task 5: Multimedia Automatic Misogyny Identification (MAMI)
This is the Github repository for SemEval-2022 Task 5, Multimedia Automatic Misogyny Identification (MAMI). This repositopry contains:

1. Baselines
2. MamiClip
4. VisualBERT

Dataset, baselines and evaluation scripts are replicated as described by the authors of the paper "**_SemEval-2022 Task 5: Multimedia Automatic Misogyny Identification_" https://aclanthology.org/2022.semeval-1.74/** 

## BASELINE

### Dataset 
The data may be distributed upon request and for academic purposes only. To request the datasets, please fill out the following form: https://forms.gle/AGWMiGicBHiQx4q98

The datasets (10000 + 1000 memes about misogyny detection). There are 10,000 training examples and 1000 test examples.

## Evaluation Script and Baselines
The evalulation scripts that has been used to rank the teams participating in the MAMI challenge, estimating macro-average F1-Measure for Subtask A and weighted-average F1-Measure for Subtask B. The evaluation script is available in the [Evaluation Folder](https://github.com/MIND-Lab/MAMI/tree/main/Evaluation).

The baseline models used for the MAMI challenge can be found in [Baseline Folder](https://github.com/MIND-Lab/MAMI/tree/main/Baselines).

This repository has the baseline implementation replicated using the models provided in then above link. 

For Subtask A, the baselines are grounded on:
1. Text-Only baseline has been derived and experimented using the USE sentence embedding. 
2. Image only has been done using fine tuned VGG-16 model.
3. A concatenation of deep image and text representations, i.e. based a single layer neural network.

For Subtask B, the baselines are grounded on:
1. a multi-label model, based on the concatenation of deep image and text representations, for predicting if a meme is misogynous and the corresponding type;
2. a hierarchical multi-label model, based on text representations, for predicting if a meme is misogynous or not and, if misogynous, the corresponding type.

The codefiles for the given baselines are taken using the github repo provided and the directory structures and computation of ground truth labels has been done by us.

Our own work: 
1. Implementation of BERT model as an experimental baseline for text only model. BERTBaseline.ipynb
2. Quantitative error analysis - errorAnalysis.ipynb

Additionally, experiment using BERT model in the file BERTBaseline.ipynb have been done by us which led us to experiment with visual BERT.  Error analysis folder contains errorAnalysis.ipynb file which gives a quantitative analysis of the models with the dataset biases and the scripts have been used to get the required analysis results.

To run the baselines and compute the performance measure for each subtask, go into the directory where the structure has been set. Download the dataset and upload TRAINING and TEST folder in the baseline directory. Run the script and get the baselines.

## Visual BERT: 

VisualBERTEmbeddings.ipynb: Embeddings get generated for the model
VisualBERT_exp.ipynb: Training of model

Code has been replicated from: https://github.com/mohamadhabash/VisualBERT-for-Memes-Classification

## CLIP

CLIP and HateCLIP: The base code has been taken from - https://github.com/TIBHannover/multimodal-misogyny-detection-mami-2022.
CLIP : The file "mami_clip.ipynb"  contains the code for model and has been tweaked for our experiments.

Hate-CLIPper:  The "hateclipper.ipynb" contains the code for HateCLIPper model and has been finetuned for the downstream classification task. This is an extension of the the CLIP model defined in "mami_clip.ipynb". 

Deep-Hate-CLIPper: The file "DeepHateCLIPper.ipynb" is a model architecture tweak building on the above Hate-CLIPper model by adding additional layers. This model is a piece of our own work and has not been referenced from any other public repository. 

Both Hate-CLIPper and Deep-Hate-CLIPper models have never been executed on MAMI SemEval Database before and this is the first execution of these models over this dataset to the best of my knowledge. 

## Contacts
If you have any question, please contact us at pvashisht@umass.edu
