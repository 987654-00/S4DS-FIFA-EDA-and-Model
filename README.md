# S4DS-FIFA-EDA-and-Model
This is my first Github Repo as part of the tasks given to me by my ML heads as a part of DJ Sanghvi College of Engineering's Data Science Chapter S4DS

# Describing the data:
The data is a 7 files long FIFA player data consisting of player details from the year 2017 to 2023. Some of the important features include:
1. Name, ID
2. Different Skill Scores like Shooting, Marking, Stamina, Strength etc
3. The Players Net Worth and the club He belongs to
4. Overall Rating of the player along with his potential score
Above mentioned features are just a few, I will cover more as we progress.
Also want to mention the fact that there are also some not so important columns like 'Club Logo','Photo','ID','Flag' along with a column which is 93% NaN ie, 'Loaned From'.

# EDA Steps Breakdown 
Here is a detailed description of all the things that I did while Performing the EDA. (Skipping all the code snippets ive used to understand the data and get its overview)

1. All the Null values were taken care of by dropping features which has more than >90% Null Values ('Loaned From') and dropping the Rows which have about 2-7% null values ('Club','Contract Valid Until','Joined')
2. In columns like Wage and Value, the data is represented as object and is of the type €11M, €34K etc. So to deal with it I have created a function 'parse_values' which takes care of the same.
3. Then 'Weight' and 'Height' also has data of type Object which is of the format 160lbs, 180lbs and 6'0", 5'9" etc, That also has been taken care of and datatype has been changed to Int.
4. Starting with the Plotting:
   i. Finding the player with the most number of penalties
   <img width="986" height="548" alt="image" src="https://github.com/user-attachments/assets/f5a0ebb0-fd64-4e64-9738-673ad9842938" />

   ii. Finding the Top 10 Clubs according to Value of Players owned
   <img width="988" height="641" alt="image" src="https://github.com/user-attachments/assets/6ac89ee8-2852-4083-a66b-bdc080240e36" />

   iii. Most Valueable Players in the Year 2017
   <img width="981" height="547" alt="image" src="https://github.com/user-attachments/assets/c01e762a-17a9-4f62-a8c2-e007166a9807" />

   iv. Player V/S Country Graph telling us about the top 10 countries from most of the players belong
   <img width="1013" height="547" alt="image" src="https://github.com/user-attachments/assets/5fbc37eb-ab5a-4cae-9999-a24dd4aee9e6" />

   v. Finding Outliers in Age
   <img width="954" height="525" alt="image" src="https://github.com/user-attachments/assets/f7eadb10-fa4b-4294-9561-08edd80328ea" />

   vi. Finding Outliers in Value of Players
   
   <img width="520" height="432" alt="image" src="https://github.com/user-attachments/assets/2f0b43a4-3040-4dbb-a42f-e0c906f47736" />

   vii. Plotting a scatterplot to check the relation between Player Value and Player OVerall Rating
   <img width="567" height="448" alt="image" src="https://github.com/user-attachments/assets/dcee154b-a0cf-4faf-b0c5-6bdb67c989a4" />

   viii. First Finding the Overall Rating of the Player and also the listed player potential and then plots it against each other to check the Difference between            them to check the Scope Of Improvement for that particular player. Finally, displaying the top 10 players with the most scope of improvement.
   <img width="996" height="582" alt="image" src="https://github.com/user-attachments/assets/98397610-7837-4447-a7f7-11b3dfca4234" />

   ix. Finding Outliers in Wage
   
   <img width="544" height="432" alt="image" src="https://github.com/user-attachments/assets/df4b7047-d27a-4c62-89cf-12eb476a8fee" />

   x. Plotting a histogram to check the distribution of the Player wages
   <img width="1044" height="525" alt="image" src="https://github.com/user-attachments/assets/73cb7483-9e30-4e26-ab3d-1dbe6730063f" />

   xi. Plotting a histogram to check the distribution of the Player Value
   <img width="1023" height="525" alt="image" src="https://github.com/user-attachments/assets/4e373d77-7bd9-4186-8b8c-74c45b5a0c34" />

   xii. From all the features present, identifying the ones which has to do with a goalkeeper. Taking their mean and making a new Column called 'Goalkeepers' to            hold this new data. This basically tells us about the overall Goalkeeping skill Rating of a player which can be used later to find the best goalkeepers.
   <img width="996" height="525" alt="image" src="https://github.com/user-attachments/assets/896299e1-5ff3-4585-80e9-425dffc6b6e8" />

   xiii. Doing the above mentioned things for a defender and plotting the best Defender based on skills like ' SlidingTackle', 'StandingTackle', 'Marking',                  'Composure', 'Positioning', 'Interceptions', 'Strength'
   <img width="996" height="525" alt="image" src="https://github.com/user-attachments/assets/e019fc30-5ccd-4849-8bdc-0e1294f904a8" />

   xiv. Finding out all the Unique Positions in a Football match
   xv. Importing the datasets of the following years from 2018 till 2023.
6. Repeating the steps 1-2-3 on the newly imported datasets
7. Checking the Overall player rating of a player in year 2017 and 2018 and then calculating their difference to check for improvement or bad performance. Inner joining the 2017 data with 2018 based on player name and adding suffixes to help distinguish between the data columns.
8. Based on the 'Player Overall Rating Change in a year' obtained from step 6, finding the top 10 players who have had the most improvement and plotting it on a barplot.
   
   <img width="996" height="525" alt="image" src="https://github.com/user-attachments/assets/35e62e28-807f-48f8-b19e-2cd20f2ebc51" />

10. Comparing the preferred foot of a player against the overall rating of the player to check if one is better than the other ie, checking if right legged players have an advantage
   <img width="562" height="432" alt="image" src="https://github.com/user-attachments/assets/62b7ee46-8abe-4e40-80fc-146cad71ff26" />

11. Calling 'parse_values' to treat the new dataset columns
12. Extracting the 'Name' and 'Value' column from the years ie 2017,18,19,20 and 21 and merginng them into a single dataframe which records the name of the player and his value in the years. Additionally, found out the value change in the player which is basically difference in his value in the year 2017 and the year 2021 to check the level of improvement in the player based on his Value. Then for the players who have had the most significant value change in the 5 years, I plotted a line chart which basically shows individual player's value in each year to visualize the growth
    <img width="988" height="540" alt="image" src="https://github.com/user-attachments/assets/fe5ae678-e697-47a2-82bc-7a72af6def57" />

13. Finding the Correlation of the Numerical Columns in the dataset with the columns 'Best Overall Rating' and finding the top 10 positive and negative ones.

# Model Building Steps Breakdown 
 ## Model No. 1 
 Best Overall Rating Based on All Numerically Important Columns
 1. This is build on the FIFA data of the Year 2018. Standard steps like function 'parse_values' was applied, handled all the null data and then splitting the data     into X and Y
 2. The X contains all the numerically important column with high Positive and negative correlation with the taget column which was found while performing EDA.
 3. Splitting the data in train and test data and checking if they both have the same shape or not (I got an error here while building the model for the first time)
 4. Making Objects of LinearRegression and DecisionTreeCLassifier to build the models, train on the data and predicting on X_train
 5. Calculating the performance of the model using MAE (Mean Absolute Error) and the error comes out to be 0.5604418336764502 and 0.628276631344116 for                 LinearRegression and DecisionTree Classifier
 6. Performing the Same Model Training and Prediction wihout using the Column 'Jersey Number' because the rating of the player shouldnt really depend on the Jersey     Number but has a high positive correlation. Removing the column 'Overall' as it has 0.99 Correlation with the target column as it could be the same column          which was repeated in the dataset.
 7. Performing Step 5 again to calculate the model performance metrics and the scores came out to be 2.0076470027536666 and 1.111266034578918 for the linear            regression and decision tree model

## Model No. 2
This has to do with learning from all the features present in the column which has to do with the player skill ie columns 27 to 60 to predict the best position of the player. I have used Random Forest Classifier to achieve this and have reached an accuracy of 74%. 
