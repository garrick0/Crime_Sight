# Repository for the image based analysis of DV data

This project intends to improve on previous MCMC modeling efforts to model domestic violence distribution at a local govenment area(LGA) level. This is achieved through integrating methods of image analysis based on scraped google street view data. 

This is completed within a set of ipython notebooks, which allow an effective means of containerising functionality and stepping through this pipeline in a logic means with clear annotations. 

This project consists of four distinct modules:
- Initial DVA Analysis
- Street_View_Scraping
- Street_View_Image_Analyis
- Combined DVA Analysis


##Initial DVA Analysis

This section performs MCMC modeling of crime data using census data as independent variables(ratio seperated males, population density, weekly income, weekly rent, unemployment). Models are trained and subsequently analysed through a test set. 

##Street_View_Scraping

This section downloads all google maps photos within a rectangular area. This requires a starting point at a likely population centre as well as the latitude and longitude of Nth/Sth/Est/Wst borders. This is used to locate and download images from each LGA. 

##Street_View_Image_Analysis

This section utilises darknet, an image recognition library to analyse the previously scraped images for salient objects. Classified image content is then aggregated over an LGA level to provide a total sum of each class of object classified in each LGA. 

##Combined DVA Analysis

This section intends to analyse the object classifications over each LGA. Objects to note are car make/model which may be used to determine vehicle value as well as graffiti or vegetation. The more salient features from this analysis may be used as independent variables in addition to census values in an MCMC derived model of crime. 




Dependencies:
- darknet (https://github.com/pjreddie/darknet)
- streetview (https://github.com/robolyst/streetview)
