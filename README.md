# How to Run the Code

This repo deals with the training of a GRU model to develop an abstract segementation system. Once the model is trained, the user can input any abstract (mostly medical related abstracts) and the model will classify each sentence of the abstract into one of the classes namely `Background`, `Objective`, `Methods`, `Conclusions`, `Results`.

1. Run the `pre-processing.ipynb` to generate the `train.csv`, `test.csv` and `val.csv` from the raw text files present in the data directory named `Dataset`
2. Run the `gru_custom.ipynb` to define and trin the custom GRU model. After training, the model checkpoint will be saved as `abstract_model.pth`. This checkpoint can be loaded to evaluate the model on the test data
3. (Optional) Run the `gui_evaluation.ipynb` to load the pre-trained model using the saved checkpoint and launch the GUI which can be used to play around with the model to evaluate it in qualitive sense or just for the basis use case of reading abstracts in an amazing way