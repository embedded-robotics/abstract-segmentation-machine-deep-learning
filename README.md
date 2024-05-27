# Abstract Segmentation using Deep Learning and Machine Learning

This repo deals with the training of machine learning and deep learning models for a sequence classification task to segment a research paper abstract (mostly medical related abstracts) into different classes namely `Background`, `Objective`, `Methods`, `Conclusions`, `Results`. The abstract is divided into multiple sentences and each sentence is then categorized into one of the highlighted classes.

## Details

Abstract segmentation is implemented using three machine/deep learning algorithms:

1. Logistic Regression Training (Word2Vec Features)
2. Gated Recurrent Unit Training
3. Large Language Model Fine-tuning [`T5`, `DistilBert`]

The code for the relevant approach is given in the corresponding directory `word2vec-logreg`, `gru` and `llm-finetuning`

## Implementation

1. Download the dataset from Kaggle (https://www.kaggle.com/code/matthewjansen/nlp-medical-abstract-segmentation) and put into `Dataset` directory
2. Run the `pre-processing.ipynb` to generate the `train.csv`, `test.csv` and `val.csv` from the raw text files present in the `Dataset` directory
3. Run the `gru/gru_custom.ipynb` to define and trin the custom GRU model. After training, the model checkpoint will be saved as `abstract_model.pth`. This checkpoint can be loaded to evaluate the model on the test data
4. (Optional) Run the `gru/gui_evaluation.ipynb` to load the pre-trained model using the saved checkpoint and launch the GUI which can be used to play around with the model to evaluate it in qualitive sense or just for the basis use case of reading abstracts in an amazing way
5. To run the code for `LLM Fine-tuning`, run different notebooks fine-tuned using different LLM within the `llm-finetuning` directory to fine-tune `DistilBert` and `T5` models via sequence classification head
6. To run the code for `Wordvec Logistic Regression`, run the notebook within the `wordvec-logreg` directory. This model uses `Word2Vec` features as the input and uses `Logistic Regression` for the multi-class classification task.

Once the model is trained, the user can input any abstract and the model will classify each sentence of the abstract into one of the classes namely `Background`, `Objective`, `Methods`, `Conclusions`, `Results`.