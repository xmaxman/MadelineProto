---
title: searchPublicChats
description: Searches public chats by prefix of their username. Currently only private and channel (including supergroup) chats can be public. Returns meaningful number of results. Returns nothing if length of the searched username prefix is less than 5. Excludes private chats with contacts from the results
---
## Method: searchPublicChats  
[Back to methods index](index.md)


Searches public chats by prefix of their username. Currently only private and channel (including supergroup) chats can be public. Returns meaningful number of results. Returns nothing if length of the searched username prefix is less than 5. Excludes private chats with contacts from the results

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|username\_prefix|[string](../types/string.md) | Yes|Prefix of the username to search|


### Return type: [Chats](../types/Chats.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $this->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Chats = $MadelineProto->searchPublicChats(['username_prefix' => string, ]);
```

Or, if you're into Lua:

```
Chats = searchPublicChats({username_prefix=string, })
```

