---
description: Submit custom events to track referee actions and reward affiliates.
---

# API Events

You can send custom events to ShareMint using our API.

These events are associated with referees and are used to reward affiliates.

For example, if you have a web3 game, and your game has a breeding event, you can reward an affiliate that invites a user to the game that breeds at least 5 times. To determine whether the conditions have been completed, you would send a breed event to our API each time the user breeds. One we recieve 5 breed events, the affiliate reward will be unlocked.

To add an API Event requirement, navigate to your project's settings page. In the _Affiliates_ section, click on _Advanced Referee Requirements_, and choose _API Event_ as the requirement type.

You will be asked to fill in the following fields:

* **Event Name** - the name of the event. This must match the event name sent via API.
* **What is the minimum value required to be considered a referral?** - This is a numeric value threshold above which an affiliate is considered to be valid. You can leave this blank or set it to 0 if you'd like to allow any value.

<figure><img src="../../.gitbook/assets/CleanShot 2023-06-23 at 17.52.35@2x.png" alt=""><figcaption><p>Example using API Event</p></figcaption></figure>

### API

Send events using our API:

{% swagger method="post" path="/api/external/save-event" baseUrl="https://sharemint.xyz" summary="To save custom events." %}
{% swagger-description %}
One of 

`address`

, 

`email`

, or 

`projectUserId`

 must be provided, otherwise, the request will not be processed.
{% endswagger-description %}

{% swagger-parameter in="body" name="slug" required="true" type="String" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" required="true" type="String" %}
Find this on the admin tab of your project
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" type="String" %}
Event name that should match an event name used for requirements on the project Settings page.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="value" type="Number" %}
A custom value for the event.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" %}
The address of the user that performed the event.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" %}
The email of the user that performed the event.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="projectUserId" type="String" %}
The ShareMint id of the user that performed the event.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByCode" type="String" %}
The referral code of the referrer that invited the user. This will usually be blank.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="referredByAddress" type="String" %}
The address of the referrer that invited the user. This will usually be blank.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}

{% endswagger-response %}
{% endswagger %}
