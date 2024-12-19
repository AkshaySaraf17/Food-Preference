Food Preference Recommender

This project implements a food preference recommender system using the Alternating Least Squares (ALS) algorithm for collaborative filtering. The system predicts user preferences for unrated items based on a user-item matrix of food preferences and recommends top items for individual users.

Features
- Collaborative Filtering: Implements the ALS algorithm to factorize the user-item matrix.
- Matrix Masking: Splits the dataset into training and testing by masking a percentage of known ratings.
- Performance Evaluation: Calculates Root Mean Square Error (RMSE) to evaluate model accuracy.
- Top-N Recommendations: Generates personalized food recommendations for users.

Requirements
- Python 3.8+
- Required Python Libraries:
  - pandas
  - numpy
  - scikit-learn
  - openpyxl

Install the required packages:
```bash
pip install pandas numpy scikit-learn openpyxl
```

Dataset
The input dataset is an Excel file containing user preferences for various food items. Columns represent food items, and rows represent users. Ratings are integers, with `NaN` for unrated items.

How to Run
1. Prepare the Dataset: Place the Excel file containing user preferences at the specified path in the script.
2. Run the Script: Execute the notebook or script to:
   - Train the model using ALS.
   - Mask a portion of the ratings to create a test set.
   - Predict missing ratings and evaluate RMSE.
3. Make Recommendations: Input a user's name from the displayed list to receive top-2 recommended items.

Key Files
- `Food Preference Recommender.ipynb`: Jupyter Notebook containing the implementation.
- `food_preference.xlsx`: Dataset file.

Workflow
1. Data Preprocessing:
   - Load the Excel file and convert it into a user-item matrix.
   - Replace missing values (`NaN`) with zeros for matrix factorization.

2. Model Training:
   - Initialize user and item latent factor matrices.
   - Optimize the ALS algorithm iteratively to minimize the error between actual and predicted ratings.

3. Evaluation:
   - Mask 20% of the known ratings for testing.
   - Calculate RMSE between actual and predicted ratings.

4. Recommendation Generation:
   - Identify unrated items for a selected user.
   - Recommend the top-2 items with the highest predicted ratings.

Customization
- Number of Factors: Adjust the `num_factors` parameter to control the dimensionality of latent features.
- Regularization: Modify `lambda_reg` for better generalization.
- Iterations: Change `num_iterations` to improve convergence.

Limitations
- Assumes that missing values represent unrated items.
- Recommendations are purely collaborative and do not account for content-based filtering.

License
This project is licensed under the MIT License. See the LICENSE file for details.


