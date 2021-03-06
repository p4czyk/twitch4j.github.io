---
title: Topic - Commerce Events
layout: docs
weight: 50
menu: 
  docs:
    parent: PubSub
---

# Topic - Commerce Events

## Description

This topic is deprecated by Twitch, but it could be used to monitor purchases in a specified channel. 

## Method Definition

*Required Parameters*

| Name          | Type      | Description  |
| ------------- |:---------:| -----------------:|
| credential | OAuth2Credential | User Auth Token for the target channel id, with any scope |
| channelId | String | Target Channel Id |

*Optional Parameters*

None

## Code-Snippets

Subscribe to all commerce purchases in the twitch4j channel and register a listener that prints all messages to console

{{<codeblocks>}}
{{<code Java>}}
```java
twitchClient.getPubSub().listenForCommerceEvents(credential, "149223493");

twitchClient.getEventManager().onEvent(ChannelCommerceEvent.class, System.out::println);
```
{{</code>}}
{{<code Groovy>}}
```groovy
twitchClient.pubSub.listenForCommerceEvents(credential, "149223493");

twitchClient.eventManager.onEvent(ChannelCommerceEvent, System.out::println)
```
{{</code>}}
{{<code Kotlin>}}
```kotlin
twitchClient.pubSub.listenForCommerceEvents(credential, "149223493");

twitchClient.eventManager.onEvent(ChannelCommerceEvent::class.java, System.out::println)
```
{{</code>}}
{{</codeblocks>}}
