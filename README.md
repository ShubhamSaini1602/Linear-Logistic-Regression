# ML From Scratch in C++

Two small machine learning models written in plain C++ with no external libraries, to understand how training works step by step.

| Model | Task | Inputs |
| :--- | :--- | :--- |
| **Linear regression** | Predict exam marks | study hours, sleep hours |
| **Logistic regression** | Predict placed / not placed | DSA score, projects, IQ, attendance |

## What each program does

### Linear regression (`linear-regression/`)
* Loads a CSV dataset (`dataset.csv`).
* Learns weights `w1`, `w2` and bias `b` with gradient descent, updating after every example.
* Prints the weights every 100 epochs. (Data was generated from `marks = 5*study + 3*sleep + 4`, so the expected weights are 5, 3 and 4).
* `predict.cpp` takes study and sleep hours from the user and predicts marks using the trained weights.

### Logistic regression (`logistic-regression/`)
* Loads `students.csv`.
* Computes min-max normalization stats from the data (not hard-coded), normalizes each feature to 0-1.
* Trains with a sigmoid output and per-sample gradient descent (learning rate 0.1, 1000 epochs).
* Reports accuracy on the training data.
* `predict.cpp` uses the trained weights to print normalized inputs, the weighted sum, the probability, and the final result for each student.

## Concepts practiced
* CSV parsing with `ifstream` and `stringstream`
* Structs, vectors, and references in C++
* Min-max normalization
* Sigmoid function and prediction as a forward pass
* Gradient descent and weight updates

Each folder contains a sample CSV so the programs run as is.

### Limitations
* Models are evaluated on the same data they were trained on, so the accuracy shown is training accuracy, not a measure of generalization.
* The datasets are small [and synthetic]; this project is for learning, not production use.
* Planned next steps: train/test split, loss tracking, mini-batch gradient descent.
