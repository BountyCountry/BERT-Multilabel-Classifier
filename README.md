# BERT-Multilabel-Classifier

This repo was produced by the K3 Partners data science team. 

Before getting started you will want to go and download your choice of BERT base model from https://github.com/google-research/bert or from the BountyCountry git repo
For this notebook we use Bert-Base, Cased If you can fit Bert-Large into GPU memory then I congratulate you as you are a very wealthy person. The zip file of the model will have six files in it and your model will need them all in the same directory as this notebook.

### Adapting this notebook to train the model on new data
This notebook trains the model on a demonstration dataset of toxic online comments. To train different data you will need to put your training data in a similar format (a data frame with an id column, a text column and then some number of label columns populated with zero or one). At the moment the code assumes 5 label columns, you will need to make adjustments to handle any other number of label columns.

### Making Predictions
Once you have trained this model it will produce a checkpoint under "working/output/". You can then simply take this file and use the notebook "multi-label-class-from-checkpoint" to make predictions on much lower spec hardware.

### Important Note
This model only accepts sequences of 128 BERT tokens at a time (around 75 words). To classify a long document you will want to split it into subdocuments and reconstruct them, performing your own logic as to how to average/sum the total predictions for the given classes.

Both notebook files expect to run in a directory that includes the following folder structure "working/output/eval".

You will need to run the first notebook to produce the checkpoint files necessary successfully run the 'from checkpoint' notebook. These checkpoint files are for your newly trained model and are in addition to the BERT checkpoint files
