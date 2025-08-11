# Recommendation_system_wwt
This project builds a personalized recommendation system for Wings R Us, a US-based quick service restaurant. Using historical order and customer data, it generates tailored product suggestions to boost customer satisfaction, increase order size, and drive loyalty through the restaurant’s mobile app.

# Overview

This project builds a personalized recommendation system for Wings R Us, a quick service restaurant. The system analyses customer cart data to suggest the next best products, aiming to increase customer satisfaction, cart size, and loyalty.
Contents

•	WWT_JUPYTER_NOTEBOOK

Jupyter notebook containing the full data pipeline: data loading, cleaning, exploratory data analysis, feature engineering, model building, validation, and prediction generation.

•	requirements.txt

List of Python dependencies needed to run the notebook.
________________________________________
# How to Run
1.	Install Python 3.11 or newer.
2.	Install dependencies using:
pip install -r requirements.txt
3.	Open WWT_JUPYTER_NOTEBOOK in Jupyter Notebook or Jupyter Lab.
4.	Run all cells sequentially. The notebook is designed to run end-to-end without errors, producing the final submission file.
________________________________________
# How to Use the Codebase

•	The entire pipeline is implemented in a single Jupyter notebook file (Python 3.11 recommended).

•	Running the notebook from top to bottom will generate the final recommendations and outputs.

•	All dependencies are listed in requirements.txt. Use pip install -r requirements.txt to install.
________________________________________
# Description
1. Exploratory Data Analysis (EDA)
    •	Loaded historical order, customer, and store datasets.

    •	Cleaned data by removing non-food items and anomalous entries.

    •	Analyzed purchase behaviors segmented by store location, customer type (new, returning, high-value), order occasion (Delivery, ToGo), and time (weekday/weekend, seasonal spikes).

    •	Identified popular items and frequent combinations to understand buying patterns and customer preferences.
 
 
2. Feature Engineering & Extraction

     • Created multiple aggregated feature files capturing:

          o	Customer loyalty and value preferences (e.g., how often high-value customers purchase an item).
  
          o	Occasion-based item popularity (e.g., which items are preferred on Delivery vs ToGo).
  
          o	Returning customer behavior metrics.
  
          o	Seasonal spike influence on item demand.
  
          o	Store and time-based purchase trends (e.g., item popularity by hour and day).

    •	Merged these aggregated datasets into a comprehensive feature matrix (step2_all_features.csv) representing rich, multi-dimensional profiles for each product.
 
3. Model Building

    •	Computed item-item similarity scores using the engineered features to understand how closely related items are.

    • Generated association rules using market basket analysis (e.g., apriori algorithm) to find strong item co-purchase patterns.

    •	Developed a hybrid recommendation approach combining:
   
          o	Content-based signals (item similarity based on features).

          o	Collaborative signals (association rules and co-occurrence).

    •	The hybrid model takes a customer's current cart (items 1, 2, and 3) and predicts the top 3 most relevant next items (item 4 recommendations).

4. Validation & Final Output

    •	Created the final recommendation file including customer ID, order ID, existing cart items, and top 3 recommended items.

    • Ensured all recommendations were valid and consistent
________________________________________
# Dependencies

The code uses the following major Python libraries:

•	pandas — data handling and processing

•	numpy — numerical computations

•	scikit-learn — similarity computations and machine learning utilities

•	mlxtend — association rules mining

•	matplotlib & seaborn — data visualization

•	jupyter — interactive notebook environment
