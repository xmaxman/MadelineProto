---
title: messages.getAllDrafts
description: messages.getAllDrafts parameters, return type and example
---
## Method: messages.getAllDrafts  
[Back to methods index](index.md)




### Return type: [Updates](../types/Updates.md)

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

$Updates = $MadelineProto->messages->getAllDrafts();
```

Or, if you're into Lua:

```
Updates = messages.getAllDrafts({})
```

