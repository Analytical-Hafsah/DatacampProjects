# Investigating Netflix Movies and Guest Stars in The Office
![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/netflix.jpg)

## Project Description.
Netflix! What started in 1997 as a DVD rental service has since exploded into the largest entertainment/media company by market capitalization, boasting over 200 million subscribers as of January 2021.
Given the large number of movies and series available on the platform.
In this project, I used data manipulation skills and dive into the entertainment industry. I used the knowledge I gained from Introduction to Python and Intermediate Python to solve this real-life dataset. I applied everything from lists and loops to pandas and matplotlib.

## Project tasks
1. Loading a friend's data into a dictionary
2. Creating a DataFrame from a dictionary
3. A visual inspection of our data
4. Loading the rest of the data from a CSV
5. Filtering for movies!
6. Creating a scatter plot
7. Digging deeper
8. Marking non-feature films
9. Plotting with color!
10. What next?

# (see all codes in the python file above

## 1. Loading your friend's data into a dictionary
As evidence of this, datacamp provided me with the following information. For the years from 2011 to 2020, the average movie durations are 103, 101, 99, 100, 100, 95, 95, 96, 93, and 90, respectively.
I started by working with pandas and then created the DataFrame from scratch. 

## Creating a dictionary

{'years': [2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020], 
'durations': [103, 101, 99, 100, 100, 95, 95, 96, 93, 90]}

## 2. Creating a DataFrame from a dictionary
To convert our dictionary movie_dict to a pandas DataFrame, we will first need to import the library under its usual alias. 
We'll also want to inspect our DataFrame to ensure it was created correctly.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/durations_df.JPG)

## 3. A visual inspection of our data
Alright, we now have a pandas DataFrame, the most common way to work with tabular data in Python. 
Now back to the task at hand. We want to follow up on our friend's assertion that movie lengths have been decreasing over time. 
A great place to start will be a visualization of the data.
Given that the data is continuous, a line plot would be a good choice, with the dates represented along the x-axis and the average length in minutes along the y-axis. 
This will allow us to easily spot any trends in movie durations. There are many ways to visualize data in Python, but matploblib.pyplot is one of the most common packages to do so.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/Netflix_Movies_Duration.png)

## 4. Loading the rest of the data from a CSV
Well, it looks like there is something to the idea that movie lengths have decreased over the past ten years! 
But equipped only with our friend's aggregations, we're limited in the further explorations we can perform. 
There are a few questions about this trend that we are currently unable to answer, including:
      1. What does this trend look like over a longer period of time?
      2. Is this explainable by something like the genre of entertainment?
Upon asking our friend for the original CSV they used to perform their analyses, they gladly oblige and send it. 
We now have access to the CSV file, available at the path "datasets/netflix_data.csv". Let's create another DataFrame, this time with all of the data. 
Given the length of our friend's data, printing the whole DataFrame is probably not a good idea, so we will inspect it by printing only the first five rows.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/netflix_df.JPG)

## 5. Filtering for movies!
Okay, we have our data! Now we can dive in and start looking at movie lengths.
Or can we? Looking at the first five rows of our new DataFrame, we notice a column type. 
Scanning the column, it's clear there are also TV shows in the dataset! 
Moreover, the duration column we planned to use seems to represent different values depending on whether the row is a movie or a show (perhaps the number of minutes versus the number of seasons)?
Fortunately, a DataFrame allows us to filter data quickly, and we can select rows where type is Movie. 
While we're at it, we don't need information from all of the columns, so let's create a new DataFrame netflix_movies containing only title, country, genre, release_year, and duration.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/netflix_movies_col_subset.JPG)

## 6. Creating a scatter plot
Okay, now we're getting somewhere. We've read in the raw data, selected rows of movies, and have limited our DataFrame to our columns of interest. 
Let's try visualizing the data again to inspect the data over a longer range of time.
This time, we are no longer working with aggregates but instead with individual movies. 
A line plot is no longer a good choice for our data, so let's try a scatter plot instead. 
We will again plot the year of release on the x-axis and the movie duration on the y-axis.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/Movie_Duration_by_Year_of_Release.png)

## 7. Digging deeper
This is already much more informative than the simple plot we created when our friend first gave us some data. We can also see that, 
while newer movies are overrepresented on the platform, many short movies have been released in the past two decades.
Upon further inspection, something else is going on. Some of these films are under an hour long! 
Let's filter our DataFrame for movies with a duration under 60 minutes and look at the genres. 
This might give us some insight into what is dragging down the average.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/short_movies.JPG)

## 8. Marking non-feature films
nteresting! It looks as though many of the films that are under 60 minutes fall into genres such as "Children", "Stand-Up", and "Documentaries". 
This is a logical result, as these types of films are probably often shorter than 90 minute Hollywood blockbuster.
We could eliminate these rows from our DataFrame and plot the values again. 
But another interesting way to explore the effect of these genres on our data would be to plot them, but mark them with a different color.

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/colors.JPG)

## 9. Plotting with color!
We now have a colors list that we can pass to our scatter plot, which should allow us to visually inspect whether these genres might be responsible for the decline in the average duration of movies.
This time, we'll also spruce up our plot with some additional axis labels and a new theme with plt.style.use().

![](https://github.com/Analytical-Hafsah/DatacampProjects/blob/main/DATACAMP/Movie_Duration_by_Year_of_Release_2.png)


## 10. What next?


# Conclusion 
As suspected, non-typical genres such as children's movies and documentaries are all clustered around the bottom half of the plot. 
But we can't know for certain until we perform additional analyses.
