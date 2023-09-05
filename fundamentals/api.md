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

{% swagger-parameter in="query" name="apiSecret" type="String" %}
Your secret API key from the project admin page
{% endswagger-parameter %}
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
{% endswagger %}

{% swagger method="get" path="/affiliate" baseUrl="https://sharemint.xyz/api/external" summary="Get affiliate details" %}
{% swagger-description %}
One of address, projectUserId, or referralCode is required.
{% endswagger-description %}

{% swagger-parameter in="query" name="address" type="String" %}
Affiliate's wallet address
{% endswagger-parameter %}

{% swagger-parameter in="query" name="projectUserId" type="String" %}
Affiliate's id in project
{% endswagger-parameter %}

{% swagger-parameter in="query" name="referralCode" type="String" %}
Affiliate's referral code
{% endswagger-parameter %}

{% swagger-parameter in="query" name="slug" required="true" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="query" name="apiSecret" type="String" %}
Your secret API key from the project admin page
{% endswagger-parameter %}
{% endswagger %}



{% swagger method="post" path="/get-or-create-invite-code" baseUrl="https://sharemint.xyz/api/external" summary="Get an affiliate's invite code. Create it if it doesn't exist" %}
{% swagger-description %}
{% endswagger-description %}

{% swagger-parameter in="body" name="address" required=true type="String" %}
User's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chain" required=true type="String" %}
Blockchain name
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="slug" type="String" %}
Project slug
{% endswagger-parameter %}
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

{% swagger-parameter in="body" name="value" type="Number" %}
Value of the event
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" %}
User's address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="projectUserId" type="String" %}
User's id on ShareMint for this project
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByCode" type="String" %}
The invite code of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByAddress" type="String" %}
The address of the referrer that invited the user
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns the created event" %}

{% endswagger-response %}
{% endswagger %}
