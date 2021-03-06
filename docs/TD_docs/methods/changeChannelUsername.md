---
title: changeChannelUsername
description: Changes username of the channel. Needs creator privileges in the channel
---
## Method: changeChannelUsername  
[Back to methods index](index.md)


Changes username of the channel. Needs creator privileges in the channel

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|channel\_id|[int](../types/int.md) | Yes|Identifier of the channel|
|username|[string](../types/string.md) | Yes|New value of username. Use empty string to remove username|


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

$Ok = $MadelineProto->changeChannelUsername(['channel_id' => int, 'username' => string, ]);
```

Or, if you're into Lua:

```
Ok = changeChannelUsername({channel_id=int, username=string, })
```

