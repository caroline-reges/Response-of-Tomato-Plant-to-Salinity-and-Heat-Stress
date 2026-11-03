# Response of Tomato to Salinity and Heat Stress

## Project topic

This project studies the effect of salinity and heat stress on tomato plants. The dataset is from the Gene Expression Omnibus:

https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE245759

This is a bulk RNA seq dataset, which was tested on 24 different samples. It has the expression of 34,000 genes in the 24 samples. The salinity treatment exposed the plants to 150 mM salt, and the heat treatment exposed plants to 37°C temperatures. They had a control group, a salinity group, a heat group, and a salinity + heat group. This dataset also includes samples who were treated with a bacteria, Pseudomonas putida, but for simplicity I will exclude those samples. That leaves 12 of the original 24 samples. 

What I'd like to do is use PCA and hierarchical clustering to see what are the main differences between the treatments, and if salinity or temperature have a stronger effect on gene expression among the tomatoes. I should be able to visually see if salinity has a stronger effect, heat has a stronger effect, or if they both have strong effects. I am interested in this, because I have performed RNAseq experiments in the past on mice where one treatment has a much more powerful effect on the samples than another treatment, to the point you cannot see the effect of the other treatment at all on my PCA plot. 

I believe the dataset is associated with this paper: 

https://academic.oup.com/plphys/article/199/3/kiaf519/8286221

But the paper mentions a different salinity level than the dataset does, so I'm not completely sure. I will use it as a reference to help confirm I trust my results

## Data Cleaning and EDA

The first thing I need to do is clean my dataset, because it includes samples that I won't need. This experiment includes plants that were treated with Pseudomonas putida, which is a bacteria that helps improve crop health and stress resistance. I'm sure that would be interesting to look at, to see how much it helps resist the stressors of heat and salinity, but for now I just want to make sure I can get my models to work, so I wanted to keep the project simple and not include that factor. 

The samples that I want to keep are:

Control: CT-1, CT-2, CT-3

Salinity: S-1, S-2, S-3

Heat Stress: HS-1, HS-2, HS-3

Salinity + Heat Stress: S+HS-1, S+HS-2, S+HS-3

Usually RNAseq data needs to be normalized, to eliminate technical or biological biases. The dataset provided are the mean normalized counts, so I can skip this step. 

The next thing I wanted to do was filter the dataset for genes that have low expression. One common way to do this is to only keep the genes where the count value is greater than 10 in 25% of the samples. This is important, because a gene can have expression levels that are significantly different between groups, but in reality, the gene expression levels are so low, that it doesn't make that much of a difference biologically. This filtering step brought the dataset from 34,000 genes down to 20,000 genes. 

Next, I wanted to look at the distribution of the data, to see if the data needed to be log transformed. I saw that the data was very skewed with a few datapoints that were very large, and the rest were very small, so I decided to log transform the data. 

![Data Distribution](images/data_distribution.png)


## Model Building / Model Training

### PCA

The first model I wanted to try with my dataset was a PCA plot. I made a PCA model with two principal components. 

![Initial PCA](images/initial_pca.png)

I wanted to see how much of the variance in the data is explained by these two principal components, and the model showed that principal component 1 explained 29% of the variance, and principal component 2 explained 17% of the variance. Combined, these components explain 46% of the variance in the dataset.

I can see that the datapoints separated by the first principal component are separated by heat stress, while the second principal component is separated by salinity. This suggests that heat stress could have a stronger effect on gene expression than salinity, but I want to further confirm this using hierarchical clustering and a heatmap. 

### Heatmap

The second model I wanted to try with my dataset was hierarchical clustering, using a heatmap. 

<img src="images/initial_heatmap.png" alt="Initial Heatmap" width="600">

Based on this initial heatmap, I can see that 








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