# API Estimate Fare For All Suppliers

Used to estimate the fare for all Suppliers who provide the service

> POST /api/paymentgateway/estimateFareWithAllSupliers  

- `Role: dispatcher`

## Request Entity

| Attribute        | Type                | Description                                                                     | Values                                                                                                                                   |
|------------------|---------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| `fleetId`          | String              | Id of fleet, provided by QUp                                                    |                                                                                                                                          |
| `distance`         | Double              | Estimate distance calculated by Google API <br>Required if bookType = 0/1/2 |                                                                                                                                          |
| `vehicleTypeId`    | UUID String         | Id of vehicle type                                                              |                                                                                                                                          |
| `zipCodeFrom`      | String              | Zip code of pickup address                                                      |                                                                                                                                          |
| `zipCodeTo`        | String              | Zip code of destination address                                                 |                                                                                                                                          |
| `duration`         | Double              | Estimate duration calculated by Google API <br>Required if bookType = 0/1/2 |                                                                                                                                          |
| `pickup`           | List<Double>        | Geo location of pickup address                                                  |                                                                                                                                          |
| `destination`      | List<Double>        | Geo location of destination address <br>Required if bookType = 0/1/2        |                                                                                                                                          |
| `bookFrom`         | String              | Indicate the component is requesting the booking                                | - Fix value: CC, API, Car-hailing, Web booking, Partner, mDispatcher, Kiosk, webBooking, partner <br>- Pax app name (ex: uride, oneride, ....) |
| `bookType`         | Integer             | Type of the booking                                                             | 0 - one way <br>1 - from airport <br>2 - to airport <br>3 - hourly <br>4 - round trip                                    |
| `pickupTime`       | String              | Pickup time                                                                     | - Now <br>- Revervation <br>- Datetime in format yyyy-MM-dd HH:mm                                                                |
| `meetDriver`       | Integer             | Request driver to reach customer at pickup point                                | - 1 - NA <br>0 - on curb <br>1 - meet driver                                                                                     |
| `userId`           | UUID String         | Id of customer                                                                  |                                                                                                                                          |
| `city`             | String              | City name of destination address                                                |                                                                                                                                          |
| `timezone`         | String              | Timezone of destination address                                                 |                                                                                                                                          |
| `tip`              | Double              | Tip amount                                                                      |                                                                                                                                          |
| `promoCode`        | String              | Promotion code which is applied on the booking                                  |                                                                                                                                          |
| `phone`            | String              | Phone number of customer                                                        |                                                                                                                                          |
| `actualFare`       | Integer             | Indicate to use actual fare                                                     | 0: use estimate fare <br>1: use actual fare                                                                                          |
| `corporateId`      | UUID String         | Id of corporate in case booking for corporate traveller                         |                                                                                                                                          |
| `packageRateId`    | UUID String         | Required if bookType = 3                                                        |                                                                                                                                          |
| `pricingType`      | Integer             | Indicate a booking is local or affiliate                                        | 0: local booking <br>1: affiliate booking                                                                                            |
| `typeRate`         | Integer             | Type of Rate                                                                    | 0 - Regular <br>  <br>1 - Hourly <br>2 - Round trip <br>3 - Intercity <br>                                                       |
| `services`         | List<String>        | Additional services                                                             |                                                                                                                                          |
| `rv`               | String              | Revision of Driver app                                                          |                                                                                                                                          |
| `extraDestination` | List<ExtraLocation> | List of [ExtraLocation](#extralocation)                                                           |                                                                                                                                          |
| `rateDetails`      | List<RateDetails>   | List of [RateDetails](#ratedetails)                                                             |                                                                                                                                          |
| `zoneId`           | UUID String         | Id of destination zone                                                          |                                                                                                                                          |
| `suplierFleetId`   | String              | Id of supplier fleet, provided by QUp                                           |                                                                                                                                          |
| `supliers`         | List<String>        | List of suppliers                                                               |                                                                                                                                          |
| `pegasus`          | Boolean             | Booking requested from Pegasus app                                              |                                                                                                                                          |
| `seat`             | Integer             | Number of seat                                                                  |                                                                                                                                          |
| `luggage`          | Integer             | Number of luggate                                                               |                                                                                                                                          |
| `intercityRouteId` | UUID String         | Id of intercity route                                                           |                                                                                                                                          |
| `routeNumber`      | Integer             | Indicate the number of intercity route                                          | 1 - round 1 <br>2 - round 2 
                                                                                    |

## Response Entity


## Example Request
```json
{
  
}
```

## Example Response
```json
{
  
}
```