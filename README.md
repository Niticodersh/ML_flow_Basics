# ML_Flow_Basics

This project demonstrates how to use **MLflow** to track machine learning model experiments. We will log parameters, metrics, and models using the `mlflow` library and learn how to set up both local and remote tracking of experiments.

## Overview

### What is MLflow?

MLflow is an open-source platform that helps manage the entire machine learning lifecycle. It provides tools for tracking experiments, packaging code into reproducible runs, and sharing and deploying models.

In this project, we focus on:

- Tracking model experiments using **mlflow.sklearn**.
- Logging parameters, metrics, and models.
- Running MLflow’s user interface to visualize experiments.
- Setting up remote tracking using DagsHub for sharing experiments.

## How It Works

### 1. **MLflow Tracking**

MLflow tracks the following:

- **Parameters**: Input variables like hyperparameters of a model.
- **Metrics**: Evaluation metrics such as Mean Squared Error (MSE), R-squared, etc.
- **Models**: The actual machine learning models that are created and trained.

When you run the experiment, MLflow creates an `mlruns` folder in the directory, which contains all the information regarding the runs. You can visualize these experiments using the MLflow UI.

### 2. **MLflow UI**

To launch the MLflow UI, run the following command in your terminal:

```bash
mlflow ui
```
This will open the MLflow dashboard in your browser at [http://localhost:5000](http://localhost:5000) by default. You can track experiments and view all the logged parameters, metrics, and models in a user-friendly graphical interface.

### 3. Remote Tracking Using DagsHub

To share your experiments with others or collaborate, you can use remote tracking with **DagsHub**. DagsHub is a platform that provides an easy way to track your experiments remotely and integrate them with your GitHub repository.

#### Steps to set up remote tracking:

1. Push your code to a GitHub repository.
2. Create a DagsHub repository and connect it to your GitHub repository.
3. Set the remote tracking URI in your code using the URI provided by DagsHub:

    ```python
    mlflow.set_registry_uri('remote_server_uri_from_dagshub')
    ```

4. Now, when you run your experiments, all the models and tracking data will be saved on the DagsHub server. You can share this with anyone by giving them access to your DagsHub repository.

### Prerequisites

- Python 3.x
- `mlflow` library
- `scikit-learn` library
- DagsHub account (for remote tracking)

### Install Dependencies

You can install the required libraries using the following command:

```bash
pip install -r requirements.txt
```

### Running the Project

1. Clone the repository and navigate to the project directory.

2. Run your training script:

    ```bash
    python your_script_name.py
    ```

3. Use the MLflow UI to visualize your results:

    ```bash
    mlflow ui
    ```

4. (Optional) For remote tracking, configure your DagsHub URI and run your experiments:

    ```python
    mlflow.set_registry_uri('your_dagshub_remote_uri')
    ```

### License

This project is licensed under the MIT License - see the LICENSE file for details.

