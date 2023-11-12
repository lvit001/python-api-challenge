# python-api-challenge
## WeatherPy
### Use the OpenWeatherMap API to retrieve weather data from the cities list generated in the started code
- First start by setting the API url which includes the weather_api_key and a parameter for units, which will be in metric units.
- To create the city_url, reference the URL we created above and add the "&q=" parameter along with the variable for the city created in the for loop.
- Add in the requests.get(city_url).json() code to parse the data found there and convert to a JSON file
- Add code to pull each city feature from the city_weather JSON file.
- Convert the city data dictionary into a data frame and display the count of each column
- Use to_csv code to convert the data frame we created into a new CSV file
### Create the Scatter Plots Requested
- Created multiple scatter plots comparing city features such as temperature, humidity, and cloudiness to the cities' latitudes.
- Used the plt.scatter code to create the initial chart and then used additional coding to add a title, label the axes, and add grid lines.
- Displayed the charts with plt.show()
- Saved the various figures using plt.savefig
It definitely would have been helpful to define a function to make these charts, luckily, we were prompted to do this further on!
### Requirement 2: Compute Linear Regression for Each Relationship
- Defined a function called "linreg" that used variables for the data frame, column for x values, column for y values, and annotation of x and y points for plotting the linear equation formula.
- The function determine x and y values, took the linear regression of the x and y values and set those equal to other variables, determined regression values, created the linear equation, and then plotted all of the data. It also printed out the r-value for the two variables to determine their correlation.
- Did have some help from chatgpt with figuring out how to change the x and y annotation points for each graph, which is where it suggested to include them as variables in the function so they could easily be adjusted
- Created two new data frames using a .loc function that would look at a latitude above 0 for the northern hemisphere and below 0 for the southern hemisphere.
- Used the linreg formula defined above to plot and find the correlation between the request variables in the northern and southern hemispheres.
## VacationPy
### Step 1: Create a map that displays a point for every city in the city_data_df DataFrame. The size of the point should be the humidity in each city.
- Used the hvplot.points code to plot all of the cities in the city_data_df. 
- Plotted the points by longitude and latitude, used the OSM title, set the frame height and width, set the size equal to the level of humidity, scaled the data points to 0.6, and set the color equal to the city name
### Step 2: Narrow down the city_data_df DataFrame to find your ideal weather condition
- Created a new data frame called "ideal_cities" and used loc functions to specify the ideal weather conditions which were: temperature between 15-30 celsius, cloudiness below 20%, and humidity below 50%.
- Dropped any rows that had null values using dropna(how="any)
### Step 3: Create a new data frame called hotel_df
- Created a new data frame called hotel_df that only included the City, Country, Lat, Lng, and Humidity columns. Made this a copy of the hotel_df data frame using copy() function
- Added a new empty column called "Hotel Name"
### Step 4: For each city, use the Geoapify API to find the first hotel located within 10,000 meters of your coordinates
- Set the radius to 10000 meters
- Added parameters for categories (accommodation.hotel), apikey, and limit (1 since we want only the first closest hotel)
- To find latitude and longitude, used a loc function in the hotel df to look at the Lat and Lng columns at the specific index
- For the filter and bias parameters, added code we learned in class that would pull from the parameters we already set
- Used the requests.get function on the base_url along with the parameters
- Used a JSON function to convert the name_address file to a JSON file.
### Step 5: Add the hotel name and the country as additional information in the hover message for each city in the map
- Used the hvplot.points function to create a map of the hotel_df data frame, which is plotted by the Lng and Lat columns, the size of the point was based on the humidity value, the color was based on the city, and used the hover_cols function to display the Hotel Name and Country column values as well.
