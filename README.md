# Final_Project
Group Name: Data Night

Group Members: Brian Stoffel, Jasmin Pattschull, Tracy Atienza, Christina Galley, Niu Rabiu

## Topic
Date Night in Rochester, Minnesota

## Background
You have dinner plans with your date and just got asked by your head dr. to be on call. There's a chance you may or may not need to work later in the night so you do not want to cancel your plans since you were looking forward to this date. They have agreed to meet you close to the hospital where you work and now you need to find a restaurant under a 15-22 minute walk just in case you need to go back to the hospital.

## Data Source
Google's Places: Nearby Search API

https://maps.googleapis.com/maps/api/place/nearbysearch/output?parameters
https://developers.google.com/maps/documentation/places/web-service/search-nearby

## Group Hypothesis
Can you leave work (St. Mary's Hospital) and get to date night within 15-22 minutes (which is the average time it takes to walk 1 mile according to nike.com, women's health magazine, and various other sources)?

## Group's thought on what approach they may want to use for analysis (i.e. what ML technique we may want to use to investigate the hypothesis)
Utilize Google's Nearby Search API to obtain restaurant data within a given distance and stored the data in a json format: Google Places API Burgers.json

![API](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/calling_google_API.png).png

We used Python to extract and transform the data by filtering out the columns.  

![python code](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/python_code.png)

Once we put the data in a pandas dataframe, we noticed some duplicated rows. To remove the duplicates, we used the `df.drop_duplicates` function.

![python code](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/remove_duplicates_python.png)

Then, we calculated the distances (in miles) between St. Mary's and each restaurant location using the python math module imported with the other dependencies at the top of the code. The radius in the distance function was set to the radius of the earth in miles. We set the coordinates for St. Mary's as the source and used a for loop to iterate through the longitudes and latitudes of each restaurant.

![python code](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/distance_function_python.png)

We merged the new didtance in miles dataframe with the original cleaned dataframe and exported it as a json file.

![python code](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/merge_data.png)

We used Tableau to visualize the Key Statistics provided below.

## Key Statistics
There are 18 restaurants within a reasonable walking distance from Saint Mary's Hospital in Rochester, Minnesota.

There is an overall average rating of 4.239, a minimum rating of 3.1 and a maximum rating of 4.6.

![summary image](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/Screenshot%20of%20Data%20Night%20Summary.PNG)

Below is a picture of the Tableau dashboard.

The blue bar graph indicates the ratings for each restaurant.  The colored bubbles are sized in relation to the price point of each restaurant. (Example: the bigger the bubble the more expensive the restaurant.  Bleu Duck is the most expensive restaurant.)

Cameo and Bleu Duck both have an overall rating of 4.6 which are the two highest rated restaurants within a reasonable walking distance to SMH.

![Tableau dashboard](https://github.com/stoffel-brian/Final_Project/blob/main/Resources/Screenshot%20of%20Data%20Night%20Dashboard.PNG)
