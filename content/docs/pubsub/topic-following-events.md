---
title: Topic - Following Events
layout: docs
weight: 50
menu: 
  docs:
    parent: PubSub
---

# Topic - Following Events

## Description

This topic can be used to monitor whenever a specified channel receives followers.

In terms of documented replacements, the User Follows Webhook provides another real-time system to receive these events.
If a webhook server cannot be used, one can also query API Helix > Users Followers at a regular interval to determine new followers. In fact, Twitch4J > Client Helper can do this for you.

With all undocumented topics, use at your own risk.

## Method Definition

| Name          | Type      | Description  |
| ------------- |:---------:| -----------------:|
| credential | OAuth2Credential | Auth Token (may not necessarily be required) |
| channelId | String | Target Channel Id |

## Code-Snippets

Subscribe to new follower events for user twitch4j and register a listener that prints all messages to console

{{<codeblocks>}}
{{<code Java>}}
```java
twitchClient.getPubSub().listenForFollowingEvents(credential, "149223493");

twitchClient.getEventManager().onEvent(FollowingEvent.class, System.out::println);
```
{{</code>}}
{{<code Groovy>}}
```groovy
twitchClient.pubSub.listenForFollowingEvents(credential, "149223493");

twitchClient.eventManager.onEvent(FollowingEvent, System.out::println)
```
{{</code>}}
{{<code Kotlin>}}
```kotlin
twitchClient.pubSub.listenForFollowingEvents(credential, "149223493");

twitchClient.eventManager.onEvent(FollowingEvent::class.java, System.out::println)
```
{{</code>}}
{{</codeblocks>}}
