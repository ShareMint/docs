# 🎰 Complex Requirements

The power of our referral platform isn't just in the simple ability to invite others to join your project. It extends to its advanced capabilities, allowing you to track and reward based on various intricate criteria. Our Complex Requirements feature lets you do just that, providing you with the ability to define and monitor sophisticated event sequences.

### What are Complex Requirements?

While simple requirements might only involve the act of inviting a friend to your project and them making a minimum purchase, complex requirements are far more diverse and flexible.

For example, you may want to monitor a smart contract event like staking or trading. But rather than considering the full volume of the trade, you're only interested in a portion of the revenue that the protocol earns. Complex requirements can be set up to capture these more nuanced activities.

Complex requirements can also be API event-driven. That means you can track events in other systems and use those as part of your referral criteria.

<figure><img src="../.gitbook/assets/CleanShot 2023-06-15 at 00.20.12.png" alt=""><figcaption><p>Smart contract events</p></figcaption></figure>

### Setting Eligibility Thresholds

Not only can you monitor a vast range of events, but you can also set thresholds for these events that need to be passed for a referee to be considered eligible. For instance, you could require a user to stake a minimum amount of currency or achieve a particular level in a game.

### Combining Multiple Events

The Complex Requirements feature also enables the combination of multiple events to form a sequence or series of tasks. For instance, you could require a user to unlock five treasure chests, level up three times, and stake 1 ETH. Only when all of these tasks are completed does the referee meet the complex requirement.

<figure><img src="../.gitbook/assets/CleanShot 2023-06-15 at 00.21.52.png" alt=""><figcaption></figcaption></figure>

### API

The API endpoints below are used to save custom events for complex requirements. An example of an event might be "staked", "level-up", "unlocked-chest", "signed-up". You set the events on the project Settings page.

Smart contract events do not need to be sent this way. To track these you can set the details on the project Settings page.

{% swagger method="post" path="/api/external/save-event" baseUrl="https://sharemint.xyz" summary="This endpoint is used to save an event within our system." %}
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

{% swagger-parameter in="body" name="invitedById" type="String" %}
The referral code of the referrer that invited the user. This will usually be blank.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="invitedByAddress" type="String" %}
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
