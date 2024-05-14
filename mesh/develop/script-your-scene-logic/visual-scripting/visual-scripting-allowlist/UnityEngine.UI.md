# UnityEngine\.UI

## Scene

### UnityEngine\.UI\.Graphic



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | Script |
|----------|------|:-----:|:------:|:------:|--------|
|`color`|UnityEngine\.Color|yes|yes|yes|Graphic \| Get Color<br>Graphic \| Set Color
|`material`|UnityEngine\.Material|yes|yes|no|Graphic \| Get Material<br>Graphic \| Set Material

### UnityEngine\.UI\.Image



Supports additional properties and methods from UnityEngine\.UI\.Graphic, UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Read? | Write? | Share? | Script |
|----------|------|:-----:|:------:|:------:|--------|
|`fillAmount`|float|yes|yes|yes|Image \| Get Fill Amount<br>Image \| Set Fill Amount
|`material`|UnityEngine\.Material|yes|yes|no|Image \| Get Material<br>Image \| Set Material
|`type`|UnityEngine\.UI\.Image\.Type|yes|yes|no|Image \| Get Type<br>Image \| Set Type

## Enums

### UnityEngine\.UI\.Image\.Type



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Simple`|0
|`Sliced`|1
|`Tiled`|2
|`Filled`|3
