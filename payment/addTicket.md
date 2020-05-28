# API Add Ticket

Add new ticket into MySQL after complete a trip

## HTTP Request
<!-- panels:start -->

<!-- panels:title-panel -->

> POST /api/paymentgateway/addTicket

- `Role: dispatcher`

<!-- div:left-panel -->

| Attribute      | Type   | Description                                   |
|----------------|--------|-----------------------------------------------|
| `fleetId`      | String | Id of fleet, provided by QUp                  |
| `bookId`       | String | Id of booking                                 |
| `distanceGG`   | Double | Distance calculated by Google API        		  |
| `distanceTour` | Double | Distance calculated by GPS of the device 		  |

<!-- div:right-panel -->

```json
{
  "fleetId":"trabi",
  "bookId":"5990165",  
  "distanceGG":11333,
  "distanceTour":0.5769957304000854
}
```
<!-- panels:end -->

## HTTP Response

<!-- panels:start -->

<!-- div:left-panel -->

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

| Attribute                        | Type        | Description                                                                                                         |
|----------------------------------|-------------|---------------------------------------------------------------------------------------------------------------------|
| `actualFare`                     | Boolean     | Indicate to use actual fare                                                                                         |
| `addNote`                        | Boolean     | Allow to add note                                                                                                   |
| `additionalServices`             | Array       | Additional services                                                                                                 |
| `airportActive`                  | Boolean     | Indicate airport fee is active                                                                                      |
| `airportSurcharge`               | Double      | Airport fee                                                                                                         |
| `approvalCode`                   | String      | Approval code from payment gateway                                                                                  |
| `authAmount`                     | Double      | Authorized amount, in case using pre-authorization flow                                                             |
| `avatar`                         | String      | Driver avatar                                                                                                       |
| `avis3rd`                        | Boolean     | Indicate booking from avís 3rd                                                                                      |
| `bookFrom`                       | String      | Indicate which component requested booking                                                                          |
| `bookId`                         | String      | Booking ID                                                                                                          |
| `bookingFee`                     | Double      | Booking fee                                                                                                         |
| `bookingFeeActive`               | Integer     | Indicate booking fee is active. <br>Values: 0/1                                                                     |
| `bookingFeeType`                 | String      | Indicate booking fee type. <br>Values: amount/percent                                                               |
| `calBasicFare`                   | Double      | Calculated base fare                                                                                                |
| `carTypeService`                 | String      | Vehicle type service                                                                                                |
| `cardType`                       | String      | Card type. <br>Values: Visa/Master                                                                                  |
| `commissionType`                 | String      | Indicate commission type. <br>Values: amount/percent                                                                |
| `commissionValue`                | Double      | Commission value                                                                                                    |
| `completedTime`                  | String      | Completed time in case booking was completed. <br>Format yyyy-MM-dd'T'HH:mm:ss.SSSZ                                 |
| `corporateId`                    | UUID String | Corporate ID                                                                                                        |
| `couponType`                     | String      | Indicate promotion type. <br>Values: amount/percent                                                                 |
| `couponValue`                    | Double      | Promotion value                                                                                                     |
| `creditInfo`                     | Json String | Credit card which used to pay for the booking. <br>Includes: card mask, card type, cardholder, payment gateway name |
| `currencyISO`                    | String      | Currency ISO on the request                                                                                         |
| `currencyISOCharged`             | String      | Currency ISO used to charge for the booking                                                                         |
| `currencySymbol`                 | String      | Currency symbol on the request                                                                                      |
| `currencySymbolCharged`          | String      | Currency symbol used to charge for the booking                                                                      |
| `customerId`                     | UUID String | Customer ID                                                                                                         |
| `customerName`                   | String      | Customer full name                                                                                                  |
| `destination`                    | String      | Destination address                                                                                                 |
| `distanceTour`                   | Double      | Distance calculated by GPS                                                                                          |
| `driverId`                       | UUID String | Driver ID                                                                                                           |
| `driverName`                     | String      | Driver full name                                                                                                    |
| `dynamicFare`                    | Double      | Dynamic fare                                                                                                        |
| `dynamicSurcharge`               | Double      | Dynamic surcharge                                                                                                   |
| `editBasicFare`                  | Boolean     | Allow driver to edit base fare                                                                                      |
| `editOtherFees`                  | Boolean     | Allow driver to edit other fee                                                                                      |
| `editTax`                        | Boolean     | Allow driver to edit tax                                                                                            |
| `editTip: false,`                | Boolean     | Allow driver to edit tip                                                                                            |
| `exchangeRate`                   | Double      | Exchange rate, in case request currency and charge currency is different                                            |
| `fare`                           | Double      | Base fare                                                                                                           |
| `fleetId`                        | String      | Fleet ID                                                                                                            |
| `heavyTraffic`                   | Double      | Heavy traffic                                                                                                       |
| `heavyTrafficActive`             | Boolean     | Indicate heavy traffic is active                                                                                    |
| `hideFare`                       | Boolean     | Hide fare on the client                                                                                             |
| `id`                             | Long        | Ticket ID                                                                                                           |
| `isMinimum`                      | Integer     | Indicate minimum fare is available. <br>Values: 0/1                                                                 |
| `isPending`                      | Boolean     | Indicate whether booking complete in pending                                                                        |
| `mDispatcherCommission`          | Double      | mDispatcher commisson value                                                                                         |
| `mDispatcherId`                  | UUID String | mDispatcher ID                                                                                                      |
| `meetDriverActive`               | Boolean     | Indicate meet driver is active                                                                                      |
| `meetDriverFee`                  | Double      | Meet driver fee                                                                                                     |
| `minimum`                        | Double      | Minimum value                                                                                                       |
| `oldBasicFare`                   | Double      | Original estimate base fare                                                                                         |
| `otherFeeActive`                 | Boolean     | Indicate other fee is active                                                                                        |
| `otherFeeDriverCanInput`         | Double      | Maximum value of other fee can input by driver                                                                      |
| `otherFeeLimitDriverInputActive` | Boolean     | Limit the maximum value of other fee can input by driver                                                            |
| `otherFees`                      | Double      | Other fees                                                                                                          |
| `otherFeesDetails`               | String      | Detail of other fees                                                                                                |
| `paidBy`                         | String      | Payment method                                                                                                      |
| `partnerCommission`              | Double      | Booking fee                                                                                                         |
| `passengerAvatar`                | String      | Customer avatar                                                                                                     |
| `paymentStatus`                  | String      | Payment status                                                                                                      |
| `paymentTime`                    | String      | Payment time in case booking was completed. <br>Format yyyy-MM-dd'T'HH:mm:ss.SSSZ                                   |
| `paymentType`                    | Integer     | Requested payment type                                                                                              |
| `pickup`                         | String      | Pickup address                                                                                                      |
| `pickupTime`                     | String      | Pickup time in format yyyy-MM-dd'T'HH:mm:ss.SSSZ                                                                    |
| `plateNumber`                    | String      | Plate number                                                                                                        |
| `pricingType`                    | Integer     | Indicate whether this is local booking. <br>Values: 0/1                                                             |
| `promoAmount`                    | Double      | Promotion amount                                                                                                    |
| `promoCode`                      | String      | Promotion code                                                                                                      |
| `psgEmail`                       | String      | Customer email                                                                                                      |
| `psgFleetId`                     | String      | Fleet ID of customer                                                                                                |
| `rating`                         | Boolean     | Force to rate for the booking                                                                                       |
| `receiptComment`                 | String      | Booking note                                                                                                        |
| `rideSharing`                    | Boolean     | Indicate whether this is ride sharing booking                                                                       |
| `rushHour`                       | Double      | Surcharge fee                                                                                                       |
| `rushHourActive`                 | Boolean     | Indicate surcharge is active                                                                                        |
| `serviceActive`                  | Boolean     | Indicate additional service is active                                                                               |
| `serviceFee`                     | Double      | Additional service fee                                                                                              |
| `status`                         | Integer     | Ticket status. <br>Values: 0/1                                                                                      |
| `subTotal`                       | Double      | Sub total                                                                                                           |
| `subTotalCharged`                | Double      | Subtotal was charged                                                                                                |
| `subTotalExchange`               | Double      | Subtotal exchanged                                                                                                  |
| `surchargeFee`                   | Double      | Surcharge fee setting                                                                                               |
| `surchargeParameter`             | Double      | Dynamic surcharge setting value                                                                                     |
| `surchargeType`                  | String      | Dynamic surcharge type. <br>Values: amount/percent                                                                  |
| `tax`                            | Double      | Tax fee                                                                                                             |
| `taxActive`                      | Boolean     | Indicate tax fee is active                                                                                          |
| `taxFee`                         | Double      | Tax fee                                                                                                             |
| `taxValue`                       | Double      | Tax value setting                                                                                                   |
| `techFee`                        | Double      | Tech fee                                                                                                            |
| `techFeeActive`                  | Boolean     | Indicate tech fee is active                                                                                         |
| `techFeeType`                    | String      | Tech fee type. <br>Values: amount/percent                                                                           |
| `techFeeValue`                   | Double      | Tech fee value setting                                                                                              |
| `timeZoneDestination`            | String      | Timezone of destination address                                                                                     |
| `tip`                            | Double      | Tip fee                                                                                                             |
| `tipActive`                      | Boolean     | Indicate tip is active                                                                                              |
| `tipAfterPayment`                | String      | Tip after ride                                                                                                      |
| `tipFee`                         | Double      | Tip fee                                                                                                             |
| `token`                          | String      | Credit token in case pay by stored card                                                                             |
| `tollFee`                        | Double      | Toll fee                                                                                                            |
| `tollFeeActive`                  | Boolean     | Indicate toll fee is active                                                                                         |
| `tollFeeDriverCanInput`          | Double      | Maximum value of toll fee can input by driver                                                                       |
| `tollFeeLimitDriverInputActive`  | Boolean     | Limit the maximum value of toll fee can input by driver                                                             |
| `total`                          | Double      | Total fare                                                                                                          |
| `totalCharged`                   | Double      | Total charged amount                                                                                                |
| `totalExchange`                  | Double      | Total exchanged                                                                                                     |
| `totalFare`                      | Double      | Total without promo amount                                                                                          |
| `trackingLog`                    | Boolean     | is tracking log                                                                                                     |
| `transactionStatus`              | String      | Transaction status                                                                                                  |
| `travellerSignature`             | Boolean     | Need traveller to sign after the trip                                                                               |
| `unroundedTotalAmt`              | Double      | Unrounded total                                                                                                     |
| `vehicleType`                    | String      | Car type name                                                                                                       |

<!-- div:right-panel -->

```json
{
  "returnCode": 200,
  "response": {
    "actualFare": true,
    "addNote": false,
    "additionalServices": [],
    "airportActive": false,
    "airportSurcharge": 0,
    "approvalCode": "",
    "authAmount": 0,
    "avatar": "images/avatar/avatarDefault.png",
    "avis3rd": false,
    "bookFrom": "CC",
    "bookId": "5990165",
    "bookingFee": 0,
    "bookingFeeActive": 0,
    "calBasicFare": 0,
    "carTypeService": "rideHailing",
    "cardType": "",
    "commissionType": "amount",
    "commissionValue": 0,
    "corporateId": "",
    "couponType": "amount",
    "couponValue": 0,
    "creditInfo": {
      "cardMask": "",
      "cardType": "",
      "cardHolder": "",
      "gateway": ""
    },
    "currencyISO": "RON",
    "currencyISOCharged": "RON",
    "currencySymbol": "leu",
    "currencySymbolCharged": "leu",
    "customerId": "",
    "customerName": "paul ",
    "destination": "Strada Tomis 11, Dej 405200",
    "distanceTour": 11333,
    "driverId": "5ec002619ef8c75afe385ec3",
    "driverName": "Ind.166 Domnar Nelu",
    "dynamicFare": 0,
    "dynamicSurcharge": 0,
    "editBasicFare": false,
    "editOtherFees": false,
    "editTax": false,
    "editTip": false,
    "exchangeRate": 0,
    "fare": 0,
    "fleetId": "trabi",
    "heavyTraffic": 0,
    "heavyTrafficActive": false,
    "hideFare": false,
    "id": 5186300,
    "isMinimum": 0,
    "isPending": false,
    "mDispatcherCommission": 0,
    "mDispatcherId": "",
    "meetDriverActive": true,
    "meetDriverFee": 0,
    "minimum": 0,
    "oldBasicFare": 0,
    "otherFeeActive": false,
    "otherFeeDriverCanInput": 0,
    "otherFeeLimitDriverInputActive": false,
    "otherFees": 0,
    "otherFeesDetails": "",
    "partnerCommission": 0,
    "passengerAvatar": "",
    "paymentStatus": "full",
    "paymentType": 1,
    "pickup": "Cetan, Romania",
    "pickupTime": "2020-05-23T02:25:18.000Z",
    "plateNumber": "CJ60DAA",
    "pricingType": 0,
    "promoAmount": 0,
    "promoCode": "",
    "psgEmail": "",
    "psgFleetId": "trabi",
    "qrImage": "",
    "qrName": "",
    "rating": false,
    "receiptComment": "numar 221 dupa cimitir",
    "rideSharing": false,
    "rushHour": 0,
    "rushHourActive": false,
    "serviceActive": false,
    "serviceFee": 0,
    "status": 0,
    "subTotal": 0,
    "subTotalCharged": 0,
    "subTotalExchange": 0,
    "surchargeFee": 0,
    "surchargeParameter": 0,
    "surchargeType": "amount",
    "tax": 0,
    "taxActive": false,
    "taxFee": 0,
    "taxValue": 0,
    "techFee": 0,
    "techFeeActive": true,
    "techFeeType": "amount",
    "techFeeValue": 0,
    "timeZoneDestination": "Europe/Bucharest",
    "tip": 0,
    "tipActive": false,
    "tipAfterPayment": "",
    "tipFee": 0,
    "token": "",
    "tollFee": 0,
    "tollFeeActive": false,
    "tollFeeDriverCanInput": 0,
    "tollFeeLimitDriverInputActive": false,
    "total": 0,
    "totalCharged": 0,
    "totalExchange": 0,
    "totalFare": 0,
    "trackingLog": false,
    "transactionStatus": "",
    "travellerSignature": false,
    "unroundedTotalAmt": 0,
    "vehicleType": "Numerar"
  }
}
```
<!-- panels:end -->
