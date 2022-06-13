# Problem Statement 3

The problem statement is given for this project.

# Data Collection 2

#### Was enough data gathered to generate a significant result? 2
- Yes, 9553 unique titles were used. You also appeared to pull much more data than you actually used because you sliced out the first 2000 posts of your scrapes and it was unclear why you were doing this. If you are making a large decision with your data such as ommiting over half of the rows from your scrapes you should explain and defend that decision so your reader can follow your logic.  
#### Was data collected that was useful and relevant to the project? 3
- Yes  
#### Was data collection and storage optimized through custom functions, pipelines, and/or automation? 1
- You appeared to have waited between scrapes and manually rerun your notebook each time. Consider automating this using the sleep function. Additionally you have a ton of try except statements in your scraper. Consider making a function for this or using a nested data structure to make your code much more readable and reduce the potential for errors.    
#### Was thought given to the server receiving the requests such as considering number of requests per second? 3
- Yes  

# Data Cleaning and EDA 0

#### Are missing values imputed/handled appropriately? 1
- You did briefly investigate null values and you dropped the rows that had any. Try to elaborate in markdown and defend your choice of null handling. Why did you feel this was the best course of action given what you know about the data?  
#### Are distributions examined and described? 0
- You did create some boxplots after you did your modeling but you did not examine any distributions in your EDA section. Your EDA should contain a thorough investigation into the characteristics of your dataset which includes making and interpreting visualizations such as boxplots and histograms.  
#### Are outliers identified and addressed? 0
- No  
#### Are appropriate summary statistics provided? 0
- You provided a few summary statistics in your data cleaning and EDA section but you did not interpret them. Make sure that you include more statistics in your EDA section and interpret them using markdown so that your reader knows how you are using them to inform yourself about your data.  
#### Are steps taken during data cleaning and EDA framed appropriately? 1
- You included some markdown to guide your reader through your data cleaning and EDA but often times this markdown was simply a short description of what you were doing rather than why. Include your thought process in your markdown so that your reader can follow your logic and understand exactly why you make the choices you do.  
#### Does the student address whether or not they are likely to be able to answer their problem statement with the provided data given what they've discovered during EDA? 0
- No  

# Preprocessing and Modeling 0

#### Is text data successfully converted to a matrix representation? 0
- You successfully converted your entire title column to a matrix representation but be careful here and make sure that you are only fitting your tfidf vectorizer on the training portion of your data after your split rather than the entire corpus.  
#### Are methods such as stop words, stemming, and lemmatization explored? 3
- Yes  
#### Does the student properly split and/or sample the data for validation/training purposes? 0
- Data was not split into training and testing data.  
#### Does the student test and evaluate a variety of models to identify a production algorithm (AT MINIMUM: two models)? 2
- You tested 6 models but you did not identify a production algorithm.  
#### Does the student defend their choice of production model relevant to the data at hand and the problem? 0
- You used accuracy score to guide you to exploring a random forest model as well as a logistic regression but you did not make a choice of production model and you did not defend that choice relative to the data at hand and the problem.  
#### Does the student explain how the model works and evaluate its performance successes/downfalls? 0
- Because you did not identify a production model you did not evaluate its performance successes/downfalls within the context of the data at hand and the problem statement.  

# Evaluation and Conceptual Understanding 2

#### Does the student accurately identify and explain the baseline score? 3
- Yes
#### Does the student select and use metrics relevant to the problem objective? 1
- You mostly used accuracy to evaluate your models and only looked at other metrics at the very end. Also you claim that your model only has 93 false positives but your confusion matrix suggests that you have 1212 false positives.  
#### Does the student interpret the results of their model for purposes of inference? 3
- You used your feature importances to guide further investigation into specific columns using split box plots which was great.  
#### Is domain knowledge demonstrated when interpreting results? 3
- Yes  
#### Does the student provide appropriate interpretation with regards to descriptive and inferential statistics? 1
- You interpreted statistics of certain columns after your modeling which was great but I would like to see more statistics and interpretations in your EDA section.  

# Conclusion and Recommendations

#### Does the student provide appropriate context to connect individual steps back to the overall project? 3
- Yes  
#### Is it clear how the final recommendations were reached? 3
- Yes  
#### Are the conclusions/recommendations clearly stated? 3
- Yes  
#### Does the conclusion answer the original problem statement? 3
- Yes  
#### Does the student address how findings of this research can be applied for the benefit of stakeholders? 3
- Yes  
#### Are future steps to move the project forward identified? 0
- No future steps to move the project forward are identified.  

# Project Organization 2

#### Are modules imported correctly (using appropriate aliases)? 3
- Yes  
#### Are data imported/saved using relative paths? 3
- Yes  
#### Does the README provide a good executive summary of the project? 2
- You do provide a good executive summary but you also include your conclusions and recommendations in it. While its appropriate to mention some key takeaways in your summary the full conclusions and recommendations are typically given their own section.  
#### Is markdown formatting used appropriately to structure notebooks? 0
- You used markdown well when interpreting the boxplots in your modeling notebook however your other 3 notebooks lacked descriptive markdown cells. Include more markdown especially in your EDA section to help guide your reader through the logic behind your descisions.  
#### Are there an appropriate amount of comments to support the code? 3
- Good job using comments to make your code more readable.  
#### Are files & directories organized correctly? 3
- Yes  
#### Are there unnecessary files included? 3
- No  
#### Do files and directories have well-structured, appropriate, consistent names? 3
- Yes  

# Visualizations 0

#### Are sufficient visualizations provided? 0
- You did provide some good boxplots in your modeling notebook which was great but your EDA section #### provides no visualizationsDo plots accurately demonstrate valid relationships? 1  
- The plots you did provide in the modeling section valid relationships between hot and not hot posts however you should demonstrate valid relationships in your EDA section.
#### Are plots labeled properly? 1  
- This is the same as above. The plots you have were good but you need to provide visualizations in your EDA section.
#### Are plots interpreted appropriately? 1  
- See above.
#### Are plots formatted and scaled appropriately for inclusion in a notebook-based technical report? 1
- Your boxplot is quite large and could be scaled down. Also consider editing the size or boldness of your titles and labels to help draw your readers eye.  

# Python Syntax and Control Flow 2

#### Is care taken to write human readable code? 3
- Good work making your variable names explicit.  
#### Is the code syntactically correct (no runtime errors)? 3
- No errors  
#### Does the code generate desired results (logically correct)? 3
- I could not find any instances where your code produced erroneous results.  
#### Does the code follows general best practices and style guidelines? 1
- - You mostly follow best practices and style guidlines but you have some lines that exceed the maximum recommended character length and get cut off when I render them on my screen. You also had some instances where the style guidlines around indentation in multiline function calls were not followed. Check out https://peps.python.org/pep-0008/ for a detailed python style guide and lets chat about installing notebook extensions to get you a handy red line that will help you here.  
#### Are Pandas functions used appropriately? 3
- Yes  
#### Are sklearn and NLTK methods used appropriately? 1
- For the most part you used sklearn methods appropriately however you fit NLTK methods on your entire dataset rather than fitting them only on a training dataset.
