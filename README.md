# Vancouver Assessment Map Cheat Sheet

You might have already seen Jens von Bergmann’s interactive map of Vancouver at https://mountainmath.ca/map/assessment. It’s really useful for looking up zoning, year of construction, tax data, and even the estimated amount of floor space in buildings. I find it essential for understanding the city.

It has also has a great feature that many people don’t know about: the ability to filter data for better visualization through the use of filters in the URL.

## Basics

Say you want to see which Vancouver buildings were built between 1900 and 1940. Just add a `years_1900_1940` filter to the link like so: [https://mountainmath.ca/map/assessment?filter=[**years_1900_1940**]](https://mountainmath.ca/map/assessment?filter=[years_1900_1940])

If you wanted to see all buildings with an estimated floor space ratio (FSR) between 0 and 1, add a `fsr_0.0_1.0` filter: [https://mountainmath.ca/map/assessment?filter=[**fsr_0.0_1.0**]](https://mountainmath.ca/map/assessment?filter=[fsr_0.0_1.0])

Filters can easily be combined with a comma. If you wanted buildings that were built between 1900-1940 _and_ are between 0 and 1 FSR, the link would look like this: [https://mountainmath.ca/map/assessment?filter=[**fsr_0.0_1.0,years_1900_1940**]](https://mountainmath.ca/map/assessment?filter=[fsr_0.0_1.0,years_1900_1940])

## Available Filters

### Area

This lets you filter on lot size (in square metres). Small lots between 100 and 300 square metres: [https://mountainmath.ca/map/assessment?filter=[**area_100_300**]](https://mountainmath.ca/map/assessment?filter=[area_100_300])

### Assessed Value

You can filter by building value (`building`), land value (`land`), and total value (`total`, building+land). 

Lots with building value between $500k and $1M: [https://mountainmath.ca/map/assessment?filter=[**building_500000_1000000**]](https://mountainmath.ca/map/assessment?filter=[building_500000_1000000])

You can also filter on *relative land value* with the `rlv` filter. This shows lots with land value between $1000 and $2000 per square metre: [https://mountainmath.ca/map/assessment?filter=[**rlv_1000_2000**]](https://mountainmath.ca/map/assessment?filter=[rlv_1000_2000])

### Floor Space Ratio (FSR)

[Floor Space Ratio or Floor Area Ratio](https://en.wikipedia.org/wiki/Floor_area_ratio) is one measure of how dense a building is. This data is not exact - it is estimated by Jens based on Vancouver’s LIDAR survey of buildings.
Buildings with an estimated FSR between 0 and 1: [https://mountainmath.ca/map/assessment?filter=[**fsr_0.0_1.0**]](https://mountainmath.ca/map/assessment?filter=[fsr_0.0_1.0])

### Geographic filters

If you want to see everything west of Ontario Street at -123.105118 degrees latitude, you'd use the `westof` filter: [https://mountainmath.ca/map/assessment?filter=[**westof_-123.105118**]](https://mountainmath.ca/map/assessment?filter=[westof_-123.105118])

Same idea for `eastof_`, `northof_`, and `southof_`.

### Land Use

Jens has also imported Metro Vancouver data on land use. This is sometimes different from how the land is zoned - it shows how the land is actually being used, not what's allowed. Some older properties may have grandfathered noncompliant uses.

You can filter for specific land use codes with the `lu` filter, or exclude codes with the `nlu` filter.

Here are all lots with "Residential - High-rise Apartment" uses: [https://mountainmath.ca/map/assessment?filter=[**lu_S135**]](https://mountainmath.ca/map/assessment?filter=[lu_S135])

Land use codes:

* S110: "Residential - Single Detached & Duplex"
* S131: "Residential – Townhouse"
* S130: "Residential - Low-rise Apartment"
* S135: "Residential - High-rise Apartment"
* S410: "Residential - Institutional and Non-Market Housing"
* S200: "Commercial"
* S230: "Mixed Residential Commercial - Low-rise Apartment"
* S235: "Mixed Residential Commercial - High-rise Apartment"
* S400: "Institutional"
* A500: "Agriculture"
* S300: "Industrial"
* R100: "Recreation Open Space and Protected Natural Areas"
* S420: "Cemetery"
* U100: "Undeveloped and Unclassified"
* M300: "Industrial – Extractive"
* S120: "Residential – Rural"
* S100: "Residential - Mobile Home Park"
* S700: "Rail Rapid Transit Other Transportation Utility and Communication"
* S600: "Port Metro Vancouver"
* R200: "Lakes Large Rivers and Other Water"
* S500: "Road Right-of-Way"
* W400: "Protected Watershed"
* S650: "Airport/Airstrip"
* F100: "Harvesting and Research"
* J000: "Recent Redeveloped / Misclassified"


### Teardown Coefficient

The "Teardown Coefficient" is [a measure developed to estimate the chance that a building is likely to be torn down](https://doodles.mountainmath.ca/blog/2016/01/18/redevelopment/). Use the `tdc` filter.

This shows all buildings with teardown coefficient between 0.05 and 0.1 (so building value between 5% and 10% of total value): [https://mountainmath.ca/map/assessment?filter=[**tdc_0.05_0.1**]](https://mountainmath.ca/map/assessment?filter=[tdc_0.05_0.1])

### Years

This lets you filter by the year a building was constructed. Look how much the West End grew between 1960 and 1975: [https://mountainmath.ca/map/assessment?filter=[**years_1960_1975**]](https://mountainmath.ca/map/assessment?filter=[years_1960_1975])

### Zone

This lets you view specific zoning districts. If you want to see how many lots are zoned RS-1, Vancouver’s most common “single family”* zoning district: [https://mountainmath.ca/map/assessment?filter=[**zone_RS-1**]](https://mountainmath.ca/map/assessment?filter=[zone_RS-1])

You can specify only the first part of a zoning code if you like. For example, if you want to see all RS lots not just RS-1: [https://mountainmath.ca/map/assessment?filter=[**zone_RS**]](https://mountainmath.ca/map/assessment?filter=[zone_RS])

What if you want everything _but_ a specific district? You can use “nzone” instead of “zone”: [https://mountainmath.ca/map/assessment?filter=[**nzone_RS**]](https://mountainmath.ca/map/assessment?filter=[nzone_RS])

Exact matches can be done using `zoneE`. This will only show RS-1 and exclude, say, RS-1A: [https://mountainmath.ca/map/assessment?filter=[**zoneE_RS-1**]](https://mountainmath.ca/map/assessment?filter=[zoneE_RS-1])

If you want to include multiple zones you can separate them with underscores: [https://mountainmath.ca/map/assessment?filter=[**zone_RT-1_RT-5**]](https://mountainmath.ca/map/assessment?filter=[zone_RT-1_RT-5])



<sub>*I'm very aware that most RS lots can now have up to 3 suites (1 main, secondary, 1 laneway house). But it's hard to describe that succinctly, and even the City of Vancouver still calls RS "One-Family Districts" and state that a major goal is to retain their "single-family residential character".</sub>
