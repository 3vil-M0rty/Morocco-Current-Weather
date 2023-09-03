# Morocco-Current-Weather
![header](/Weather_Data/head.png)
## Introduction
In today's data-driven world, APIs (Application Programming Interfaces) serve as the foundation for integrating various services and data sources into our applications. This Jupyter Notebook project embarks on a fascinating journey, showcasing the power of APIs by leveraging two prominent ones: the OpenWeather API and the Google Maps API.

## Dependencies
Before running this project, ensure you have the following dependencies installed:
- pandas
- matplotlib
- folium
- numpy
- googlemaps
- time
- scipy
- datetime
- requests
- bs4

## openWeather API
### Weather Data Retrieval
The project begins by developing a function that can transform a location's name into its corresponding geographic coordinates using the OpenWeather API. Subsequently, another function is created to retrieve weather data from the OpenWeather API in multiple languages. This data retrieval process encompasses real-time weather conditions associated with a given location name, facilitating the examination of atmospheric dynamics and patterns. The collected data encompasses parameters such as temperature, humidity, cloud cover, wind speed, and more.

### Moroccan Cities Extraction Using BeautifulSoup
I extracted the names of Moroccan cities from this [wikipedia page](https://fr.wikipedia.org/wiki/Liste_des_villes_du_Maroc) using `BeautifulSoup`, to use them as the locations for data retrieval. Out of the 345 cities that were parsed, I successfully obtained weather data for 343 cities.

### Converting And Saving Results
I employed the `pandas` library to transform the retrieved weather data into a dataframe, which I subsequently saved as a .csv file for potential future reference.


## Data Exploration
### Scatter Plots
#### Max Temperature In Celsius vs Latitude
![temps-vs-latitude](/Weather_Data/temp_vs_lat.png)
#### Humidity Percentage vs Latitude
![humidity-vs-latitude](/Weather_Data/humidity_vs_lat.png)
#### Cloudiness Percentage vs Latitude
![cloudiness-vs-latitude](/Weather_Data/cloudiness_vs_lat.png)
#### Wind Speed In meters/sec vs Latitude
![wind-vs-latitude](/Weather_Data/wind_vs_lat.png)

### Linear Regression
A linear regression was preformed on the four weather parameters: max temperature, humidity, cloudiness and windspeed in relation to latitude.
#### Max Temperature
![maxtemp-lr](/Weather_Data/lr_temp_vs_lat.png)
#### Humidity
![humidity-lr](/Weather_Data/lr_humdity_vs_lat.png)
#### Cloudiness
![cloudiness-lr](/Weather_Data/lr_cloudiness_vs_lat.png)
#### WindSpeed
![wind-lr](/Weather_Data/lr_wind_vs_lat.png)

## Folium Maps
By utilizing the `folium` library, I successfully generated a total of four maps. One of these maps displays the cities along with their corresponding weather data, while the other three are heatmaps representing maximum temperature, humidity, and cloudiness. To view these maps rendered within the Jupyter notebook, please click on this link [maps](https://nbviewer.org/github/3vil-M0rty/Morocco-Current-Weather/blob/main/Morocco_Today%27s_Weather.ipynb), as they are not displayed here on GitHub.

## Google Maps API
To begin the process, I prompted the user to input their desired maximum and minimum temperature preferences. With this information, I filtered the list of cities accordingly, narrowing down the selection to those meeting the temperature criteria. Subsequently, I employed the Google Maps API (`gmaps`) to identify nearby hotels for each of these selected cities. The gathered hotel data was organized into a structured dataframe using the `pandas` library, making it easier to work with. Finally, I created an interactive map using `folium`, which not only displayed the locations of the hotels but also provided additional information such as the hotel's name, the city it's located in, and its rating.

## Data Sources
- openWeather API
- Wikipedia
- Google Maps API
