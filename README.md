# Temperature Cooling Analysis

This repository contains a project that analyzes the cooling of an object over time using Newton's Law of Cooling. It uses experimental data to fit a model and predict temperature changes.

## Files

*   `Computation.ipynb`: A Jupyter Notebook with a detailed analysis comparing different cooling constants (k). It includes goodness of fit measures (R-squared, RMSE) and residual analysis.
*   `Notebook.ipynb`: The core Jupyter Notebook for this project. It performs the main analysis, including model fitting and extrapolation.
*   `Notebook_k_updated.ipynb`: A Jupyter Notebook focused on finding the optimal cooling constant (k) and refitting the model with new data.
*   `dataset.csv`: The dataset containing the time, ambient temperature, and object temperature readings.
*   `sources/`: A directory containing reference materials and related papers.

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Create a virtual environment:**
    ```bash
    python -m venv .venv
    source .venv/bin/activate
    ```

3.  **Install the required libraries:**
    The notebooks use the following Python libraries: `numpy`, `pandas`, `scipy`, and `matplotlib`. You can install them using pip:
    ```bash
    pip install numpy pandas scipy matplotlib
    ```

## Usage

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

2.  **Open one of the notebooks:**
    *   `Notebook.ipynb` for the main analysis.
    *   `Computation.ipynb` for a more detailed comparison of models.
    *   `Notebook_k_updated.ipynb` for an analysis focused on the cooling constant `k`.

    You can run the cells in the notebook to see the analysis, data visualization, and model fitting results.

## Summary of Findings

The analysis in the notebooks reveals several key findings about the cooling process:

*   **Model Suitability**: Newton's Law of Cooling serves as an effective model for the temperature data, providing a close fit to the observed measurements, especially in the initial hours.

*   **Optimal Cooling Constant**:
    *   Using the initial dataset, the optimal cooling constant `k` is determined to be approximately **0.123**. This value yields a model with a high R-squared value (0.9953) and low RMSE (0.4053 °C), indicating a strong goodness of fit.
    *   The corresponding thermal time constant (`tau`) is approximately **8.14 hours**.

*   **Out-of-Sample Validation**:
    *   An out-of-sample test was conducted with a new measurement at the 13-hour mark (50.4 °C).
    *   The initial model (k=0.123) predicted a temperature of 42.8 °C, a significant deviation from the actual observation. This highlights the limitations of the initial model for long-term extrapolation.

*   **Model Refinement**:
    *   When the model is refitted to include the 13-hour data point, the optimal cooling constant `k` is updated to approximately **0.110**.
    *   This refined model provides a more accurate long-term prediction, suggesting that the cooling characteristics of the object may change over time or temperature ranges.
