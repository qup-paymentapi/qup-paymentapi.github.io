# API Add Ticket

Add new ticket into MySQL after complete a trip

> **POST /api/paymentgateway/addTicket**

- `Role: dispatcher`

## Request Entity

| Attribute      | Type   | Description                                   |
|----------------|--------|-----------------------------------------------|
| `fleetId`      | String | Id of fleet, provided by QUp                  |
| `bookId`       | String | Id of booking                                 |
| `distanceGG`   | Double | Distance calculated by Google API        		|
| `distanceTour` | Double | Distance calculated by GPS of the device 		|

## Response Entity


## Example Request
```json
{
  "fleetId":"trabi",
  "bookId":"5990165",  
  "distanceGG":11333,
  "distanceTour":0.5769957304000854
}
```

## Example Response
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