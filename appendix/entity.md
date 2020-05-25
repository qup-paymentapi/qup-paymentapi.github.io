# Request Emtity

## RateDetails Entity

| Attribute          | Type                | Description                                                                     | Values                                                                                |
|--------------------|---------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|
| `distance`         | Double              | Estimate distance calculated by Google API <br><br>Required if bookType = 0/1/2 |                                                                                       |
| `vehicleTypeId`    | UUID String         | Id of vehicle type                                                              |                                                                                       |
| `duration`         | Double              | Estimate duration calculated by Google API <br><br>Required if bookType = 0/1/2 |                                                                                       |
| `bookType`         | Integer             | Type of the booking                                                             | 0 - one way <br>1 - from airport <br>2 - to airport <br>3 - hourly <br>4 - round trip |
| `pickupTime`       | String              | Pickup time                                                                     | - Now <br>- Revervation <br>- Datetime in format yyyy-MM-dd HH:mm                     |
| `packageRateId`    | UUID String         | Required if bookType = 3                                                        |                                                                                       |
| `typeRate`         | Integer             | Type of Rate                                                                    | 0 - Regular <br>1 - Hourly <br>2 - Round trip <br>3 - Intercity                       |
| `services`         | List<String>        | Additional services                                                             |                                                                                       |
| `extraDestination` | List<ExtraLocation> | List of [ExtraLocation](appendix/entity.md?id=extralocation-entity)                                                           |                                                                                       |
| `seat`             | Integer             | Number of seat                                                                  |                                                                                       |
| `luggage`          | Integer             | Number of luggate                                                               |                                                                                       |
| `intercityRouteId` | UUID String         | Id of intercity route                                                           |                                                                                       |
| `routeNumber`      | Integer             | Indicate the number of intercity route                                          | 1 - round 1 <br>2 - round 2                                                           |

## ExtraLocation Entity

| Attribute   | Type         | Description                                |
|-------------|--------------|--------------------------------------------|
| `geo`       | List<Double> | Geo location of destination address        |
| `zipCode`   | String       | Zip code of destination address            |
| `distance`  | Double       | Estimate distance calculated by Google API |
| `duration`  | Double       | Estimate duration calculated by Google API |
