# 💵 Support for fiat payments

ShareMint supports for fiat payments via our API.

To use this feature visit the _Admin_ page of your project. In the section you can get an API access key. This key is secret and allows you to add payments made in fiat.

The API endpoint to add a fiat payment is:

```
POST https://sharemint.xyz/api/external/save-payment
```

With data:

```
slug: string
apiSecret: string
invitedById: string
value: string
quantity?: string
address?: string
email?: string
```

`slug` is the ShareMint project slug.

`apiSecret` can be found on the project's _Admin_ page.

`invitedById` is the referral code of the user that referred this payment.

`value` is the amount paid in US Dollars.

`quantity` is the quantity of items purchased. Optional and defaults to `1`.

`address` is the purchaser's crypto wallet address.

`email` is the purchaser's email address.

One of `address` or `email` is required.
