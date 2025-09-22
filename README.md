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
2. In columns like Wage and Value, the data is represented as object and is of the type €11M, €34K etc. So to deal with it I have created a function which takes care of the same.
3. Then 'Weight' and 'Height' also has data of type Object which is of the format 160lbs, 180lbs and 6'0", 5'9" etc, That also has been taken care of and datatype has been changed to Int.
4.   
