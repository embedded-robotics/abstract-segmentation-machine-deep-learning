# Abstract Segmentation using Deep Learning and Machine Learning

This repo deals with the training of a GRU model to develop an abstract segementation system. Once the model is trained, the user can input any abstract (mostly medical related abstracts) and the model will classify each sentence of the abstract into one of the classes namely `Background`, `Objective`, `Methods`, `Conclusions`, `Results`.

The same multi-class classification problem is being solved using three appraoches namely `GRU`, `LLM Fine-Tuning` and `Wordvec Logistic Regression`. The code for the relevant approach is given in the corresponding directory:

1. Run the `pre-processing.ipynb` to generate the `train.csv`, `test.csv` and `val.csv` from the raw text files present in the data directory named `Dataset`
2. Run the `gru/gru_custom.ipynb` to define and trin the custom GRU model. After training, the model checkpoint will be saved as `abstract_model.pth`. This checkpoint can be loaded to evaluate the model on the test data
3. (Optional) Run the `gru/gui_evaluation.ipynb` to load the pre-trained model using the saved checkpoint and launch the GUI which can be used to play around with the model to evaluate it in qualitive sense or just for the basis use case of reading abstracts in an amazing way
4. To run the code for `LLM Fine-tuning`, run different notebooks fine-tuned using different LLM within the `llm-finetuning` directory
5. To run the code for `Wordvec Logistic Regression`, run the notebook within the `wordvec-logreg` directory