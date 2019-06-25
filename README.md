This is an assignment from the Data Analyst Nanodegree from Udacity. The dataset that is wrangled is	the tweet archive of Twitter user @dog_rates, also known as WeRateDogs.	WeRateDogs is a	Twitter	account	that rates people's dogs with a humorous	comment	about the dog. These ratings almost always have	a denominator of10.

### Gathering the data

Data was gathered from 3 sources:
- Enhanced Twitter Archive, which contains basic tweet data for all 5000+ of their
tweets. 
- Additional Data via the Twitter API, which contains retweet count and number of times a tweet was favorited. This data was first saved into a tweet_json.txt file. 
- Image Predictions File, which is a table full of image predictions alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

### Assessing the data

This step allows us to identify quality and tidiness issues. 
Low-quality data are considered as dirty data and have content issues. We have to assess at
least height quality issues. As for untidy data, they are considered as messy data and are
structural issues. We’ll identify at least two of them.
There are two types of assessment:
- Visual assessment, which consists in scrolling through the data in Google Sheets or Excel to name a few - I first took a look at the cvs file in Google Spreadsheet.
- Programmatic assessment, for which we use code such as pandas' head, tail, describe, shape, sample, value_counts and info methods.

Here’s a list of the issues that have been highlighted:

Tidiness Issues
<ul>
    <li>predictions and df_tweets DataFrames should be merged with df</li>
    <li>Certain columns will need to be deleted because they are not useful to our analysis</li>
</ul>

Quality Issues
<ul>
    <li>There are some tweets that do not have images</li>
    <li>There are retweets that we do not wish to keep in our DataFrame</li>
    <li>Some rows have a denominator that isn't 10. This happens when there is another fraction in the text.</li>
    <li>Some rows have numerators that are exessively big, which is probably an error</li>
    <li>Some rows have dog name errors: all the lower case dog names</li>
    <li>tweet_id, timestamp, and source columns need to be converted to the right datatype</li>
    <li>Source column is an entire 'a href' link instead of simply the device/medium such as 'Twitter for iPhone', 'Twitter Web Client', 'Vine'</li>
    <li>Some breeds in p1 have their 1st letter as upper case</li>
    
</ul>

### Cleaning the data

This part of the data wrangling was divided in three parts: Define, code and test the code. These three steps were on each of the issues described in the assess section. First and very helpful step was to create a copy of the three original dataframes. I wrote the codes to manipulate the copies. If there was an error, I could create a new copy from the original. Whenever I made a mistake, I could create another copy of the dataframes and continue working on the cleaning part.


### Conclusion 
Through the data wrangling and analysis, we used many libraries such as pandas, NumPy,
requests, tweepy, and json, which allow us to gather, assess, and clean the data.
Finally, we put the following documents together:

- wrangle_act.ipynb: code for gathering, assessing, cleaning, analyzing, and visualizing
data
- wrangle_report.pdf: documentation for data wrangling steps: gather, assess, and
clean
- act_report.pdf: documentation of analysis and insights into final data
- twitter_archive_enhanced.csv: file as given
- image_predictions.tsv: file downloaded programmatically
- tweet_json.txt: file constructed via API
- twitter_archive_master.csv: combined and cleaned data
