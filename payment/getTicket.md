# API Get Ticket

Get ticket details after payment completed

> POST /api/paymentgateway/getTicket

- `Role: dispatcher`

## Request Entity

| Attribute    | Type   | Description                                   |
|--------------|--------|-----------------------------------------------|
| fleetId      | String | Id of fleet, provided by QUp                  |
| bookId       | String | Id of booking                                 |

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

## Example Request
```json
{
  "fleetId":"uride",
  "bookId":"5987844"
}
```

## Example Response
```json
{
  "returnCode": 200,
  "response": {
    "actualFare": true,
    "addNote": true,
    "additionalServices": [
      {
        "serviceId": "5cc86aaf35789c14051502bf",
        "name": "Insurance Fee",
        "type": "Compulsory",
        "fee": 0.25,
        "active": true
      }
    ],
    "airportActive": true,
    "airportSurcharge": 0,
    "approvalCode": "140815",
    "authAmount": 11.25,
    "avatar": "images/avatar/5e62894ca4371b697197bb30.png",
    "avis3rd": false,
    "bookFrom": "URIDE",
    "bookId": "5987844",
    "bookingFee": 0,
    "bookingFeeActive": 0,
    "bookingFeeType": "amount",
    "calBasicFare": 14.78,
    "carTypeService": "rideHailing",
    "cardType": "",
    "commissionType": "amount",
    "commissionValue": 0,
    "completedTime": "2020-05-21T18:28:15.000Z",
    "corporateId": "",
    "couponType": "amount",
    "couponValue": 0,
    "creditInfo": {
      "cardMask": "XXXXXXXX3459",
      "cardType": "Visa",
      "cardHolder": "Andrée mueller",
      "gateway": "JetPay"
    },
    "currencyISO": "CAD",
    "currencyISOCharged": "CAD",
    "currencySymbol": "$",
    "currencySymbolCharged": "$",
    "customerId": "5b48b0433f208ff961846ce8",
    "customerName": "Andrée  mueller ",
    "destination": "124 Laidlaw Dr, Thunder Bay, ON P7A 7V4",
    "distanceTour": 4053.593873500824,
    "driverId": "5e62894ca4371b697197bb30",
    "driverName": "Assefa Janko",
    "dynamicFare": 0,
    "dynamicSurcharge": 0,
    "editBasicFare": false,
    "editOtherFees": true,
    "editTax": false,
    "editTip": false,
    "exchangeRate": 0,
    "fare": 14.78,
    "fleetId": "uride",
    "heavyTraffic": 0,
    "heavyTrafficActive": false,
    "hideFare": false,
    "id": 5184204,
    "isMinimum": 0,
    "isPending": false,
    "mDispatcherCommission": 0,
    "mDispatcherId": "",
    "meetDriverActive": false,
    "meetDriverFee": 0,
    "minimum": 0,
    "oldBasicFare": 14.78,
    "otherFeeActive": true,
    "otherFeeDriverCanInput": 200,
    "otherFeeLimitDriverInputActive": true,
    "otherFees": 0,
    "otherFeesDetails": "",
    "paidBy": "Personal card",
    "partnerCommission": 0,
    "passengerAvatar": "images/avatar/avatarDefault.png",
    "paymentStatus": "full",
    "paymentTime": "2020-05-21T18:28:15.000Z",
    "paymentType": 1,
    "pickup": "124 Laidlaw Dr, Thunder Bay, ON P7A 7V4",
    "pickupTime": "2020-05-21T17:53:21.000Z",
    "plateNumber": "CKSP 457",
    "pricingType": 0,
    "promoAmount": 0,
    "promoCode": "",
    "psgEmail": "andree-1980@hotmail.com",
    "psgFleetId": "uride",
    "rating": false,
    "receiptComment": "",
    "rideSharing": false,
    "rushHour": 0,
    "rushHourActive": true,
    "serviceActive": true,
    "serviceFee": 0.25,
    "status": 1,
    "subTotal": 15.03,
    "subTotalCharged": 15.03,
    "subTotalExchange": 0,
    "surchargeFee": 0,
    "surchargeParameter": 0,
    "surchargeType": "amount",
    "tax": 0,
    "taxActive": false,
    "taxFee": 0,
    "taxValue": 0,
    "techFee": 3,
    "techFeeActive": true,
    "techFeeType": "amount",
    "techFeeValue": 3,
    "timeZoneDestination": "America/Toronto",
    "tip": 0,
    "tipActive": true,
    "tipAfterPayment": "",
    "tipFee": 0,
    "token": "JJMKBNMHHKJOKMKLHJOLKNIB",
    "tollFee": 0,
    "tollFeeActive": false,
    "tollFeeDriverCanInput": 0,
    "tollFeeLimitDriverInputActive": false,
    "total": 18.03,
    "totalCharged": 18.03,
    "totalExchange": 0,
    "totalFare": 18.03,
    "trackingLog": false,
    "transactionStatus": "credit",
    "travellerSignature": false,
    "unroundedTotalAmt": 18.03,
    "vehicleType": "Car-Ontario"
  }
}
```
