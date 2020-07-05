A tool to fetch and catalog data about the PWRCell product line using the JSON
endpoints hosted at pwrcell.generac.com

## pwrcell.generac.com API
All under https://pwrcell.generac.com

* Get list of devices
  * `/{profileId}.json`
  * profileId comes down in the initial html response
  * ex: `{"dvcs":[{"s":"000101000004","n":"Pika PVLink ","st":8208,"t":"PV Module","p":614,"et":272466}, ... ]}`
* Get power (watts) per time period
  * `/power/{deviceId}/{endTimeLocalTzSecs}/{lookbackRangeSecs}.json`
    * `endTimeLocalTzSecs` can be special value `now`
    * `lookbackRangeSecs` can be special value `all`
      * I'm unsure how far back `all` goes
  * Period is 3600s (1hr) unless `lookbackRangeSecs` is less than 36hr then period is 60s (1m) (assuming based on JS code)
  * ex: TODO
* Get energy (used/stored/created?) in (watt hours?) per time period
  * `/charge/{deviceId}/{endTimeLocalTzSecs}/{lookbackRangeSecs}.json`
    * `endTimeLocalTzSecs` can be special value `now`
    * `lookbackRangeSecs` can be special value `all`
      * I'm unsure how far back `all` goes
  * Period is 3600s (1hr), doesn't appear to provide high-resolution view even with short `lookbackRangeSecs`
  * ex: TODO
* Get battery charge (watt hours) per time period
  * `/charge/{deviceId}/{endTimeLocalTzSecs}/{lookbackRangeSecs}.json`
    * `endTimeLocalTzSecs` can be special value `now`
    * `lookbackRangeSecs` can be special value `all`
      * I'm unsure how far back `all` goes
  * Only valid for battery device
  * Period is 3600s (1hr) unless `lookbackRangeSecs` is less than 36hr then period is 60s (1m) (assuming based on JS code)
  * ex: TODO
* Wind Turbine Data?
  * `/last_power/{deviceId}.json ???`
