---
description: ShareMint API documentation
---

# 🎍 API

{% swagger method="get" path="/user" baseUrl="https://sharemint.xyz/api/external" summary="Fetch a project user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="slug" required="true" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="query" name="address" required="true" type="String" %}
User address or email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="chain" required="true" type="String" %}
Blockchain name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="apiSecret" type="String" required="false" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the user" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/address-from-invite-code" baseUrl="https://sharemint.xyz/api/external" summary="Get user address from invite code" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="code" required="true" type="String" %}
User's referral code
{% endswagger-parameter %}

{% swagger-parameter in="query" name="slug" required="true" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the user" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/affiliate" baseUrl="https://sharemint.xyz/api/external" summary="Get affiliate details" %}
{% swagger-description %}
One of address, projectUserId, or referralCode is required.
{% endswagger-description %}

{% swagger-parameter in="query" name="address" type="String" required="false" %}
Affiliate's wallet address
{% endswagger-parameter %}

{% swagger-parameter in="query" name="projectUserId" type="String" required="false" %}
Affiliate's id in project
{% endswagger-parameter %}

{% swagger-parameter in="query" name="referralCode" type="String" required="false" %}
Affiliate's referral code
{% endswagger-parameter %}

{% swagger-parameter in="query" name="slug" required="true" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="query" name="apiSecret" type="String" required="false" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the affiliate details" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/get-or-create-invite-code" baseUrl="https://sharemint.xyz/api/external" summary="Get invite code" %}
{% swagger-description %}
Get an affiliate's invite code. Create it if it doesn't exist.
{% endswagger-description %}

{% swagger-parameter in="body" name="address" required="true" type="String" %}
User's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chain" required="true" type="String" %}
Blockchain name
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the affiliate" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/save" baseUrl="https://sharemint.xyz/api/external" summary="Save a referral via referral id or wallet address" %}
{% swagger-description %}
One of address, email, or transactionHash is required.
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedById" type="String" required="true" %}
The invite code of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedByAddress" type="String" required="false" %}
The address of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" required="false" %}
User's wallet address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" required="false" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionHash" type="String" required="false" %}
Transaction hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chain" type="String" required="false" %}
Chain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="minter" type="String" required="false" %}
One of "payer" or "receiver"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" type="String" required="false" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="verified" type="Boolean" required="false" %}
If the referral is verified. Can only be set when providing an apiSecret
{% endswagger-parameter %}

{% swagger-parameter in="body" name="disqualifiedAsReferee" type="Boolean" %}
If the user is disqualified from being a referee. Can only be set when providing an apiSecret
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the information about the referral" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/save-transaction" baseUrl="https://sharemint.xyz/api/external" summary="Save a referral via a transaction hash" %}
{% swagger-description %}
This saves both the referral and the payment made in the transaction.
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" required="false" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="minter" type="String" required="true" %}
One of "payer" or "receiver"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionHash" type="String" required="true" %}
Transaction hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chain" type="String" required="false" %}
Chain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedById" type="String" required="true" %}
The invite code of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedByAddress" type="String" required="false" %}
The address of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" type="String" required="false" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="verified" type="Boolean" required="false" %}
Is the user verified?
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the information about the referral" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/save-event" baseUrl="https://sharemint.xyz/api/external" summary="Save an event" %}
{% swagger-description %}
One of address, email, or projectUserId is required.
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" required="true" type="String" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" type="String" %}
Name of the event that you set in the project settings
{% endswagger-parameter %}

{% swagger-parameter in="body" name="value" type="Number" required="false" %}
Value of the event
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" required="false" %}
User's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" required="false" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="projectUserId" type="String" required="false" %}
User's id on ShareMint for this project
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByCode" type="String" required="false" %}
The invite code of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByAddress" type="String" required="false" %}
The address of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the created event" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/save-payment" baseUrl="https://sharemint.xyz/api/external" summary="Save payment" %}
{% swagger-description %}
One of address or email is required.
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" required="true" type="String" %}
Your secret API key from the project admin page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedById" required="true" type="String" %}
Referrer's id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="value" required="true" type="String" %}
Payment value. Must be bigger than 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedByAddress" type="String" required="false" %}
Referrer's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="String" required="false" %}
Amount of purchases
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chain" type="String" required="false" %}
Blockchain name. Can be "FIAT", "ETHEREUM", "POLYGON", "ARBITRUM", "OPTIMISM", "SOLANA", "GOERLI", "SEPOLIA"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" required="false" %}
User's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" required="false" %}
User's email
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the id of the user" %}

{% endswagger-response %}
{% endswagger %}
