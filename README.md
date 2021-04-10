# Dream Analysis


<img src="./img/dreams_tones.jpg" width="2000">

“The interpretation of dreams is the royal road to a knowledge of the unconscious activities of the mind.” ― Sigmund Freud, The Interpretation of Dreams (1900)

## Introduction
The main objective of this analysis is to provide data-driven insights into one of the many obscure activities of the brain, dream, and its interpretation. What kind of emotional responses can we expect from our dreams? Are dreams a tiny glimpse into our figment of imagination or perhaps asked differently, are dreams the manifestations of who we are and our daily experiences? Although the interpretation of any dream will only make sense in the context of the dreamer's life, I suspect individuals with shared backgrounds and experiences display relatively similar emotions from their dreams to those from different backgrounds. 

## Motivation
Dreams have always facinated me. In my dreams, I have played out many reality-based scenarios differently than they occurred, fullfiled the deepest desires, experienced incredible moments, felt shock and horror, and even done things that defy the law of physics.  And now, it led me to this data analysis where I take few common assumptions about dreams in order validate claims based on statistics. 


## Methodology

1. Web-scrapped a subset of the Sleep and Dream Database (SDDb), a digital archive and search engine developed by a psychologist and dream researcher Kelly Bulkeley, Ph.D. As of Apr 2021, the database  has a little over 34,000 dream entries from participants with varying backgrounds. 

2. Filtered the dataset by the association of the dreams to "Fire", "Air", "Water", and "Earth" key words, which yielded ~17% of the SDDb, each dream recorded with the appopriate associated survey series, date, and detials such as demographics or dream related measurements of the dreamer (e.g., recallation/insomina).

3. Apllied [TextBlob sentiment analysis ](https://textblob.readthedocs.io/en/dev/) to the dream entries. TextBlob is a python library that uses Natural Language Processing to analyze the sentiment of the textual information in terms of polarity and subjectivity. 

Polarity measures the degree of positive or negative attitude detected from the text. Result is in the range of `[-1.0, 1.0]`, where `-1.0` is the highest point for negative polarity and `1.0` for positive.

Subjectivity identifys the level of subjectivity/objectivity in the given text, given in the range of `[0.0, 1.0]`, as `1.0` indicating the most subjective text and `0.0` the least. 

4. Run the dream logs through[ IBM watson tone analyzer](https://www.ibm.com/watson/services/tone-analyzer/), a tool that can analyze the emotional and language tones in a text using linguistic analysis at a document and sentence level. Below is the definition of each tone provided by watson tone analyzer documentation. 

    <img src="./img/tone_definition.png" width="600">


## Exploritory Data Analysis (EDA)

The polarity metrics show that at a high-level, on average majority of the groups tend to have either a neutral dream or slightly leaning towards the positive specturm. The points that stand out (with large volume of data as exhibited with the size of the bubble) are:

- Gender: The female and male groups have relatively similar level of polarity
- Age: The two extreme opposite age groups show the highest variance from each other with the latter group leaning towards the positive side
- Race: Not enough data collected in race to make any inference with certainty 
- Education: An increase in the level of education does not show a strong relation to dream polarity
- Income: Those in the higher income bracket (> $100K) have the highest polarity in comparison to the lower income groups
- Politics: Although conservative seem to have a higher polarity attributed to their group, it is surprising to also find that the very conservative groups have an average polarity score similar to that of liberals
- Marital Status: Larger volume of data in this category comes from single and married participants, from which married groups have the higher average polarity score
- Religion: similar to race, majority of the participants lie in just one category, in this case, "other/none". However, the identified three religion followers roughly have the same polarity measurement. 

    <img src="./img/polarity_by_demo.jpg" width="2000">















