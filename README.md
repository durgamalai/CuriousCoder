# CuriousCoder
This project is about predicting a song's popularity by Training and testing machine learning models on music data from Spotify dataset.

Dataset:
We used a dataset that has approximately 232,000 tracks from 2019 that was collected from Spotify's API and published on Kaggle for public use. The dataset can be found in the following link:  

Spotify Tracks DB - https://www.kaggle.com/zaheenhamidani/ultimate-spotify-tracks-db

Since we ran classification models we had to feature engineer a column that required us to use additional data to determine whether a song was popular or not (see below Methods section for more information). The data used for this purpose was also gathered from Spotify's API and is available on Kaggle:  

Top 50 Songs - 2019: https://www.kaggle.com/leonardopena/top50spotify2019

Top 100 Songs - 2019: https://www.kaggle.com/reach2ashish/top-100-spotify-songs-2019

Preprocessing & Analysis:
We started with exploratory data analysis (EDA) to understand the the dataset.  During the EDA, we found that the "Children's Music" genre was duplicated due to different characters used in the dataset. After addressing this discrepancy by renaming this genre, we saw that approximately 56,000 tracks were duplicated. We grouped the data by their unique id numbers, and kept the maximum values of each column among the duplicated values (refer to the notebook for more information). Additionally, we checked to see if there were any missing values in the dataset and did not find any.

We then had to feature engineer our target column by using the popularity scores column. We binarize this column by establishing a cutoff popularity score. After looking at the range of popularity scores within Top 50 and Top 100 songs from the same year, we established the cutoff point to be greater than or equal to 58 out of 100.

After this, we proceeded with one hot encoding the categorical columns "key", "mode" and "time_signature". The dataset was then ready to be split into training and testing sets and used to train our models. We trained and tested using a Random Forest model, XGBoost model and a Logistic Regression model. 

Results:
Logistic Regression model had the best recall score of 0.66

Aside from the models, we additionally explored different attributes within the popular songs and the unpopular songs separately.
