# Project 2
This is my repository for Project 2 for my Stat Computing Course at JHU BSPH

## Project Breakdown 
Instructions for the project can be found here: https://lcolladotor.github.io/jhustatcomputing/projects/project-2/

### Section 1: Fun with functions
In this section, I wrote my own R functions to compute common statistical quantities, without having to rely on R's built-in versions.

- **`Exp(x, k)`**: approximates eˣ using the first `k` terms of its Taylor series expansion, without using `exp()`.
- **`sample_mean(x)`** and **`sample_sd(x)`**: calculate the sample mean and sample standard deviation of a numeric vector, without using `mean()` or `sd()`.
- **`calculate_CI(x, conf)`**: builds a confidence interval for the population mean using the t-distribution, with an adjustable confidence level. Results were checked against R's `confint()`.

### Section 2: Wrangling data

In this section, I cleaned and combined two TidyTuesday datasets on Australian rainfall and temperature into one data frame, `df`.

- **Cleaning**: dropped rows with missing values and combined the `year`, `month` and `day` columns into a single `date` column.
- **Standardizing**: converted city names to upper case so they matched across both datasets.
- **Joining**: merged the rainfall and temperature data by city and date, keeping only observations found in both.

### Section 3: Data visualization

In this section, I used `ggplot2` to explore the wrangled data.

- **Temperature over time**: a line plot of daily maximum and minimum temperatures from 2014 onwards, faceted by city.
- **`plot_rainfall(city_name, year)`**: a reusable function that returns a histogram of daily rainfall on a log scale for any city and year. It checks its inputs and gives a helpful error message when a city or year is not in the data.

### Section 4: Apply functions and plot

In this section, I applied my functions from Section 1 to the rainfall data.

- **`rain_df`**: the sample mean, standard deviation, and 95% confidence interval of daily rainfall for each city and year from 2014 onwards.
- **Confidence interval plot**: the yearly means with error bars for the confidence intervals, faceted by city.
