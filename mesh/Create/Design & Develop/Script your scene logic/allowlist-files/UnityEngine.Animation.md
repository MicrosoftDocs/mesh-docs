# UnityEngine\.Animation

## Scene

### UnityEngine\.Animator

Interface to control the Mecanim animation system\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`GetBool`|`name` string|bool|Returns the value of the given boolean parameter\.|Animator \| Get Bool
|`GetFloat`|`name` string|float|Returns the value of the given float parameter\.|Animator \| Get Float
|`GetInteger`|`name` string|int|Returns the value of the given integer parameter\.|Animator \| Get Integer
|`ResetTrigger`|`name` string|void|Resets the value of the given trigger parameter\.|Animator \| Reset Trigger
|`SetBool`|`name` string<br>`value` bool|void|Sets the value of the given boolean parameter\.|Animator \| Set Bool
|`SetFloat`|`name` string<br>`value` float|void|Send float values to the Animator to affect transitions\.|Animator \| Set Float
|`SetFloat`|`name` string<br>`value` float<br>`dampTime` float<br>`deltaTime` float|void|Send float values to the Animator to affect transitions\.|Animator \| Set Float
|`SetInteger`|`name` string<br>`value` int|void|Sets the value of the given integer parameter\.|Animator \| Set Integer
|`SetTrigger`|`name` string|void|Sets the value of the given trigger parameter\.|Animator \| Set Trigger

