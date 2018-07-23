
Objective:
------

Analyze traffic patterns and its effects on mobility for either of these cities - Bangalore, __Delhi__, Mumbai or Hyderabad

Knowledge: 
------

- [Gist](https://gist.github.com/apoorv74/7335567c375db67095e614997ee0eed3)


Possibilities:
------

- [] Busiest Day of the year 2016/2017/2018 till now
- [] Effects of timing during events like IPL
- [x] Busiest Airport/Station rides [Might require to normalize by distance between points]
- [x] How far can you go in an hour - In various cities
- [x] Busiest patches in a city
- [x] Time per km ranges at every Hour of the day
- [x] Longest Journeys
- [x] Average time deviation from 0-23 for every route

Steps to reproduce the analysis:
------

- Clone this repo
- Create a Data directory under the parent directory
- Download Datasets from [UBER Movement](https://movement.uber.com/explore/)
  - There are two types of datasets involved here - 2018 Q1 time taken across every route
  - GeoJSON files for cities (wards for Bangalore and Delhi, hex tiles for Mumbai)
- Move all _Time taken per route_ datasets to the _Data_ directory. Save these files as [city_name]_hod_times.csv
- Create a _spatial_ directory inside the _Data_ directory and move all _spatial_ (GeoJSON) datasets here.
- A distance matrix will have to be evaluated between wards
  - This is done using QGIS
    - Open the GeoJSON file in QGIS
    - Find the polygon centroids (Use the _Polygon Centroid_ function inside _Geometry Tools_ in the _Vector_ toolbar option)
    - Find the distance between every pair of points (Use the _Distance Matrix_ function under _Analysis Tools_ in the _Vector_ toolbar option)
    - Save this file as [city_name]_distance_matrix.csv
- Run all chunks on the .Rmd file
- HTML output will be exported with output of all executed chunks inside the _Notebooks_ directory