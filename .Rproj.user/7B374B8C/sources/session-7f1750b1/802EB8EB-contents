#' Social Media Analysis Functions
#'
#' This collection of functions is designed to analyze social media data.
#' The functions cover various aspects of social media analytics, including
#' the calculation of basic metrics such as total posts, likes, comments, shares,
#' and the average engagement rate. Additionally, visualization functions are provided
#' to illustrate engagement trends and posting activity over time.
#' A dummy sentiment analysis is also included, which assigns a random sentiment
#' score to each post.
#'
#' The `calculate_metrics` function summarizes engagement data, providing insights
#' into social media performance. `plot_engagement` and `plot_post_trends` functions
#' allow for easy visualization of engagement and post count trends, respectively.
#' The `analyse_sentiment` function adds basic sentiment analysis capabilities,
#' demonstrating the potential for more sophisticated text analysis.
#'
#' @section Functions:
#' \itemize{
#'   \item{\code{calculate_metrics}: Calculate summary metrics from social media data.}
#'   \item{\code{plot_engagement}: Visualize engagement trends over time.}
#'   \item{\code{analyse_sentiment}: Perform a dummy sentiment analysis on post data.}
#'   \item{\code{plot_post_trends}: Plot the trend of the number of posts over time.}
#' }
#' @section Data:
#' The functions expect the input data to be in a specific format, as outlined
#' in the individual function documentation.
#' @keywords social media, analysis, sentiment, visualization
#' @name social-media-analysis-functions
#' @docType package
#' @author A. Rahman


#' Calculate Basic Social Media Metrics
#'
#' This function calculates basic engagement metrics for social media data including
#' total posts, likes, comments, shares, and average engagement rate.
#' @param data A data frame with social media activity data.
#' @return A data frame summarising the total posts, likes, comments, shares,
#'   and average engagement rate.
#' @export
#' @importFrom dplyr summarise
#' @examples
#' calculate_metrics(social_data)
calculate_metrics <- function(data) {
  dplyr::summarise(data,
                   total_posts = sum(posts),
                   total_likes = sum(likes),
                   total_comments = sum(comments),
                   total_shares = sum(shares),
                   average_engagement_rate = (sum(likes + comments + shares) / sum(posts))
  )
}

#' Visualize Engagement Trends
#'
#' This function creates a line plot visualizing the engagement trends based on
#' the likes, comments, and shares over time.
#' @param data A data frame with social media activity data.
#' @return A ggplot object showing the engagement trends.
#' @export
#' @importFrom ggplot2 ggplot aes geom_line labs
#' @examples
#' plot_engagement(social_data)
plot_engagement <- function(data) {
  ggplot2::ggplot(data, ggplot2::aes(x = date, y = likes + comments + shares)) +
    ggplot2::geom_line(group = 1, color = "blue") +
    ggplot2::labs(title = "Daily Engagement Trend", x = "Date", y = "Total Engagement (Likes + Comments + Shares)")
}

#' Dummy Sentiment Analysis
#'
#' This function assigns a dummy sentiment score to social media posts.
#' It randomly assigns each post a sentiment of "Positive", "Negative", or "Neutral".
#' @param posts A data frame or vector containing social media posts.
#' @return A data frame with sentiment scores assigned to each date.
#' @export
#' @examples
#' analyse_sentiment(social_data$posts)
analyse_sentiment <- function(posts) {
  sentiment_scores <- sample(c("Positive", "Negative", "Neutral"), length(posts), replace = TRUE)
  data.frame(date = posts$date, sentiment = sentiment_scores)
}

#' Visualize Posting Trends
#'
#' This function creates a line plot visualizing the number of posts over time.
#' @param data A data frame with social media activity data.
#' @return A ggplot object showing the posting trends.
#' @export
#' @importFrom ggplot2 ggplot aes geom_line geom_point labs
#' @examples
#' plot_post_trends(social_data)
plot_post_trends <- function(data) {
  ggplot2::ggplot(data, ggplot2::aes(x = date, y = posts)) +
    ggplot2::geom_line(group = 1, color = "green") +
    ggplot2::geom_point(color = "darkgreen") +
    ggplot2::labs(title = "Post Trend Over Time", x = "Date", y = "Number of Posts")
}

# Loading the dataset
load("data/social_data.RData")

# Using the calculate_metrics function to create a metrics table
metrics_table <- calculate_metrics(social_data)

# Calculating metrics and printing the table
print(metrics_table)

# Creating and printing the engagement plot
engagement_plot <- plot_engagement(social_data)
print(engagement_plot)

# Performing dummy sentiment analysis and printing the results
sentiment_data <- analyse_sentiment(social_data)
print(sentiment_data)

# Creating and printing the posting trend plot
post_trend_plot <- plot_post_trends(social_data)
print(post_trend_plot)
