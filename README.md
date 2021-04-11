# geo_tweet
Filter Twitter v.2 Academic Research's data within location and date

Given a file of tweets extrated from the new v.2 API, this function filters the exact geolocated ones according to a user specified location and radius together with a date.This allows to get precise event locations.


<details open="open">
  <summary><h2 style="display: inline-block">Obtain data in Python </h2></summary>

The package `twarc2` can be used in python in order to extract all tweets that match an specific query. The following code provides an example of this:

`twarc2 search --archive "(#BLM OR #BlackLivesMatter) has:geo lang:en -is:retweet place_country:US" --start-time "2020-05-25" --end-time "2021-01-31" >output.json
`
To obtain the full features we use the option `flatten`:

`twarc2 flatten output.json output_flat.json`

and export as .csv to import latter in R:

`twarc2 csv output_flat.json blm_python.csv`

`geo_tweets`assumes that the input in `data` contains only the subsect of data with exact geolocation (column `geo.coordinates.coordinates`). 

<details open="open">
  <summary><h2 style="display: inline-block">Example </h2></summary>

`dd<-geo_tweet(38.8977,-77.0365,1,blm_geo,"2020-06-01 00:00:00","2021-01-01 00:00:00")
`
This ouput stores the location only requisites in `dd` and both the location and data filtering in `date_subset`.





