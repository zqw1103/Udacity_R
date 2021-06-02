# Udacity_R

In this project, you will use data provided by Motivate, a bike share system provider for many major cities in the United States, to uncover bike share usage patterns. You will compare the system usage between three large cities: Chicago, New York City, and Washington, DC.
The Datasets
Randomly selected data for the first six months of 2017 are provided for all three cities. All three of the data files contain the same core six (6) columns:
● Start Time (e.g., 2017-01-01 00:07:57)
● End Time (e.g., 2017-01-01 00:20:53) ● Trip Duration (in seconds - e.g., 776)
● Start Station (e.g., Broadway & Barry Ave)
● End Station (e.g., Sedgwick St & North Ave)
● User Type (Subscriber or Customer)
The Chicago and New York City files also have the following two columns:
● Gender
● Birth Year
 The original files are much larger and messier, and you don't need to download them, but they can be accessed here if you'd like to see them (Chicago, New York City, Washington). These files had more columns and they differed in format in many cases. Some data wrangling has been performed to condense these files to the above core six columns to make your analysis and the evaluation of your R skills more straightforward.
Statistics Computed
 There are a number of different areas of interest available in this dataset. Here are some ideas we came up with for exploration, but feel free to explore any question you are interested in.
#1 Popular times of travel (i.e., occurs most often in the start time)
● What is the most common month?
#2 Trip duration
● What's the average travel time in all the three cities?
#3 User info
● What are the counts of each gender (only available for NYC and Chicago)?
