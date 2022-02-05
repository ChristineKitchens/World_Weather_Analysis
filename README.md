# Plan a Vacation Based on Preferred Weather Conditions
Development of web API to allow PlanMyTrip.com customers to select their ideal hotel based on desired travel conditions. To run this code, make sure to obtain the necessary API keys from [OpenWeatherApp](https://openweathermap.org/) and [Google Cloud Platform](https://console.cloud.google.com/home/dashboard?project=tribal-monolith-339901). Enable both the Google Map and Directions API within the Google Cloud Platform.


## Generate List of Lat/Long Coordinates to Obtain Nearby City and Hotel Data
Download the repository and open the [Weather_Database.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Weather_Database/Weather_Database.ipynb) notebook (requires installation of Jupyter Notebook). 

Run the entire notebook to obtain a csv of potential vacation locations and associated weather conditions. The original script creates a list based on a randomly selected list of 2000 lat/long coordinates, but if a larger or smaller sample is required, the following code in the second cell can be modified:

'''
# Create a set of random latitude and longitude combinations.
lats = np.random.uniform(low=-90.000, high=90.000, size=2000)
lngs = np.random.uniform(low=-180.000, high=180.000, size=2000)
lat_lngs = zip(lats, lngs)
lat_lngs
'''

Modify the "size =" argument to increase or decrease the number of potential cities to pick from.

## Generate a List of Potential Vacation Spots 

Next, open the [Vacation_Search.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Search/Vacation_Search.ipynb) notebook and run the entire notebook. Cell 3 will prompt the user to enter the preferred maximum and minimum temperatures for their preferred vacation locations. After completing the prompt, the code will continue executing. An interactive map will generate at the end of the code that the user can navigate. Clicking on a marker will result in a pop up box that gives information on about hotels, location, and weather.

![Interactive Map](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Search/WeatherPy_vacation_map.png)

## Plan a Vacation Itinerary 

If the user want to plan a potential itinerary, open the [Vacation_Itinerary.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Itinerary/Vacation_Itinerary.ipynb) notebook. Run the first 4 cells.

Looking at the interative map, select four potential locations. In cell 5, update the location names with the desired travel points. 

'''
# From the map above pick 4 cities and create a vacation itinerary route to travel between the four cities. 
# 5. Create DataFrames for each city by filtering the 'vacation_df' using the loc method. 
# Hint: The starting and ending city should be the same city.

vacation_start = vacation_df.loc[vacation_df["City"] == "Barwadih",]
vacation_end = vacation_df.loc[vacation_df["City"] == "Barwadih",]
vacation_stop1 = vacation_df.loc[vacation_df["City"] == "Balaghat",]
vacation_stop2 = vacation_df.loc[vacation_df["City"] == "Jhansi",]
vacation_stop3 = vacation_df.loc[vacation_df["City"] == "Bagru",] 
'''

Note that the start and end locations should be the same city.

Execute the remaining cells in the book. Cell 7 will contain a map with a travel itinerary layer.

[WeatherPy_travel_map.png](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Itinerary/WeatherPy_travel_map.png)

Cell 10 will contain a map with markers that, when clicked on, will create a pop up window with location and weather details.

[WeatherPy_travel_map_marker.png](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Itinerary/WeatherPy_travel_map_markers.png)

## Resources
- Data Source: 
  - [WeatherPy_Database.csv](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Weather_Database/WeatherPy_Database.csv)
  - [WeatherPy_vacation.csv](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Search/WeatherPy_vacation.csv)
- Jupyter Notebooks: 
  - [Weather_Database.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Weather_Database/Weather_Database.ipynb)
  - [Vacation_Search.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Search/Vacation_Search.ipynb)
  - [Vacation_Itinerary.ipynb](https://github.com/InRegards2Pluto/World_Weather_Analysis/blob/96de29e80229fff7b18d54dbc95d8954283eb093/Vacation_Itinerary/Vacation_Itinerary.ipynb) 
- Software: Jupyter Notebook