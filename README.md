# Python_APIs
What's the Weather Like?
Background
Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's answer a fundamental question: "What's the weather like as we approach the equator?"
Now, we know what you may be thinking: "Duh. It gets hotter..."
But, if pressed, how would you prove it?

![obraz](https://user-images.githubusercontent.com/87150331/154318467-7b5d7e77-206f-4f0a-ac6f-4fb4be5e8415.png)




Adding A .gitignore File
I don't want the api_keys.py file containing the API key to be exposed to the public on GitHub, as this would mean anyone could copy and use our API key, possibly causing to incur charges.
When I type git status in the command line, I can see all the files created so far that are untracked.
If I only wanted to add the WeatherPy.ipynb file to GitHub I could type git add WeatherPy.ipynb. However, every time I want to add a new file or update current files to the repository, I have to add each file individually, which is time-consuming and cumbersome. Instead, I can add the files I don't want to track to the .gitignore file.
Before I added our files to GitHub, added api_keys.py to the .gitignore file. 

To do that follow these steps:


Open the GitHub folder in VS Code.


Open the .gitignore file, and on the first line type the following:


# Adding config.py file.
api_keys.py


While the .gitignore file is open, add the API_practice.ipynb and random_numbers.ipynb files and save the file.


In the command line, type git status and press Enter. The output should say the .gitignore file has been modified and the WeatherPy.ipynb file is untracked.


Use git add, git commit, and git push to commit the modifications to .gitignore and the WeatherPy.ipynb file to GitHub.


On GitHub, the only new file you should see is the WeatherPy.ipynb file.


Part I - WeatherPy

In this example, I'll be creating a Python script to visualize the weather of 500+ cities across the world of varying distances from the equator. To accomplish this, I'll be utilizing a simple Python library, the OpenWeatherMap API, and a little common sense to create a representative model of weather across world cities.
The first requirement is to create a series of scatter plots to showcase the following relationships:

Temperature (F) vs. Latitude
Humidity (%) vs. Latitude
Cloudiness (%) vs. Latitude
Wind Speed (mph) vs. Latitude

After each plot, I will add a sentence or two explaining what the code is analyzing.
The second requirement is to run a linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

Northern Hemisphere - Temperature (F) vs. Latitude
Southern Hemisphere - Temperature (F) vs. Latitude
Northern Hemisphere - Humidity (%) vs. Latitude
Southern Hemisphere - Humidity (%) vs. Latitude
Northern Hemisphere - Cloudiness (%) vs. Latitude
Southern Hemisphere - Cloudiness (%) vs. Latitude
Northern Hemisphere - Wind Speed (mph) vs. Latitude
Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, I will take the time to explain what the linear regression is modeling. For example, I will describe any relationships I notice and any other analysis I may have.

My final notebook:

Randomly select at least 500 unique (non-repeat) cities based on latitude and longitude.
Perform a weather check on each of the cities using a series of successive API calls.
Include a print log of each city as it's being processed with the city number and city name.
Save a CSV of all retrieved data and a PNG image for each scatter plot.


Part II - VacationPy


To complete this part of the assignment, I will need to do the following:



Create a heat map that displays the humidity for every city from Part I.

![obraz](https://user-images.githubusercontent.com/87150331/154319260-bb35bc91-5894-48b9-a7ef-915fc1164ef6.png)


Narrow down the DataFrame to find my ideal weather condition. For example:


A max temperature lower than 80 degrees but higher than 70.


Wind speed less than 10 mph.


Zero cloudiness.


Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.


Use Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.


Plot the hotels on top of the humidity heatmap with each pin containing the Hotel Name, City, and Country.

![obraz](https://user-images.githubusercontent.com/87150331/154319385-434ce8a3-1b19-4ae1-bd30-a8ce8b99c2f3.png)



Hints and Considerations


The city data you generate is based on random coordinates as well as different query times. As such, your outputs will not be an exact match to the provided starter notebook.



Next, I will spend the requisite time necessary to study the OpenWeatherMap API. Based on my initial study, I will be able to answer basic questions about the API: Where do I request the API key? Which Weather API in particular will I need? What URL endpoints does it expect? What JSON structure does it respond with? Before I will write a line of code, I will be aiming to have a crystal clear understanding of my intended outcome.



In building my script, I will pay attention to the cities I am using in my query pool. Am I getting coverage of the full gamut of latitudes and longitudes? Or Am I simply choosing 500 cities concentrated in one region of the world? Even if I were a geographic genius, simply rattling 500 cities based on my human selection would create a biased dataset. I am thinking of how I should counter this. (Hint: Consider the full range of latitudes).


Once I have computed the linear regression for one chart, the process will be similar for all others. As a bonus I will create a function that will create these charts based on different parameters.


Each coordinate will trigger a separate call to the Google API. To create my own criteria to plan my vacation, I will try to reduce the results in my DataFrame to 10 or fewer cities.









