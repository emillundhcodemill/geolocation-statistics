
# geolocation-statistics
A piece of anonymized page-view and click statistics from a production web service

This repository contains event statistics from a web service.
The service is running an A/B test which randomly chooses between two versions of a page presented to the visitors. 
The two choices in the A/B test are each given an ID, which are stated in the statistics schema (below) as `choice_id`.

The location of the collected events are saved by geohash (www.geohash.com) and were offset by a random amount 
in the creation of this test data. In order to preserve structure, we chose random offsets depending on location 
such that close-by points were offset by the same random amount,
while points lying further apart were offset by different amounts in different directions.

### JSON Schema
```
[
  {
    "action": type of interaction between user and web service, here "pageload" or "click"
    "geohash": 12-digit anonymized geohash
    "choice_id": the version of the web page served to the user in the A/B test
  }
]
```
