# Response of Tomato to Salinity and Heat Stress

## Project topic

This project studies the effect of salinity and heat stress on tomato plants. The dataset is from the Gene Expression Omnibus:

https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE245759

This is a bulk RNA seq dataset, which was tested on 24 different samples. It has the expression of 34,000 genes in the 24 samples. The salinity treatment exposed the plants to 150 mM salt, and the heat treatment exposed plants to 37°C temperatures. They had a control group, a salinity group, a heat group, and a salinity + heat group. This dataset also includes samples who were treated with a bacteria, Pseudomonas putida, but for simplicity I will exclude those samples. That leaves 12 of the original 24 samples. 

What I'd like to do is use PCA and hierarchical clustering to see what are the main differences between the treatments, and if salinity or temperature have a stronger effect on gene expression among the tomatoes. I should be able to visually see if salinity has a stronger effect, heat has a stronger effect, or if they both have strong effects. I am interested in this, because I have performed RNAseq experiments in the past on mice where one treatment has a much more powerful effect on the samples than another treatment, to the point you cannot see the effect of the other treatment at all on my PCA plot. 

I believe the dataset is associated with this paper: 

https://academic.oup.com/plphys/article/199/3/kiaf519/8286221

But the paper mentions a different salinity level than the dataset does, so I'm not completely sure. I will use it as a reference to help confirm I trust my results

## Data cleaning and EDA


Does it include clear explanations on how and why a cleaning is performed? Depending on your data, some examples of EDA might include:

Tabulated data cleaning examples: Inspect null values and drop or impute.

User/product ratings data examples: Basic EDAs on user count, product count, and basic data cleaning/processing (e.g. proper data types and treating null values)

Text data examples: Basic EDA such as word count, histogram etc and basic data cleaning such as stop words removal, Explaining word embedding methods: When you evaluate, the score is based on how they demonstrated understanding by explaining the concepts and giving reasonings why they chose the methods/techniques etc, but not based on just complexity of the model or technique or just performance alone.

Image or sound data examples: Pixel value count or histogram, spectral analysis such as power spectrum or frequency analysis to make feature vectors, etc

Does it include clear explanations on how and why an certain analysis (EDA) is performed?

Does it have proper visualization?

Does it have proper analysis? E.g. histogram, correlation matrix, heatmap, plots etc.

Does it have conclusions or discussions? E.g. the EDA summary, findings, discussing foreseen difficulties and/or analysis strategy.

Model building / Model choice (15 pts)
How many models have been used and compared? Any reasonings for model choice?

Model training (15 pts)
Show model training procedure including hyper parameter tuning. Show any procedure for measuring train and/or test performances.

Results and Analysis: (20 pts)

Does it have a summary of results and analysis?
Does it have a proper visualization? (e.g. tables, graphs/plots, heat maps, statistics summary with interpretation etc)
Does it use different kinds of evaluation metric properly? Also does it explain why they chose the metric?
Does it iterate the training and evaluation process and improve the performance? Does it address selecting features through the iteration process?
Did the author compare the results from the multiple models and did appropriate comparison?
Discussion and Conclusion: (10 pts) Add your discussion on the results, ways to improve the results