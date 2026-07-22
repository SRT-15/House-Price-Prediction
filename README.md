🏠 House Price Prediction

Ever wonder how much a house should cost? This project tries to answer exactly that. Feed it some details about a house — how many bedrooms, how big it is, where it's located — and it'll spit out a predicted price.

What's going on here?

We're using real housing data (from King County, Washington) to train a machine learning model. Once trained, the model can look at a house it's never seen before and make a pretty reasonable guess at what it's worth.

Two different approaches are tested and compared:

Linear Regression — the simpler, more interpretable one. Think of it as drawing the best possible straight line through all the data points.
Random Forest — the more powerful one. It builds hundreds of mini decision trees and averages their answers, which tends to be a lot more accurate.
The data

The dataset used is kc_final.csv — King County house sales data. Each row is a house that was sold, and we look at 18 features to predict the price:

Feature	What it means
bedrooms	Number of bedrooms
bathrooms	Number of bathrooms
sqft_living	Size of the living space (sq ft)
sqft_lot	Size of the land plot (sq ft)
floors	Number of floors
waterfront	Is it on the water? (1 = yes, 0 = no)
view	Quality of the view (0–4)
condition	Overall condition of the house (1–5)
grade	Construction & design quality (1–13)
sqft_above	Square footage above ground
sqft_basement	Square footage of the basement
yr_built	Year the house was built
yr_renovated	Year it was last renovated (0 = never)
zipcode	ZIP code of the house
lat / long	GPS coordinates
sqft_living15	Average living space of the 15 nearest neighbors
sqft_lot15	Average lot size of the 15 nearest neighbors
How it works, step by step
Load the data — read in the CSV file
Split it up — 80% of the houses are used for training, 20% are held back for testing
Train the models — the models learn patterns from the training data
Measure accuracy — check how well the models perform on the houses they've never seen
Make a prediction — plug in details for a brand new house and get a price estimate
How accurate is it?

Three metrics are used to judge how good the predictions are:

MAE (Mean Absolute Error) — on average, how many dollars off is the prediction? Lower is better.
RMSE (Root Mean Squared Error) — similar to MAE, but punishes big mistakes more harshly. Lower is better.
R² Score — how much of the price variation does the model explain? Ranges from 0 to 1, and closer to 1 is better.

Random Forest generally wins on all three.

Example prediction

The notebook includes a sample house to predict on — a 3-bedroom, 2-bathroom place in Seattle (ZIP 98103), built in 1995, about 2,000 sq ft. Both models give a price estimate for it so you can see them side by side.

Requirements
pandas
scikit-learn

Install them with:

bash
pip install pandas scikit-learn

You'll also need the kc_final.csv dataset in the same folder as the notebook.

Running it

Open House_Price_Prediction.ipynb in Jupyter and run the cells top to bottom. That's it!
