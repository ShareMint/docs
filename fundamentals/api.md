---
description: ShareMint API documentation
---

# 🎍 API

{% swagger method="get" path="/external/user" baseUrl="https://sharemint.xyz/api" summary="Fetch a project user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="slug" required="true" %}
Project slug
{% endswagger-parameter %}

{% swagger-parameter in="query" name="address" required="true" %}
User address or email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="chain" required="true" %}
Blockchain
{% endswagger-parameter %}

{% swagger-parameter in="query" name="apiSecret" %}
Your secret API key from the project admin page
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="/save-event" baseUrl="https://sharemint.xyz/api/external" summary="Save an event" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="slug" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiSecret" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="value" type="Number" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" %}
User address
{% endswagger-parameter %}
{% endswagger %}
