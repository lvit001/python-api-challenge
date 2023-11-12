# python-api-challenge
## WeatherPy
# Use the OpenWeatherMap API to retrieve weather data from the cities list generated in the started code
- First start by setting the API url which includes the weather_api_key and a parameter for units, which will be in metric units.
- To create the city_url, reference the URL we created above and add the "&q=" parameter along with the variable for the city created in the for loop.
- Add in the requests.get(city_url).json() code to parse the data found there and convert to a JSON file
- Add code to pull each city feature from the city_weather JSON file.
- Convert the city data dictionary into a data frame and display the count of each column
- Use to_csv code to convert the data frame we created into a new CSV file
# Create the Scatter Plots Requested
- Created multiple scatter plots comparing city features such as temperature, humidity, and cloudiness to the cities' latitudes.
- Used the plt.scatter code to create the initial chart and then used additional coding to add a title, label the axes, and add grid lines.
- Displayed the charts with plt.show()
- Saved the various figures using plt.savefig
It definitely would have been helpful to define a function to make these charts, luckily, we were prompted to do this further on!
# Requirement 2: Compute Linear Regression for Each Relationship
- Defined a function called "linreg" that used variables for the data frame, column for x values, column for y values, and annotation of x and y points for plotting the linear equation formula.
- The function determine x and y values, took the linear regression of the x and y values and set those equal to other variables, determined regression values, created the linear equation, and then plotted all of the data. It also printed out the r-value for the two variables to determine their correlation.
- Did have some help from chatgpt with figuring out how to change the x and y annotation points for each graph, which is where it suggested to include them as variables in the function so they could easily be adjusted
- Created two new data frames using a .loc function that would look at a latitude above 0 for the northern hemisphere and below 0 for the southern hemisphere.
- Used the linreg formula defined above to plot and find correlation between the request variables in the northern and southern hemispheres.
## VacationPy
# Step 1: Create a map that displays a point for every city in the city_data_df DataFrame. The size of the point should be the humidity in each city.

