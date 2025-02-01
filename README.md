# Robot Action Prediction

This project is a deep learning-based solution that predicts the action a robot should take based on its surroundings and obstacles. The model uses an LSTM (Long Short-Term Memory) network to classify situations into one of three possible commands: **turn**, **stop**, or **return**.

## Features
- **Dynamic Dataset Generation**: Automatically generates a textual dataset describing situations based on distances, positions, and obstacles.
- **LSTM Model**: Trained on the dataset to classify commands with high accuracy.
- **Custom Rules**: Applies predefined rules for generating the dataset to simulate real-world robot decision-making scenarios.

## Project Structure
- `robot_text_commands.csv`: The dataset generated for training the model.
- `lstm_robot_model.h5`: Saved LSTM model file.
- `Action_Prediction.ipynb`: Notebook to train and predict the LSTM model.

## Dataset
The dataset is dynamically generated with the following logic:
1. If obstacles are detected on the left, the robot **turns to the right**.
2. If obstacles are detected on the right, the robot **turns to the left**.
3. If an obstacle is detected in front of the robot, it **stops**.

The dataset contains the following fields:
- `situation`: A textual description of the robot's surroundings.
- `command`: The action the robot should take (`tourner à gauche`, `stop`, or `tourner à droite`).

## Model
The LSTM model has:
- **Input Layer**: Encodes the textual input using tokenization and padding.
- **LSTM Layer**: Captures the temporal relationships in the textual data.
- **Dense Layers**: Outputs the probability distribution over the three commands.

## Training
The model is trained for 4 epochs using the Adam optimizer and a categorical cross-entropy loss function. Early stopping is used to prevent overfitting.

## Usage
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/ourahma/Robot_Action_Prediction.git
   cd Robot_Action_Prediction
   ```

2. **Install Dependencies**:
   Ensure you have Python 3 and the necessary libraries:
   ```bash
   pip install tensorflow pandas numpy
   ```

   Example input:
   ```
   "Il y a un obstacle à gauche"
   ```

   Output:
   ```
   Command: tourner à droite
   ```

## Files
- `Action_Prediction.ipynb`: Contains the code to train the LSTM model also provides a function to predict commands based on input situations.
- `robot_text_commands.csv`: The generated dataset.
- `lstm_robot_model.h5`: The saved trained model.

---

### Future Improvements
- Incorporate real sensor data for training instead of synthetic data.
- Extend the model to support additional commands or complex scenarios.
- Optimize the model for deployment on embedded systems.

---

## **Contact**
For questions or feedback, feel free to reach out at [marouaourahma@gmail.com].

