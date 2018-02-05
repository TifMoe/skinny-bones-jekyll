---
layout: article
title: "Predicting Chicago Graduation Rates"
categories: blog
excerpt: "Second project for Metis - using Linear Regression to predict Chicago graduation rates"
tags: [blog, metis, linear regression]
image:
  feature: chicago-grad-feature.jpg  #1024x256
  teaser: chicago-grad-teaser.jpg #400x250
  credit: Tamarcus Brown
  creditlink: https://unsplash.com/photos/zuQDqLFavI4
---

For someone without a formal education in a quantitative field, our second project at Metis definitely pulled me into some new territory. 

The assignment? Build a linear model to predict a continuous variable using (at least in part) data scraped from the web. I choose to try to predict high school graduation rates for Chicago Public Schools using:

- Average ACT score of the school
- Rate of low income students in the school
- Amount of crime surrounding the school
- School type
- State budget for the school

At a high level, my plan of attack for this project is outlined in a page of my notes below:

<center>
	<img src="{{ site.url }}/images/model-selection-sketch.jpg" width="50%">	
</center>


If you're asking yourself what a linear model is then you're in luck! Read on!

___

#### Linear Models

Linear Models are a class of machine learning models that will take in some numerical data (features) and corresponding results (target) to define a line that best captures the shape of the data with the least amount of error. Because a line is really just a function that maps a change in X to a change in Y (remember `Y = mX + b`?) this function can then be used to make future predictions on Y values for new data (or X's) that the model hasn't seen before. 

<center>
	<img src="{{ site.url }}/images/line-sketch.jpg" width="35%">
</center>

The job of a regression model is to take the X's and Y's from the training data and to find the slope and intercept that create a line that best fits the data. A great way to think about the 'best fit' is to picture a line where the distance between the line and all the X's is reduced to the lowest possible amount - the least *error* between the prediction and the actual values. 

<center>
	<img src="{{ site.url }}/images/line-sketch-error.jpg" width="50%">
</center>

In calculating the line with the least error, there are generally two ways to approach it:

> 1) **Analytical Solution** - this uses Linear Algebra to find the exact line with the least amount of error between the predicted values and the actual values. 

> 2) **Numerical Approximation** - this is used when the data is too big to fit in memory (which is required for the analytical solution) and an algorithm called [Gradient Decent](https://en.wikipedia.org/wiki/Gradient_descent) is the optimization method most widely used in numerical approximation

I don't have a ton of data to deal with (there's only so many high schools in the city of Chicago!) so I used #1, the **Analytical Solution**. Specifically, I'm using an algorithm called [Ordinary Least Squares](https://en.wikipedia.org/wiki/Ordinary_least_squares) to estimate the slope and intercept terms in my regression model.

Great! Now that we're all experts on linear regression, let's take a look at the data I used!

___

#### What can I use to predict graduation rates?

**School Attributes:** <br>
I was able to find the Average ACT Score, % of Students from Low Income Families and School Type for CPS high schools in the 2016/2017 school year from the same file containing graduation rates (*thanks, [Chicago Data Portal](https://data.cityofchicago.org/Education/Chicago-Public-Schools-School-Profile-Information-/8i6r-et8s)!*). 

**Budget Data:** <br>
I built a web scrapper to pull the CPS budgets for the 2016/2017 school year from an old DNA info article [here](https://www.dnainfo.com/chicago/20160926/norwood-park/cps-enrollment-budgets-2016-2017-map-list). From this data, I derived a feature for 'dollars per student' to normalize the budget across schools of varying size.

**Crime Data:** <br>
Finally, I found a file with every [crime reported in Chicago during the 2017](https://data.cityofchicago.org/Public-Safety/Crimes-2017/d62x-nvdr). 

I was interested in finding a count of crimes occurring on the same block as CPS high schools during 2017 so I first used a python library called *matplotlib* to map all Chicago crimes against all CPS high school locations:

<center>
	<img src="{{ site.url }}/images/chicago-crimes-schools.png" width="80%">
</center>

This is cool, but I want to find a count of crimes occurring on a specific school block. To do this, I used a python library called *geopy* to find the great circle distance in miles from each school's location to the list of crimes and counted the number of occurrences within .125 miles (or, approximately 1 city block). 

After cleaning my outliers, I could then use this new count to size and color my school marks on the first plot below according to the total number of crimes occurring on the same block as the school. The second plot shows the normalized count of *crimes per student* (to account for schools of varying size) though this count has been increased to *crimes per 1000 students* for visualization purposes. 

<figure class="half">
		<img src="{{ site.url }}/images/crimes-per-school.png">
		<img src="{{ site.url }}/images/crimes-per-student.png">
		<figcaption>Crimes per school and crimes per student visualized above.</figcaption>
</figure>

___

#### Now that I have my data, how do I know what is predictive of graduation rates?

Before I did any modeling, the first step was to conduct some exploratory data analysis to understand the correlations between the features (or, data) and my target (in this case, graduation rates). 

For example, I can see that there are some pretty strong correlations between the Average ACT score, crimes per student, and percent of low-income students:

<figure>
	<center>
		<img src="{{ site.url }}/images/correlation-grad-rates.png" width="80%">
		<figcaption>For correlations, you want to see your data fall into a line that is sloped up or down. An upward line shows that as X increases, Y increases (like Average ACT). But a downward line indicates that as X increases, Y decreases (like crime per student)</figcaption>
	</center>
</figure>

___

#### Finally, let's build a model!

I used cross validation and started with a simple linear model using my most predictive feature - the school's Average ACT score - to predict graduation rates. 

To evaluate my model, I want to compare the average error (distance between my prediction line and the actual values) in my training data to my validation data. Because we use the training data to (cough cough) *train* the model - I want to make sure I'm not seeing a low error due to over fitting. To account for this, I compared the average error (Root Mean Square Error, to be specific) from my training data to the error in predictions on my validation data and make sure they're relatively consistent. With small datasets, you can use cross validation to accomplish this - more to come on cross validation in a future post!

Below, you can see that the relationship doesn't look entirely linear (there's a curve to the data) but my model is a straight line.


<figure>
	<center>
		<img src="{{ site.url }}/images/first-model.png" width="70%">
		<figcaption>Univariate Linear Regression Model using average ACT scores to predict graduation rates</figcaption>
	</center>
</figure>

<center>
<b>Root Mean Square Error:</b><br>
Training Set: 9.15<br>
Validation Set: 9.18
</center>

You can see my average error was around 9.2 percentage points in the model above. Next, I tried to add polynomial terms to my model to capture more of the non-linear relationship. Let's take a look below:

<figure>
	<center>
		<img src="{{ site.url }}/images/second-model.png" width="70%">
		<figcaption>Univariate Polynomial Regression Model using average ACT scores to predict graduation rates</figcaption>
	</center>
</figure>

<center>
<b>Root Mean Square Error:</b><br>
Training Set: 7.97<br>
Validation Set: 8.14
</center>

Wow! You can see that this model is a much better fit to this data and can predict graduation rates using only the Average ACT score within 8 percentage points. 

When I added more features into the model, I found that my training error only improved slightly, but my validation errors started shooting up. This is a tell-tell sign that I'm over-fitting my model, or that I don't have enough data to add that level of complexity. 

In addition to understanding outliers, recursive dimensionality, residual plots and over-fitting, there are a lot of assumptions that go into Linear Regression which are not covered above (you can check out my instructor's [blog](https://dziganto.github.io/data%20science/linear%20regression/machine%20learning/python/Linear-Regression-101-Assumptions-and-Evaluation/) for a great write-up on this!) but I'll save that for a future post. 

**You can check out the full project on my [Github](https://github.com/TifMoe/luther-project/blob/master/notebooks/4_ModelSelection.ipynb).**

