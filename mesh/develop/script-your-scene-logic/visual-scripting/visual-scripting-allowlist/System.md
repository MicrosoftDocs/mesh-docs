# System

## Structs

### [bool](https://learn.microsoft.com/en-us/dotnet/api/system.boolean?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Boolean \| Get False String |string|yes|no|
| Boolean \| Get True String |string|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Boolean \| Equals |`obj` bool|bool|
| Boolean \| Parse |`value` string|bool|

### [char](https://learn.microsoft.com/en-us/dotnet/api/system.char?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Character \| Get Max Value |char|yes|no|
| Character \| Get Min Value |char|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Character \| Equals |`obj` char|bool|
| Character \| Is Control |`c` char|bool|
| Character \| Is Digit |`c` char|bool|
| Character \| Is Letter |`c` char|bool|
| Character \| Is Letter Or Digit |`c` char|bool|
| Character \| Is Lower |`c` char|bool|
| Character \| Is Number |`c` char|bool|
| Character \| Is Punctuation |`c` char|bool|
| Character \| Is Separator |`c` char|bool|
| Character \| Is Symbol |`c` char|bool|
| Character \| Is Upper |`c` char|bool|
| Character \| Is White Space |`c` char|bool|
| Character \| To Lower |`c` char|char|
| Character \| To Lower Invariant |`c` char|char|
| Character \| To Upper |`c` char|char|
| Character \| To Upper Invariant |`c` char|char|

 ### [double([_______](https://learn.microsoft.com/en-us/dotnet/api/system.double?view=net-8.0))



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Double \| Get Max Value |double|yes|no|
| Double \| Get Min Value |double|yes|no|
| Double \| Get Na N |double|yes|no|
| Double \| Get Negative Infinity |double|yes|no|
| Double \| Get Positive Infinity |double|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Double \| Is Finite |`d` double|bool|
| Double \| Is Infinity |`d` double|bool|
| Double \| Is NaN |`d` double|bool|
| Double \| Is Negative |`d` double|bool|
| Double \| Is Negative Infinity |`d` double|bool|
| Double \| Is Normal |`d` double|bool|
| Double \| Is Positive Infinity |`d` double|bool|
| Double \| Parse |`s` string|double|

 ### [float](https://learn.microsoft.com/en-us/dotnet/api/system.single?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Float \| Get Epsilon |float|yes|no|
| Float \| Get Max Value |float|yes|no|
| Float \| Get Min Value |float|yes|no|
| Float \| Get Na N |float|yes|no|
| Float \| Get Negative Infinity |float|yes|no|
| Float \| Get Positive Infinity |float|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Float \| Equals |`obj` float|bool|
| Float \| Is Finite |`f` float|bool||`f` float|bool|Float \| Is Infinity
| Float \| Is NaN |`f` float|bool|
| Float \| Is Negative |`f` float|bool|
| Float \| Is Negative Infinity |`f` float|bool|
| Float \| Is Normal |`f` float|bool|
| Float \| Is Positive Infinity |`f` float|bool|
| Float \| Is Subnormal |`f` float|bool|
| Float \| Parse |`s` string|float|

 ### [int](https://learn.microsoft.com/en-us/dotnet/api/system.int32?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Integer \| Get Max Value |int|yes|no|
| Integer \| Get Min Value |int|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Integer \| Equals |`obj` int|bool|
| Integer \| Parse |`s` string|int|

 ### [DateTime](https://learn.microsoft.com/en-us/dotnet/api/system.datetime?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Date Time \| Get Date |DateTime|yes|no|
| Date Time \| Get Day |int|yes|no|
| Date Time \| Get Day Of Week |DayOfWeek|yes|no|
| Date Time \| Get Day Of Year |int|yes|no|
| Date Time \| Get Hour |int|yes|no|
| Date Time \| Get Kind |DateTimeKind|yes|no|
| Date Time \| Get Millisecond |int|yes|no|
| Date Time \| Get Minute |int|yes|no|
| Date Time \| Get Month |int|yes|no|
| Date Time \| Get Now |DateTime|yes|no|
| Date Time \| Get Second |int|yes|no|
| Date Time \| Get Today |DateTime|yes|no|
| Date Time \| Get UTC Now |DateTime|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Date Time \| Create Date Time |`year` int<br>`month` int<br>`day` int|DateTime|
| Date Time \| Create Date Time |`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int|DateTime|
| Date Time \| Create Date Time q|`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`millisecond` int|DateTime|
| Date Time \| Create Date Time |`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`millisecond` int<br>`kind` DateTimeKind|DateTime|
| Date Time \| Create Date Time |`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`kind` DateTimeKind|DateTime|
| Date Time \| Add Months |`months` int|DateTime|
| Date Time \| Add Years |`value` int|DateTime|
| Date Time \| Compare |`t1` DateTime<br>`t2` DateTime|int|
|`DaysInMonth`|`year` int<br>`month` int|int|Date Time \| Days In Month
| Date Time \| Equals |`t1` DateTime<br>`t2` DateTime|bool|
| Date Time \| Is Daylight Saving Time ||bool|
| Date Time \| Is Leap Year |`year` int|bool|
| Date Time \| Parse |`s` string|DateTime|
| Date Time \| Specify Kind |`value` DateTime<br>`kind` DateTimeKind|DateTime|
| Date Time \| Subtract |`value` DateTime|TimeSpan|
| Date Time \| Subtract |`value` TimeSpan|DateTime|
| Date Time \| To Local Time ||DateTime|
| Date Time \| To Long Date String ||string|
| Date Time \| To Long Time String ||string|
| Date Time \| To Short Date String ||string|
| Date Time \| To Short Time String ||string|
| Date Time \| To String |`format` string|string|
| Date Time \| To Universal Time ||DateTime|

 ### [DateTimeOffset([_______](https://learn.microsoft.com/en-us/dotnet/api/system.datetimeoffset?view=net-8.0))



| Node | Inputs | Outputs |
|--------|------------|---------|
| Date Time Offset \| Subtract |`value` DateTimeOffset|TimeSpan|
| Date Time Offset \| Subtract |`value` TimeSpan|DateTimeOffset|

 ### [TimeSpan](https://learn.microsoft.com/en-us/dotnet/api/system.timespan?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
|`TotalSeconds`|double|yes|no|Time Span \| Get Total Seconds

## Other

 ### [object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-8.0)



 ### [string](https://learn.microsoft.com/en-us/dotnet/api/system.string?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| String \| Get Empty |string|yes|no|
| String \| Get Length |int|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| String \| Create String |`c` char<br>`count` int|string|
| String \| Compare |`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int|int|
| String \| Compare |`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int<br>`ignoreCase` bool|int|
| String \| Compare |`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int<br>`comparisonType` StringComparison|int|
| String \| Compare |`strA` string<br>`strB` string|int|
| String \| Compare |`strA` string<br>`strB` string<br>`ignoreCase` bool|int|
| String \| Compare |`strA` string<br>`strB` string<br>`comparisonType` StringComparison|int|
| String \| Compare Ordinal |`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int|int|
| String \| Compare Ordinal |`strA` string<br>`strB` string|int|
| String \| Concat |`arg0` object|string|
| String \| Concat |`arg0` object<br>`arg1` object|string|
| String \| Concat |`arg0` object<br>`arg1` object<br>`arg2` object|string|
| String \| Concat |`arg0` object<br>`arg1` object<br>`arg2` object<br>`arg3` object|string|
| String \| Concat |`str0` string<br>`str1` string|string|
| String \| Concat |`str0` string<br>`str1` string<br>`str2` string|string|
| String \| Concat |`str0` string<br>`str1` string<br>`str2` string<br>`str3` string|string|
| String \| Contains |`value` string|bool|
| String \| Contains |`value` string<br>`comparisonType` StringComparison|bool|
| String \| Ends With |`value` string|bool|
| String \| Ends With |`value` string<br>`comparisonType` StringComparison|bool|
| String \| Equals |`value` string|bool|
| String \| Equals |`a` string<br>`b` string|bool|
| String \| Equals |`a` string<br>`b` string<br>`comparisonType` StringComparison|bool|
| String \| Equals |`value` string<br>`comparisonType` StringComparison|bool|
| String \| Format |`format` string<br>`arg0` object|string|
| String \| Format |`format` string<br>`arg0` object<br>`arg1` object|string|
| String \| Format |`format` string<br>`arg0` object<br>`arg1` object<br>`arg2` object|string|
| String \| Get Hash Code |`comparisonType` StringComparison|int|
| String \| Index Of |`value` string|int|
| String \| Index Of |`value` string<br>`startIndex` int|int|
| String \| Index Of |`value` string<br>`startIndex` int<br>`count` int|int|
| String \| Index Of |`value` string<br>`startIndex` int<br>`count` int<br>`comparisonType` StringComparison|int|
| String \| Index Of |`value` string<br>`startIndex` int<br>`comparisonType` StringComparison|int|
| String \| Index Of |`value` string<br>`comparisonType` StringComparison|int|
| String \| Insert |`startIndex` int<br>`value` string|string|
| String \| Is Null Or Empty |`value` string|bool|
| String \| Is Null Or White Space |`value` string|bool|
| String \| Last Index Of |`value` string|int|
| String \| Last Index Of |`value` string<br>`startIndex` int|int|
| String \| Last Index Of |`value` string<br>`startIndex` int<br>`count` int|int|
| String \| Last Index Of |`value` string<br>`startIndex` int<br>`count` int<br>`comparisonType` StringComparison|int|
| String \| Last Index Of |`value` string<br>`startIndex` int<br>`comparisonType` StringComparison|int|
| String \| Last Index Of |`value` string<br>`comparisonType` StringComparison|int|
| String \| Pad Left |`totalWidth` int|string|
| String \| Pad Right |`totalWidth` int|string|
| String \| Remove |`startIndex` int|string|
| String \| Remove |`startIndex` int<br>`count` int|string|
| String \| Replace |`oldValue` string<br>`newValue` string|string|
| String \| Replace |`oldValue` string<br>`newValue` string<br>`comparisonType` StringComparison|string|
| String \| Starts With |`value` string|bool|
| String \| Starts With |`value` string<br>`comparisonType` StringComparison|bool|
| String \| Substring |`startIndex` int|string|
| String \| Substring |`startIndex` int<br>`length` int|string|
|`ToLower`||string|String \| To Lower
| String \| To Lower Invariant ||string|
| String \| To Upper ||string|
| String \| To Upper Invariant ||string|
| String \| Trim ||string|
| String \| Trim End ||string|
| String \| Trim Start ||string|

 ### [TimeZoneInfo](https://learn.microsoft.com/en-us/dotnet/api/system.timezoneinfo?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Time Zone Info \| Get Daylight Name |string|yes|no|
| Time Zone Info \| Get Display Name |string|yes|no|
| Time Zone Info \| Get Id |string|yes|no|
| Time Zone Info \| Get Local |TimeZoneInfo|yes|no|
| Time Zone Info \| Get Standard Name |string|yes|no|
| Time Zone Info \| Get Supports Daylight Saving Time |bool|yes|no|
| Time Zone Info \| Get UTC |TimeZoneInfo|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Time Zone Info \| Convert Time |`dateTime` DateTime<br>`destinationTimeZone` TimeZoneInfo|DateTime|
| Time Zone Info \| Convert Time |`dateTime` DateTime<br>`sourceTimeZone` TimeZoneInfo<br>`destinationTimeZone` TimeZoneInfo|DateTime|
| Time Zone Info \| Convert Time By System Time Zone ID |`dateTime` DateTime<br>`destinationTimeZoneId` string|DateTime|
| Time Zone Info \| Convert Time By System Time Zone ID |`dateTime` DateTime<br>`sourceTimeZoneId` string<br>`destinationTimeZoneId` string|DateTime|
| Time Zone Info \| Convert Time From UTC |`dateTime` DateTime<br>`destinationTimeZone` TimeZoneInfo|DateTime|
| Time Zone Info \| Convert Time To UTC |`dateTime` DateTime|DateTime|
| Time Zone Info \| Convert Time To UTC |`dateTime` DateTime<br>`sourceTimeZone` TimeZoneInfo|DateTime|
| Time Zone Info \| Find System Time Zone By ID |`id` string|TimeZoneInfo|
| Time Zone Info \| From Serialized String |`source` string|TimeZoneInfo|
| Time Zone Info \| Has Same Rules |`other` TimeZoneInfo|bool|
| Time Zone Info \| Is Ambiguous Time |`dateTime` DateTime|bool|
| Time Zone Info \| Is Daylight Saving Time |`dateTime` DateTime|bool|
| Time Zone Info \| Is Invalid Time |`dateTime` DateTime|bool|

 ### [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-8.0)



 ### [Uri](https://learn.microsoft.com/en-us/dotnet/api/system.uri?view=net-8.0)



| Property | Type | Read? | Write? |
|----------|------|:-----:|:------:|
| Uri \| Get Absolute Path |string|yes|no|
| Uri \| Get Absolute Uri |string|yes|no|
| Uri \| Get Authority |string|yes|no|
| Uri \| Get Fragment |string|yes|no|
| Uri \| Get Host |string|yes|no|
| Uri \| Is Absolute Uri |bool|yes|no|
| Uri \| Get Path And Query |string|yes|no|
| Uri \| Get Port |int|yes|no|
| Uri \| Get Query |string|yes|no|
| Uri \| Get Scheme |string|yes|no|
| Uri \| Get User Info |string|yes|no|

| Node | Inputs | Outputs |
|--------|------------|---------|
| Uri \| Create Uri |`uriString` string|Uri|
| Uri \| Create Uri |`baseUri` Uri<br>`relativeUri` string|Uri|
| Uri \| Escape Data String |`stringToEscape` string|string|
| Uri \| Is Base Of |`uri` Uri|bool|
| Uri \| Unescape Data String |`stringToUnescape` string|string|

## Enums

 ### [DateTimeKind](https://learn.microsoft.com/en-us/dotnet/api/system.datetimekind?view=net-8.0)



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Unspecified`|0
|`Utc`|1
|`Local`|2

 ### [DayOfWeek](https://learn.microsoft.com/en-us/dotnet/api/system.dayofweek?view=net-8.0)



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Sunday`|0
|`Monday`|1
|`Tuesday`|2
|`Wednesday`|3
|`Thursday`|4
|`Friday`|5
|`Saturday`|6

 ### [StringComparison](https://learn.microsoft.com/en-us/dotnet/api/system.stringcomparison?view=net-8.0)



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`CurrentCulture`|0
|`CurrentCultureIgnoreCase`|1
|`InvariantCulture`|2
|`InvariantCultureIgnoreCase`|3
|`Ordinal`|4
|`OrdinalIgnoreCase`|5
