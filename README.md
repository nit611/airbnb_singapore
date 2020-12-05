# AirBnB Singapore: a CRISP-DM analysis

### [Udacity's Data Scientist Nanodegree project!](https://www.udacity.com/course/data-scientist-nanodegree--nd025)

This project is a simple end-to-end data analysis of the AirBnB market in Singapore. Throughout the project, I follow the CRISP-DM methology: business & data understanding, data preparation & modelling, evaluation & deployment.
The data is obtained from [Inside AirBnB](sideairbnb.com/get-the-data.html).

### Table of Contents

- [Installations](#installations-and-libraries-used)
- [Project Overview](#project-overview)
- [Files](#files)
- [Methodologies](#methodologies)
- [Summary of Findings](#summary-of-findings)
- [Acknowledgements](#acknowledgements)
- [Licenses](#licenses)

### Installations and libraries used

- `pip install nltk` - [NLTK](http://www.nltk.org/)
- _[pandas](https://pandas.pydata.org/)_
- _[matplotlib](https://matplotlib.org/)_
- _[seaborn](https://seaborn.pydata.org/index.html)_
- _[Scikit-learn](https://scikit-learn.org/stable/)_
- _[numPy](https://numpy.org/)_

### Project Overview

The questions asked are from the perspective of a prospective host of AirBnB in Singapore, as well as a tourist visiting Singapore. The `.ipynb` notebook illustrates the business understanding of the project.

- How well can we predict price, and what are the factors affecting price of a listing the most?
- Do the prices have an 'obvious' relationship with neighbourhood?
- Which neighbourhood on average receives 'positive' sentiment in their listings' reviews?
- Are positive sentiment neighbourhoods pricier?
- How well can we predict a positive review with the given characteristics of listings, the host themselves, neighbourhood, etc. ?

### Files

`output_images` is a consolidated folder of the saved analyses images.
`listings.csv`, `reviews,csv` and `calendar.csv` are the three main datasets.

The project's flow is such that the data cleaning and preparation made for the first part of the analysis (using the `listings.csv` data), sets the data up to be merged with the calendar and reviews datasets for the last parts of the analysis.

### Methodologies

- Categorical variables are handles by one-hot encoding, and appended to the dataframe, to pass it to the linear regression analysis. Of course, they are handled based on the relevance to the question, and thus several categorical variables are dropped.
- Missing data imputation is done through three modes:
  Filling the values with the mean, mode and adding dummy_na columns, for the appropriate variables. For example, the `beds` variable is an integer, and had just 1.2% missing values. Imputation with the mode seemed appropriate. Had the variable been missing more, the imputation would be based still on the mode, but perhaps the mode of the corresponding `room_type`.

### Summary of Findings

- The Linear Regression model is able to predict the prices of listings with 15.5% accuracy
- The most influential factors affecting prices are: whether the listing is located in the Eastern region or not; whether the listing is an entire apartment; the number of people it can accommodate, etc. Prices are lower if an apartment is a shared apartment.
- The prices are likely to reduce if the host is located in the North/Northeastern regions.
- The prices are likely to be lower if the number of beds are more - but shared apartments also have lower prices and higher number of beds.
- The Central Water Catchment, Bukit Panjang and Choa Chu Kang are the neighborhoods with the most positive reviews. They are also located close to each other, near the Singapore zoo, and the Treep Top Walk, etc.
- Other _positive_ neighborhoods are the Southern and Easter region's neighborhoods.
- There is a weak non-linear relationship between the positivity of reviews in a neighborhood and the average price in the neighborhood.
- The linear regression model can predict the positivity of reviews for a listing with 36.5% accuracy.

### Acknowledgements

- [Chris I.](https://chris-writes-code.medium.com/), for helping with Singapore's map coordinates for plotting the scatter of frequency and prices.
- [Sachin Nitish](https://github.com/sachinnitish) for the unrelenting assist in programming and debugging.

### Licenses

All materials used are open source, and available on the internet.
