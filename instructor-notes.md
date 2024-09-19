# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) The Diagram: Instructor Notes

Using a digital drawing device (such as Excalidraw, Google Jamboard, or Microsoft Onenote), draw out a diagram similar to the one found [here](./assets/prev-diagram.png).

The idea is that, for Project 2, students receive files with names that may be counter to their understanding of what a train-test split is. The major topics to hit are:

**Training Phase:**
1. During the training phase, do not use `test.csv` (it doesn't have a target and so is useless for training)
1. Split cleaned `train.csv` into `X`, `y`
1. Train-test split `X` and `y`
1. Using Scikit-learn transformers, preprocess your data, training the preprocessors on `X_train` and then passing `X_test` through your preprocessing step.
1. Then fit the model as usual, evaluating on both `X_train` and `X_test`
1. Once a model is determined, we can move on to the serving phase.

**Serving Phase:**
1. Use the same preprocessing steps on `train.csv` and `test.csv`
1. Read in `test.csv` as `X_serv`, since it won't have a target and is the real-time predictions we will serve to the client
1. Preprocess these data using the same architecture from the training phase, but this time using the whole `X` (from `train.csv`) for fitting. Pass `X_serv` through this.
1. Similarly, us the same model architecture you agreed on in the training phase, train on the full `X`. Make predictions on `X_serv`.
1. These predictions are your Kaggle submission!
