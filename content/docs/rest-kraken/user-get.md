---
title: Users - Get
layout: docs
weight : 49
menu: 
  docs:
    parent: API - Kraken
---

#  Get Users

## Description

Gets a list of specified user objects.

*This is a legacy method which is still included, because helix does not provide the user creation date yet.*

## Method Definition

```java
@RequestLine("GET /users?login={logins}")
@Headers({
	"Accept: application/vnd.twitchtv.v5+json"
})
HystrixCommand<KrakenUserList> getUsersByLogin(
	@Param("logins") List<String> logins	
);
```

*Required Parameters*

| Name          | Type      | Description  |
| ------------- |:---------:| -----------------:|
| logins | text | User login name (lower case channelname/username). Multiple login names can be specified. Limit: 100. |

None

*Optional Parameters*

None

## Code-Snippets

### get information about a single user

{{<codeblocks>}}
{{<code Java>}}
```java
KrakenUserList resultList = twitchClient.getKraken().getUsersByLogin(Arrays.asList("twitch4j")).execute();
```
{{</code>}}
{{<code Groovy>}}
```groovy
def resultList = twitchClient.kraken.getUsersByLogin(["twitch4j"]).execute()
```
{{</code>}}
{{<code Kotlin>}}
```kotlin
val resultList = twitchClient.kraken.getUsersByLogin(listOf("twitch4j")).execute()
```
{{</code>}}
{{</codeblocks>}}
