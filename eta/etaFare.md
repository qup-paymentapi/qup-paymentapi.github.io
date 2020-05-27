# API Estimate Fare Normal

Used to estimate the fare for a normal trip

> POST /api/paymentgateway/estimateFare

- `Role: dispatcher`

## Request Entity

| Attribute          | Type        | Description                                                                 | Values                                                          |
|--------------------|-------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------|
| `actualFare`       | Integer     | Indicate to use actual fare                                                 | 0: use estimate fare <br>1: use actual fare                     |
| `bookFrom`         | String      | Indicate the component is requesting the booking                            | - CC, API, Car-hailing, Kiosk, webBooking, partner <br>- Pax app name (ex: uride, oneride, ....) |
| `bookType`         | Integer     | Type of the booking                                                         | 0 - one way <br>1 - from airport <br>2 - to airport <br>3 - hourly <br>4 - round trip            |
| `city`             | String      | City name of pickup address                                                 |                                                                 |
| `corporateId`      | UUID String | Id of corporate in case booking for corporate traveller                     |                                                                 |
| `destination`      | List        | Geo location of destination address <br>Required if bookType = 0/1/2        |                                                                 |
| `distance`         | Double      | Estimate distance calculated by Google API <br>Required if bookType = 0/1/2 |                                                                 |
| `duration`         | Double      | Estimate duration calculated by Google API <br>Required if bookType = 0/1/2 |                                                                 |
| `extraDestination` | List        | List of [ExtraLocation](eta/resource.md?id=extralocation-entity)            |                                                                 |
| `fleetId`          | String      | Id of fleet, provided by QUp                                                |                                                                 |
| `intercityRouteId` | UUID String | Id of intercity route                                                       |                                                                 |
| `luggage`          | Integer     | Number of luggate <br>Required if typeRate = 3                              |                                                                 |
| `meetDriver`       | Integer     | Request driver to reach customer at pickup point                            | - 1 - NA <br>0 - on curb <br>1 - meet driver                    |
| `packageRateId`    | UUID String | Hourly Package Rate Id <br>Required if typeRate = 1                         |                                                                 |
| `pegasus`          | Boolean     | Booking requested from Pegasus app                                          |                                                                 |
| `phone`            | String      | Phone number of customer                                                    |                                                                 |
| `pickup`           | List        | Geo location of pickup address                                              |                                                                 |
| `pickupTime`       | String      | Pickup time                                                                 | - Now <br>- Revervation <br>- Datetime in format yyyy-MM-dd HH:mm                                |
| `pricingType`      | Integer     | Indicate a booking is local or affiliate                                    | 0: local booking <br>1: affiliate booking                       |
| `promoCode`        | String      | Promotion code which is applied on the booking                              |                                                                 |
| `routeNumber`      | Integer     | Indicate the number of intercity route <br>Required if typeRate = 3         | 1 - round 1 <br>2 - round 2                                     |
| `rv`               | String      | Revision of Driver app                                                      |                                                                 |
| `seat`             | Integer     | Number of seat <br>Required if typeRate = 3                                 |                                                                 |
| `services`         | List        | Additional services                                                         |                                                                 |
| `timezone`         | String      | Timezone of destination address                                             |                                                                 |
| `typeRate`         | Integer     | Type of Rate                                                                | 0 - Regular <br>1 - Hourly <br>2 - Round trip <br>3 - Intercity |
| `userId`           | UUID String | Id of customer                                                              |                                                                 |
| `vehicleTypeId`    | String      | Name of vehicle type                                                        |                                                                 |
| `zipCodeFrom`      | String      | Zip code of pickup address                                                  |                                                                 |
| `zipCodeTo`        | String      | Zip code of destination address                                             |                                                                 |
| `zoneId`           | UUID String | Id of destination zone                                                      |                                                                 |


## Response Entity

| Attribute    | Type    | Description                                  |
|--------------|---------|----------------------------------------------|
| `returnCode` | Inteter | Indicate the result of the request           |
| `response`   | Json    | Json string contains the response attributes |

!> Available Return Code

| Return Code | Description                                              |
|-------------|----------------------------------------------------------|
| `200`       | Success                                                  |
| `406`       | Missing something. Check request values or fleet setting |

!> Response Attributes

| Attribute            | Type    | Description                                                            |
|----------------------|---------|------------------------------------------------------------------------|
| `airportFee`         | Double  | Airport fee                                                            |
| `basicFare`          | Double  | Base fare                                                              |
| `bookingFee`         | Double  | Booking fee                                                            |
| `bookingFeeActive`   | Boolean | Indicate whether booking fee is active                                 |
| `currencyISO`        | String  | Currency code. A 3-letter code of the [International Standard ISO 4217](https://en.wikipedia.org/wiki/ISO_4217). |
| `dynamicFare`        | Double  | Dynamic fare                                                           |
| `dynamicSurcharge`   | Double  | Dynamic surcharge                                                      |
| `etaFare`            | Double  | Total estimated fare                                                   |
| `extraDistanceFee`   | Double  | Extra distance fee                                                     |
| `extraDurationFee`   | Double  | Extra duration fee                                                     |
| `meetDriverFee`      | Double  | Meet driver fee                                                        |
| `min`                | Boolean | Indicate minimum fare is available                                     |
| `minFare`            | Double  | Minimum fare                                                           |
| `normalFare`         | Boolean | Indicate normal fare is available                                      |
| `otherFees`          | Double  | Other fee                                                              |
| `promoAmount`        | Double  | Promotion amount can by applied                                        |
| `promoCode`          | String  | Promotion code                                                         |
| `reverseRoute`       | Boolean | Indicate whether this is a reverse route                               |
| `route`              | String  | Route name                                                             |
| `routeId`            | String  | Route Id                                                               |
| `rushHourFee`        | Double  | Surcharge fee                                                          |
| `serviceFee`         | Double  | Additional service fee                                                 |
| `shortTrip`          | Boolean | Indicate whether this is a short trip                                  |
| `subTotal`           | Double  | Sub total fare                                                         |
| `surchargeParameter` | Double  | Surcharge parameter                                                    |
| `tax`                | Double  | Tax fee                                                                |
| `taxSetting`         | Double  | tax value setting                                                      |
| `taxValue`           | Double  | tax value setting                                                      |
| `techFee`            | Double  | Tech fee                                                               |
| `tip`                | Double  | Tip fee                                                                |
| `tipValue`           | Double  | Tip value setting                                                      |
| `tollFee`            | Double  | Toll fee                                                               |
| `totalWithoutPromo`  | Double  | Total fare without promo                                               |
| `typeRate`           | Double  | Type of rate                                                           |
| `unroundedTotalAmt`  | Double  | Unrounded total fee                                                    |
| `vehicleType`        | String  | Vehicle type name                                                      |

## Example Request
```json
{
  "bookFrom": "URIDE",
  "bookType": 0,
  "city": "P1B 2V2_North Bay_Ontario_Canada",
  "destination": [
    -79.4372222,
    46.3063889
  ],
  "distance": 3578,
  "duration": 422,
  "fleetId": "uride",
  "meetDriver": -1,
  "pegasus": true,
  "phone": "+16473000385",
  "pickup": [
    -79.46784537339585,
    46.31534267700438
  ],
  "pickupTime": "Now",
  "promoCode": "",
  "rv": "4.6.4311",
  "services": [
    "5cc86aaf35789c14051502bf"
  ],
  "tip": 0,
  "typeRate": 0,
  "userId": "5e5052c9ab65637a06be3b48",
  "vehicleTypeId": "Car-Ontario",
  "zipCodeFrom": "P1B 2V2",
  "zipCodeTo": "P1B 9V6",
  "zoneId": "5ce25ab2e4b04ede332f4906"
}
```

## Example Response
```json
{
  "returnCode": 200,
  "response": {
    "airportFee": 0,
    "basicFare": 9.08,
    "bookingFee": 0,
    "bookingFeeActive": false,
    "currencyISO": "CAD",
    "dynamicFare": 0,
    "dynamicSurcharge": 0,
    "etaFare": 12.33,
    "extraDistanceFee": 0,
    "extraDurationFee": 0,
    "meetDriverFee": 0,
    "min": false,
    "minFare": 0,
    "normalFare": true,
    "otherFees": 0,
    "promoAmount": 0,
    "reverseRoute": false,
    "route": "",
    "routeId": "",
    "rushHourFee": 0,
    "serviceFee": 0.25,
    "shortTrip": false,
    "surchargeParameter": 0,
    "tax": 0,
    "taxValue": 0,
    "techFee": 3,
    "tip": 0,
    "tipValue": 0,
    "tollFee": 0,
    "totalWithoutPromo": 12.33,
    "typeRate": 0,
    "unroundedTotalAmt": 12.33,
    "vehicleType": "Car-Ontario"
  }
}
```
