# MLOP
# IRIS MLOps Pipeline

This repository contains a simple MLOps pipeline for training and evaluating a Random Forest classifier on the IRIS dataset. Below is an overview of the included files and their utility:

## Files and Their Purpose

### `src/train.py`
- **Utility**: This script trains a Random Forest classifier on the IRIS dataset.
- **Details**:
  - Loads the IRIS dataset using `sklearn.datasets.load_iris()`.
  - Initializes and trains a `RandomForestClassifier`.
  - Saves the trained model to a file named `iris_model.joblib` using `joblib.dump()`.

### `tests/test_model.py`
- **Utility**: This file contains unit tests to validate the model's performance.
- **Details**:
  - Uses `pytest` to test the model's accuracy.
  - Asserts that the model's accuracy is at least 90% (`assert acc >= 0.9`).
  - Ensures the model meets the minimum performance threshold before deployment.

### `requirements.txt`
- **Utility**: Lists the Python dependencies required to run the pipeline.
- **Details**:
  - Includes `scikit-learn` for machine learning functionalities.
  - Includes `joblib` for model serialization.
  - Includes `pytest` for running unit tests.

### `.github/workflows/sanity-test.yml`
- **Utility**: Defines a GitHub Actions workflow for automated testing.
- **Details**:
  - Triggers on pull requests to the `main` branch.
  - Sets up a Python 3.10 environment.
  - Installs dependencies from `requirements.txt`.
  - Runs the unit tests using `pytest` and logs the results.
  - (Optional) Uses CML to post test results as a comment on the pull request.

## How to Use This Repository

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/iris-ml-pipeline.git
   cd iris-ml-pipeline
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Train the Model**:
   ```bash
   python src/train.py
   ```

4. **Evaluate the Model**:
   ```bash
   python src/evaluate.py
   ```

5. **Run Tests**:
   ```bash
   pytest tests/test_eval.py
   ```

6. **Create a Pull Request**:
   - Push changes to the `dev` branch and create a pull request to `main`.
   - GitHub Actions will automatically run the tests and report the results.

## Notes
- The repository is set up with a `dev` branch for development and a `main` branch for stable releases.
- The GitHub Actions workflow ensures that tests are run automatically on pull requests, maintaining code quality.

