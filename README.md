# Social Media Analysis

This package offers a collection of functions designed to analyze social media data, focusing on metrics calculation, engagement visualization, and a dummy sentiment analysis. It is suitable for researchers, marketers, and data analysts who are interested in understanding social media dynamics through statistical and graphical insights.

## Features

- **Calculate Basic Metrics**: Summarizes total posts, likes, comments, shares, and calculates the average engagement rate.
- **Visualize Engagement Trends**: Generates line plots to visualize engagement based on likes, comments, and shares over time.
- **Dummy Sentiment Analysis**: Assigns a random sentiment score (Positive, Negative, Neutral) to each social media post.
- **Visualize Posting Trends**: Creates plots to show the trend of post counts over time.

## Installation

```r
# Install the required packages first, if not already installed
if (!requireNamespace("dplyr", quietly = TRUE))
  install.packages("dplyr")

if (!requireNamespace("ggplot2", quietly = TRUE))
  install.packages("ggplot2")

# You can then load the package using
library(dplyr)
library(ggplot2)
```

## Usage

Here are some examples on how to use the functions within this package:

### Load the dataset

```r
load("data/social_data.RData")
```

### Calculate Metrics

```r
metrics_table <- calculate_metrics(social_data)
print(metrics_table)
```

### Plot Engagement Trends

```r
engagement_plot <- plot_engagement(social_data)
print(engagement_plot)
```

### Perform Dummy Sentiment Analysis

```r
sentiment_data <- analyse_sentiment(social_data$posts)
print(sentiment_data)
```

### Plot Posting Trends

```r
post_trend_plot <- plot_post_trends(social_data)
print(post_trend_plot)
```

## Author

- **A. Rahman**
