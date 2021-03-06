---
title: setBotUpdatesStatus
description: Bots only. Informs server about number of pending bot updates if they aren't processed for a long time
---
## Method: setBotUpdatesStatus  
[Back to methods index](index.md)


Bots only. Informs server about number of pending bot updates if they aren't processed for a long time

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|pending\_update\_count|[int](../types/int.md) | Yes|Number of pending updates|
|error\_message|[string](../types/string.md) | Yes|Last error's message|


### Return type: [Ok](../types/Ok.md)

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

$Ok = $MadelineProto->setBotUpdatesStatus(['pending_update_count' => int, 'error_message' => string, ]);
```

Or, if you're into Lua:

```
Ok = setBotUpdatesStatus({pending_update_count=int, error_message=string, })
```

