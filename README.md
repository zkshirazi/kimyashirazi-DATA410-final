# Forbes World's Billionaires List 2022
### By Kimya Shirazi 

Link to the dataset:
https://www.kaggle.com/datasets/prasertk/forbes-worlds-billionaires-list-2022?resource=download

## Introduction

While the COVID-19 Pandemic caused soaring unemployment, many corporations reached record profits, and in turn—accelerated the wealth of select billionaires worldwide. The pandemic, coupled with war and sluggish markets, influenced the economy and redefined the capacity of billionaires from 2020 onward. According to Forbes’ 36th-annual ranking of the planet’s richest people, there are 2,668 billionaires in 2022, which is 87 fewer than a year ago. Collectively, the billionaires on Forbes’ list are worth a combined $12.7 trillion—$400 billion less than in 2021. Global politics play a key role in this trend, as the most dramatic drops occurred in Russia, where there are 34 fewer billionaires than last year following Vladimir Putin’s invasion of Ukraine. Additionally, in China, where a government crackdown on tech companies has led to 87 fewer Chinese billionaires on the list. 

However, in America, billionaire CEOs such as Jeff Bezos of Amazon and Elon Musk of Tesla/SpaceX experienced dramatic increases in wealth—both personally & in the valuation of their respective companies. Elon Musk specifically topped the World’s Billionaires list for the first time. Moreover, Forbes found more than 1,000 billionaires who are richer than they were a year ago. And 236 newcomers have become billionaires over the past year—including the first ever from Barbados, Bulgaria, Estonia and Uruguay. America maintains a global lead, with 735 billionaires worth a collective $4.7 trillion. China (including Macau and Hong Kong) remains number two, with 607 billionaires worth a collective $2.3 trillion. 

The combination of the Pandemic & global politics creates a particularly unique context for Forbes’ 2022 list of billionaires. This is significant because, by utilizing data analytics & machine learning methodologies, there is an opportunity to investigate the greater impacts of current events on wealth and the future of the global economy. Specifically, in reference to the competition between global powers via a country’s collective private wealth. 

## Description of Data

The Forbes World’s Billionaires list is a snapshot of wealth using stock prices and exchange rates from March 11, 2022. Moreover, Forbes’ also publishes a real-time net worth list, updated daily, of all 2,668 billionaires. However, for the purpose of this study, I will be employing the March 2022 dataset sourced from Kaggle. 

The data is organized in a CSV file with 2,668 rows (one for each billionaire) and 22 columns. The 22 columns include data on the following:

1. Rank
2. Billionaire’s name 
3. Age
4. Net worth (in millions USD)
5. Year of ranking (2022 for all rows)
6. Month of ranking (4 for all rows, meaning April)
7. Category/industry
8. Primary source of wealth 
9. Country of residence
10. State (if applicable)
11. City 
12. Country of citizenship
13. Organization/company
14. Self-made (true or false)
15. Gender
16. Birthdate 
17. Title (CEO, entrepreneur, etc.)
18. Philanthropy score 
19. Residence
20. Number of siblings
21. Bio (short description)
22. Extended biography 

The Forbes’ list includes individuals rather than multigenerational families who share fortunes, though the dataset includes wealth belonging to a billionaire’s spouse and children if that person is the founder of the fortune. In some cases, Forbes’ lists siblings or couples together if the ownership breakdown among them isn’t clear, but here an estimated net worth of $1 billion per person is needed to meet that threshold. Moreover, the calculation includes a variety of assets, including private companies, real estate, art and more. While Forbes does not have access to each billionaire’s private balance sheet (though some provide it), they simply discount fortunes in the cases where documentation is not supplied or available. 

## Description of the Methods

Based on the nature of the dataset, I will be employing algorithms that center around classification. Given a set of observations and labels to train on, classification entails categorizing the data points using the provided information. Classification algorithms involve a labeled dataset, thus classification is defined as a form of supervised learning. The two primary types of classification algorithms are lazy learners and eager learners. Lazy learners store the training data in memory and classify the testing data point based on related stored train data. While training requires less time with a lazy learner, the prediction can be slower. In contrast, an eager learner trains on the data in order to cover all possible scenarios, therefore establishing predictions afterwards. Hence, training requires ample time with this method, but the prediction rate is faster. There is no “best” classification algorithm, but it is key to tailor it to the dataset based on the unique qualities of the data to optimize performance. Consequently, for the purpose of this study, I will experiment with a variety of classification algorithms.  

### Preprocessing Steps

Before the technical preprocessing steps take place, it is critical to consider the goal of the research and to evaluate which columns might be useful for said goal/analysis. Of the 22 columns, the relevant pieces of data for the purpose of "investigative journalism" are ranking, net worth, country of residence, title, industry, and organization/company. As I progress throughout the research, however, I will experiement with different variables and further investigate how they might assist an analysis of global wealth post-select global political events (i.e. the Pandemic, Russian & Ukrainian War, Chinese-U.S. relations, etc.). 

The chosen dataset contains numerical and textual data. However, the majority of the relevant data is textual, with net worth and ranking being the only two significant numerical pieces of data. As a result, there is a substantial amount of preprocessing which is necessary in order to draw meaningful information from the textual data. There are several libraries in Python that assist with textual preprocessing—specifically NLTK, Gensim, and spaCy. Regardless of the chosen library, there are several standard steps which apply, and help transform the text data into being fit for a machine learning model. At this stage, some experimentation can be done with lemmatization and stemming. Next, it is key to remove url links, punctuation, and excess white space in the descriptions. Then, to standardize the data, all of the letters must be lowercase. 

Finally, it is of significant importance to gather a list of common English stopwords (commonly used words that do not contribute to overall meaning), and remove them from the text data to eliminate them from influencing classification as well as lower the number of words per observation. After the string data is significantly cleaner, we can tokenize the text (split it into individual words in a list). This is essential in order to transform our text data into a matrix or vector form. The two options for doing this are using the CountVectorizer function or by creating a TF-IDF (Term Frequency Inverse Document Frequency) matrix. These approaches utilize the frequency count of the words in the post as the metric for future modeling input. A functional programming approach is ideal for setting up these processing steps in order to best streamline cleaning training data and future data that might be plugged into the model.

### Machine Learning Methodology 
This section will be filled in for the final project using the score results and comparing the different methodologies to understand why some may outperform others.

## Pipeline
![Untitled drawing](https://user-images.githubusercontent.com/76021844/163297864-ca3c80a7-e2f2-45a4-ae8e-458b9ea62016.png)


## Concluding Thoughts and Future Work 
Cross-validation would be a useful exercise to ensure there is no one specific model that outperforms the others. This area was a computational efficiency problem when I was conducting my analysis, but cross-validation is a very important way to understand the results of a particular model if a longer timeframe were available.

## References 

https://www.forbes.com/billionaires/
