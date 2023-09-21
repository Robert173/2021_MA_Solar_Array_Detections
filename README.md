# 2021 Massachusetts Solar Array Detections

## Project Background: 
The purpose of this project was to produce a geospatial database of ground-based solar arrays in Massachusetts to study the impact of their construction on land-use change in the state. To do this, I trained and configured a convolutional neural network (CNN) that classifies pixels as either array or background. I used this model to predict array pixels in 2021 aerial imagery of Massachusetts, from which I was able to produce panel polygons and bounding polygons of array structures. With these I was able to estimate the land use conversion caused by array construction in each county of Massachusetts.

## Project Methods:
Solar arrays were manually labeled in 4-band, 15 cm resolution aerial imagery of Massachusetts taken in 2021 [^1].

The predicted array pixels were converted to vector polygons and filtered.

## Repository Contents
This repository contains zipped shapefiles with a variety of data products from the project. Arrays are represented as vector shapefiles of panels, centroids of arrays, and array "fields" (bounding polygons). These are rendered at different minimum sizes (array field >= 1000, 2000, 4000, 8000, 16000, 32000, 64000 sq m). Also, unfiltered shapefiles are provided for predictions in UTM zone 18 and 19. 

Array fields (from field >= 2000 shapefile) were clipped to a 2005 land use shapefile and divided by county to provide estimates of regional land use changes caused by array development[^2].

## Data Disclaimer
The data in this repository has not been checked for accuracy against imagery, however I have filtered it using several spatial rule sets to remove most false positives. Individual inspections of sample arrays have shown a generally high degree of accuracy.


[^1] The 2021 imagery was registered in NAD83(2011) UTM zone 18 or 19. The boundary between 18 and 19 roughly bisects Worcester county. 
[^2] Commercial array development began in earnest in 2008 and peaked in 2012. 
