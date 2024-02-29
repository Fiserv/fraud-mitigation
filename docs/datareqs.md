# Data Integration

___

Provide the most relevant attributes for the most accurate fraud score.

---

## Customer Profile

Platforms are customer centric, decisions are made on the likelihood of this consumer committing fraud on this event. As such accurate customer information is essential.

- Customer ID
- Customer Name
- Email Address
- Phone Number
- Customer Address

```json
{
    "customerExtId": "1029384756",
    "customerName": "John Doe",
    "email": "john.doe@emailjohn.net",
    "customerPhoneNumber": "5550000000",
    "customerStreet": "0 Main Street",
    "customerCity": "Mitigation",
    "customerStateOrProvince": "UT",
    "customerCountry": "USA",
    "customerPostalCode": "11111"
}
```

---

## Order Information

Order details allow identification of high-risk delivery and store addresses, as well as high-risk products (i.e., gift cards) that are included in basket. 

- Order ID
- Price and Currency
- Delivery Address
- Basket Details
- Store Address

```json
{
    "orderNumber": "0192837465",
    "total": 100,
    "currency": "USD",
    "shippingStreet": "0 Main Street",
    "shippingCity": "Mitigation",
    "shippingStateOrProvince": "UT",
    "shippingCountry": "USA",
    "shippingPostalCode": "11111",
    "shippingType": "SD",
    "shippingItems": [
        {
            "name": "Football",
            "type": "Sports",
            "description": "Football",
            "quantity": 1,
            "price": 75,
            "currency": "USD"
        },
        {
            "name": "Baseball",
            "type": "Sports",
            "description": "Baseball",
            "quantity": 1,
            "price": 25,
            "currency": "USD"
        }
    ],
    "merchantStreet": "0 Main Blvd",
    "merchantCity": "Detection",
    "merchantStateOrProvince": "UT",
    "merchantCountry": "USA",
    "merchantPostalCode": "22222"
}
```

---

## Payment Information

Payment method information is essential in fraud prevention as it is the means of committing fraud. Full billing data allows identification of high-risk names and addresses.

- Card Number
- Billing Name
- Billing Address
- Card Expiration
- Payment Type (Card/Wallet)

```json
{
    "encryptedCard": "000111000111",
    "billingName": "Jane Doe",
    "billingStreet": "0 Main Street",
    "billingCity": "Mitigation",
    "bilingStateOrProvince": "UT",
    "billingCountry": "USA",
    "billingPostalCode": "11111",
    "cardExpiryMonth": 10,
    "cardExpiryYear": 2099,
    "paymentType": "PaymentCard"
}
```

---

## Device Information

Tying a consumer to a device allows for more accurate identification of a specific entity. Device data also allows accurate detection of the location from which an order is placed.

- Device ID
- IP Address
- User Agent
- Model and Manufacturer
- Location

```json
{
    "deviceId": "rvnand-4-EAF7B6C9RB",
    "ipAddress": "111.000.11.00",
    "deviceUserAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_2) AppleWebKit/601.3.9 (KHTML, like Gecko) Version/9.0.2 Safari/601.3)",
    "deviceModel": "Retina",
    "deviceManufacturer": "Intel",
    "deviceLat": 11.11,
    "deviceLong": 11.11,
    "deviceCity": "Dallas",
    "deviceStateOrProvince": "TX",
    "deviceCountry": "USA"
}
```

---

## Transaction Information

Transaction details change across the lifecycle (pre-auth/post-auth) of an order allowing the Fraud Engine to understand issuer declines, failed 3DS, etc.

- Transaction ID
- Price and Currency
- Transaction Type
- Issuer Response
- AVS/CVV Response

```json
{
    "clientRequestId": "5fcd13e2ec114c58b5216c542a4ce4d7",
    "total": 100,
    "currency": "USD",
    "transactionType": "CHARGE_SALE",
    "declineNotification": false,
    "avsCode": "X",
    "securityResponseCode": "V",
    "scheme": "VISA"
}
```

---

## Dispute Information

Dispute information provides known/confirmed fraud cases to the Fraud Engine on the day the dispute is raised. This allows immediate response to emerging fraud trends.

- Dispute ID
- Dispute Date
- Dispute Reason
- Dispute Status
- Order ID Disputed






