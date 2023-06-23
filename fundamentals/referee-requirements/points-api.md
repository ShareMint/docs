---
description: >-
  The points API allows you to unlock affiliate rewards based on how many points
  each referee has received.
---

# Points API

You can send points for each user to ShareMint using our API.

These points are associated with referees and are used to reward affiliates.

You can send multiple points for each user. For example, you can send us a score of 100 for fighting, 120 for breeding, and 200 for forging. You can set a requirement that rewards are unlocked if a referee has a score of at least 100 across all three categories.

To add an API Points requirement, navigate to your project's settings page. In the _Affiliates_ section, click on _Advanced Referee Requirements_, and choose _API Points_ as the requirement type.

You will be asked to fill in the following fields:

* **Name** - the name of the key to store the points under. This must match the  name sent via API.
* **What is the minimum value required to be considered a referral?** - This is a numeric value threshold above which an affiliate is considered to be valid. You can leave this blank or set it to 0 if you'd like to allow any value.

In this example, a referee must have a breeding score of at least 5, and a forging score of at least 8:

<figure><img src="../../.gitbook/assets/CleanShot 2023-06-23 at 18.10.48@2x.png" alt=""><figcaption><p>API Points example</p></figcaption></figure>

### API

Send points using our API:

{% swagger method="post" path="/api/external/save-points" baseUrl="https://sharemint.xyz" summary="To save points." %}
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

{% swagger-parameter in="body" name="key" required="true" type="String" %}
The key to store the points under.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="points" type="Number" %}
The number of points the user has total. This will override their previous points score.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="String" %}
The address of the user to store the points for.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" %}
The email of the user to store the points for.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="projectUserId" type="String" %}
The ShareMint id of the user  to store the points for.
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
