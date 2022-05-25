# Sentiment_Analysis
### Final_Year_Project
A neural network made from the normal coding programming <br>
I am using NLP in this project using several formulas <br>


This notebook is divided into the below sections:

1. Data Cleaning and Preprocessing.

2. Exploratory Data Analysis (EDA) and Visualisation.

3. Feature Selection, Feature engineering and

4. Model building.

5. Checking Accuracy 

Looking closely at the values you just calculated, we see the following:

* Words that you would expect to see more often in positive reviews – like "amazing" – have a ratio greater than 1. The more skewed a word is toward postive, the farther from 1 its positive-to-negative ratio will be.<br>
* Words that you would expect to see more often in negative reviews – like "terrible" – have positive values that are less than 1. The more skewed a word is toward negative, the closer to zero its positive-to-negative ratio will be.<br>
Neutral words, which don't really convey any sentiment because you would expect to see them in all sorts of reviews – like "the" – have values very close to 1. A perfectly neutral word – one that was used in exactly the same number of positive reviews as negative reviews – would be almost exactly 1. The +1 we suggested you add to the denominator slightly biases words toward negative, but it won't matter because it will be a tiny bias and later we'll be ignoring words that are too close to neutral anyway.<br>
Ok, the ratios tell us which words are used more often in postive or negative reviews, but the specific values we've calculated are a bit difficult to work with. A very positive word like "amazing" has a value above 4, whereas a very negative word like "terrible" has a value around 0.18. Those values aren't easy to compare for a couple of reasons:<br>

* Right now, 1 is considered neutral, but the absolute value of the postive-to-negative ratios of very postive words is larger than the absolute value of the ratios for the very negative words. So there is no way to directly compare two numbers and see if one word conveys the same magnitude of positive sentiment as another word conveys negative sentiment. So we should center all the values around netural so the absolute value for neutral of the postive-to-negative ratio for a word would indicate how much sentiment (positive or negative) that word conveys.<br>
* When comparing absolute values it's easier to do that around zero than one. To fix these issues, we'll convert all of our ratios to new values using logarithms.
<br>
<br>
If everything worked, now you should see neutral words with values close to zero. In this case, "the" is near zero but slightly positive, so it was probably used in more positive reviews than negative reviews. But look at "amazing"'s ratio - it's above 1, showing it is clearly a word with positive sentiment. And "terrible" has a similar score, but in the opposite direction, so it's below -1. It's now clear that both of these words are associated with specific, opposing sentiments.
<br>
Now running the following cells to see more ratios.
The first cell displays all the words, ordered by how associated they are with postive reviews. (Your notebook will most likely truncate the output so you won't actually see all the words in the list.)
