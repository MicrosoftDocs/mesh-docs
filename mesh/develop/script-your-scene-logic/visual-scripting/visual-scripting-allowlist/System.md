# System

## Structs

### bool



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`FalseString`|string|yes|no|Boolean \| Get False String
|`TrueString`|string|yes|no|Boolean \| Get True String

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Equals`|`obj` bool|bool|Boolean \| Equals
|`Parse`|`value` string|bool|Boolean \| Parse

### char



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`MaxValue`|char|yes|no|Character \| Get Max Value
|`MinValue`|char|yes|no|Character \| Get Min Value

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Equals`|`obj` char|bool|Character \| Equals
|`IsControl`|`c` char|bool|Character \| Is Control
|`IsDigit`|`c` char|bool|Character \| Is Digit
|`IsLetter`|`c` char|bool|Character \| Is Letter
|`IsLetterOrDigit`|`c` char|bool|Character \| Is Letter Or Digit
|`IsLower`|`c` char|bool|Character \| Is Lower
|`IsNumber`|`c` char|bool|Character \| Is Number
|`IsPunctuation`|`c` char|bool|Character \| Is Punctuation
|`IsSeparator`|`c` char|bool|Character \| Is Separator
|`IsSymbol`|`c` char|bool|Character \| Is Symbol
|`IsUpper`|`c` char|bool|Character \| Is Upper
|`IsWhiteSpace`|`c` char|bool|Character \| Is White Space
|`ToLower`|`c` char|char|Character \| To Lower
|`ToLowerInvariant`|`c` char|char|Character \| To Lower Invariant
|`ToUpper`|`c` char|char|Character \| To Upper
|`ToUpperInvariant`|`c` char|char|Character \| To Upper Invariant

### double



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`MaxValue`|double|yes|no|Double \| Get Max Value
|`MinValue`|double|yes|no|Double \| Get Min Value
|`NaN`|double|yes|no|Double \| Get Na N
|`NegativeInfinity`|double|yes|no|Double \| Get Negative Infinity
|`PositiveInfinity`|double|yes|no|Double \| Get Positive Infinity

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`IsFinite`|`d` double|bool|Double \| Is Finite
|`IsInfinity`|`d` double|bool|Double \| Is Infinity
|`IsNaN`|`d` double|bool|Double \| Is NaN
|`IsNegative`|`d` double|bool|Double \| Is Negative
|`IsNegativeInfinity`|`d` double|bool|Double \| Is Negative Infinity
|`IsNormal`|`d` double|bool|Double \| Is Normal
|`IsPositiveInfinity`|`d` double|bool|Double \| Is Positive Infinity
|`Parse`|`s` string|double|Double \| Parse

### float



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`Epsilon`|float|yes|no|Float \| Get Epsilon
|`MaxValue`|float|yes|no|Float \| Get Max Value
|`MinValue`|float|yes|no|Float \| Get Min Value
|`NaN`|float|yes|no|Float \| Get Na N
|`NegativeInfinity`|float|yes|no|Float \| Get Negative Infinity
|`PositiveInfinity`|float|yes|no|Float \| Get Positive Infinity

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Equals`|`obj` float|bool|Float \| Equals
|`IsFinite`|`f` float|bool|Float \| Is Finite
|`IsInfinity`|`f` float|bool|Float \| Is Infinity
|`IsNaN`|`f` float|bool|Float \| Is NaN
|`IsNegative`|`f` float|bool|Float \| Is Negative
|`IsNegativeInfinity`|`f` float|bool|Float \| Is Negative Infinity
|`IsNormal`|`f` float|bool|Float \| Is Normal
|`IsPositiveInfinity`|`f` float|bool|Float \| Is Positive Infinity
|`IsSubnormal`|`f` float|bool|Float \| Is Subnormal
|`Parse`|`s` string|float|Float \| Parse

### int



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`MaxValue`|int|yes|no|Integer \| Get Max Value
|`MinValue`|int|yes|no|Integer \| Get Min Value

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Equals`|`obj` int|bool|Integer \| Equals
|`Parse`|`s` string|int|Integer \| Parse

### System\.DateTime



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`Date`|System\.DateTime|yes|no|Date Time \| Get Date
|`Day`|int|yes|no|Date Time \| Get Day
|`DayOfWeek`|System\.DayOfWeek|yes|no|Date Time \| Get Day Of Week
|`DayOfYear`|int|yes|no|Date Time \| Get Day Of Year
|`Hour`|int|yes|no|Date Time \| Get Hour
|`Kind`|System\.DateTimeKind|yes|no|Date Time \| Get Kind
|`Millisecond`|int|yes|no|Date Time \| Get Millisecond
|`Minute`|int|yes|no|Date Time \| Get Minute
|`Month`|int|yes|no|Date Time \| Get Month
|`Now`|System\.DateTime|yes|no|Date Time \| Get Now
|`Second`|int|yes|no|Date Time \| Get Second
|`Today`|System\.DateTime|yes|no|Date Time \| Get Today
|`UTCNow`|System\.DateTime|yes|no|Date Time \| Get UTC Now

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`DateTime`|`year` int<br>`month` int<br>`day` int|System\.DateTime|Date Time \| Create Date Time
|`DateTime`|`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int|System\.DateTime|Date Time \| Create Date Time
|`DateTime`|`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`millisecond` int|System\.DateTime|Date Time \| Create Date Time
|`DateTime`|`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`millisecond` int<br>`kind` System\.DateTimeKind|System\.DateTime|Date Time \| Create Date Time
|`DateTime`|`year` int<br>`month` int<br>`day` int<br>`hour` int<br>`minute` int<br>`second` int<br>`kind` System\.DateTimeKind|System\.DateTime|Date Time \| Create Date Time
|`AddMonths`|`months` int|System\.DateTime|Date Time \| Add Months
|`AddYears`|`value` int|System\.DateTime|Date Time \| Add Years
|`Compare`|`t1` System\.DateTime<br>`t2` System\.DateTime|int|Date Time \| Compare
|`DaysInMonth`|`year` int<br>`month` int|int|Date Time \| Days In Month
|`Equals`|`t1` System\.DateTime<br>`t2` System\.DateTime|bool|Date Time \| Equals
|`IsDaylightSavingTime`||bool|Date Time \| Is Daylight Saving Time
|`IsLeapYear`|`year` int|bool|Date Time \| Is Leap Year
|`Parse`|`s` string|System\.DateTime|Date Time \| Parse
|`SpecifyKind`|`value` System\.DateTime<br>`kind` System\.DateTimeKind|System\.DateTime|Date Time \| Specify Kind
|`Subtract`|`value` System\.DateTime|System\.TimeSpan|Date Time \| Subtract
|`Subtract`|`value` System\.TimeSpan|System\.DateTime|Date Time \| Subtract
|`ToLocalTime`||System\.DateTime|Date Time \| To Local Time
|`ToLongDateString`||string|Date Time \| To Long Date String
|`ToLongTimeString`||string|Date Time \| To Long Time String
|`ToShortDateString`||string|Date Time \| To Short Date String
|`ToShortTimeString`||string|Date Time \| To Short Time String
|`ToString`|`format` string|string|Date Time \| To String
|`ToUniversalTime`||System\.DateTime|Date Time \| To Universal Time

### System\.DateTimeOffset



| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Subtract`|`value` System\.DateTimeOffset|System\.TimeSpan|Date Time Offset \| Subtract
|`Subtract`|`value` System\.TimeSpan|System\.DateTimeOffset|Date Time Offset \| Subtract

### System\.TimeSpan



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`TotalSeconds`|double|yes|no|Time Span \| Get Total Seconds

## Other

### object



### string



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`Empty`|string|yes|no|String \| Get Empty
|`Length`|int|yes|no|String \| Get Length

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`string`|`c` char<br>`count` int|string|String \| Create String
|`Compare`|`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int|int|String \| Compare
|`Compare`|`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int<br>`ignoreCase` bool|int|String \| Compare
|`Compare`|`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int<br>`comparisonType` System\.StringComparison|int|String \| Compare
|`Compare`|`strA` string<br>`strB` string|int|String \| Compare
|`Compare`|`strA` string<br>`strB` string<br>`ignoreCase` bool|int|String \| Compare
|`Compare`|`strA` string<br>`strB` string<br>`comparisonType` System\.StringComparison|int|String \| Compare
|`CompareOrdinal`|`strA` string<br>`indexA` int<br>`strB` string<br>`indexB` int<br>`length` int|int|String \| Compare Ordinal
|`CompareOrdinal`|`strA` string<br>`strB` string|int|String \| Compare Ordinal
|`Concat`|`arg0` object|string|String \| Concat
|`Concat`|`arg0` object<br>`arg1` object|string|String \| Concat
|`Concat`|`arg0` object<br>`arg1` object<br>`arg2` object|string|String \| Concat
|`Concat`|`arg0` object<br>`arg1` object<br>`arg2` object<br>`arg3` object|string|String \| Concat
|`Concat`|`str0` string<br>`str1` string|string|String \| Concat
|`Concat`|`str0` string<br>`str1` string<br>`str2` string|string|String \| Concat
|`Concat`|`str0` string<br>`str1` string<br>`str2` string<br>`str3` string|string|String \| Concat
|`Contains`|`value` string|bool|String \| Contains
|`Contains`|`value` string<br>`comparisonType` System\.StringComparison|bool|String \| Contains
|`EndsWith`|`value` string|bool|String \| Ends With
|`EndsWith`|`value` string<br>`comparisonType` System\.StringComparison|bool|String \| Ends With
|`Equals`|`value` string|bool|String \| Equals
|`Equals`|`a` string<br>`b` string|bool|String \| Equals
|`Equals`|`a` string<br>`b` string<br>`comparisonType` System\.StringComparison|bool|String \| Equals
|`Equals`|`value` string<br>`comparisonType` System\.StringComparison|bool|String \| Equals
|`Format`|`format` string<br>`arg0` object|string|String \| Format
|`Format`|`format` string<br>`arg0` object<br>`arg1` object|string|String \| Format
|`Format`|`format` string<br>`arg0` object<br>`arg1` object<br>`arg2` object|string|String \| Format
|`GetHashCode`|`comparisonType` System\.StringComparison|int|String \| Get Hash Code
|`IndexOf`|`value` string|int|String \| Index Of
|`IndexOf`|`value` string<br>`startIndex` int|int|String \| Index Of
|`IndexOf`|`value` string<br>`startIndex` int<br>`count` int|int|String \| Index Of
|`IndexOf`|`value` string<br>`startIndex` int<br>`count` int<br>`comparisonType` System\.StringComparison|int|String \| Index Of
|`IndexOf`|`value` string<br>`startIndex` int<br>`comparisonType` System\.StringComparison|int|String \| Index Of
|`IndexOf`|`value` string<br>`comparisonType` System\.StringComparison|int|String \| Index Of
|`Insert`|`startIndex` int<br>`value` string|string|String \| Insert
|`IsNullOrEmpty`|`value` string|bool|String \| Is Null Or Empty
|`IsNullOrWhiteSpace`|`value` string|bool|String \| Is Null Or White Space
|`LastIndexOf`|`value` string|int|String \| Last Index Of
|`LastIndexOf`|`value` string<br>`startIndex` int|int|String \| Last Index Of
|`LastIndexOf`|`value` string<br>`startIndex` int<br>`count` int|int|String \| Last Index Of
|`LastIndexOf`|`value` string<br>`startIndex` int<br>`count` int<br>`comparisonType` System\.StringComparison|int|String \| Last Index Of
|`LastIndexOf`|`value` string<br>`startIndex` int<br>`comparisonType` System\.StringComparison|int|String \| Last Index Of
|`LastIndexOf`|`value` string<br>`comparisonType` System\.StringComparison|int|String \| Last Index Of
|`PadLeft`|`totalWidth` int|string|String \| Pad Left
|`PadRight`|`totalWidth` int|string|String \| Pad Right
|`Remove`|`startIndex` int|string|String \| Remove
|`Remove`|`startIndex` int<br>`count` int|string|String \| Remove
|`Replace`|`oldValue` string<br>`newValue` string|string|String \| Replace
|`Replace`|`oldValue` string<br>`newValue` string<br>`comparisonType` System\.StringComparison|string|String \| Replace
|`StartsWith`|`value` string|bool|String \| Starts With
|`StartsWith`|`value` string<br>`comparisonType` System\.StringComparison|bool|String \| Starts With
|`Substring`|`startIndex` int|string|String \| Substring
|`Substring`|`startIndex` int<br>`length` int|string|String \| Substring
|`ToLower`||string|String \| To Lower
|`ToLowerInvariant`||string|String \| To Lower Invariant
|`ToUpper`||string|String \| To Upper
|`ToUpperInvariant`||string|String \| To Upper Invariant
|`Trim`||string|String \| Trim
|`TrimEnd`||string|String \| Trim End
|`TrimStart`||string|String \| Trim Start

### System\.TimeZoneInfo



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`DaylightName`|string|yes|no|Time Zone Info \| Get Daylight Name
|`DisplayName`|string|yes|no|Time Zone Info \| Get Display Name
|`Id`|string|yes|no|Time Zone Info \| Get Id
|`Local`|System\.TimeZoneInfo|yes|no|Time Zone Info \| Get Local
|`StandardName`|string|yes|no|Time Zone Info \| Get Standard Name
|`SupportsDaylightSavingTime`|bool|yes|no|Time Zone Info \| Get Supports Daylight Saving Time
|`UTC`|System\.TimeZoneInfo|yes|no|Time Zone Info \| Get UTC

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`ConvertTime`|`dateTime` System\.DateTime<br>`destinationTimeZone` System\.TimeZoneInfo|System\.DateTime|Time Zone Info \| Convert Time
|`ConvertTime`|`dateTime` System\.DateTime<br>`sourceTimeZone` System\.TimeZoneInfo<br>`destinationTimeZone` System\.TimeZoneInfo|System\.DateTime|Time Zone Info \| Convert Time
|`ConvertTimeBySystemTimeZoneId`|`dateTime` System\.DateTime<br>`destinationTimeZoneId` string|System\.DateTime|Time Zone Info \| Convert Time By System Time Zone ID
|`ConvertTimeBySystemTimeZoneId`|`dateTime` System\.DateTime<br>`sourceTimeZoneId` string<br>`destinationTimeZoneId` string|System\.DateTime|Time Zone Info \| Convert Time By System Time Zone ID
|`ConvertTimeFromUTC`|`dateTime` System\.DateTime<br>`destinationTimeZone` System\.TimeZoneInfo|System\.DateTime|Time Zone Info \| Convert Time From UTC
|`ConvertTimeToUTC`|`dateTime` System\.DateTime|System\.DateTime|Time Zone Info \| Convert Time To UTC
|`ConvertTimeToUTC`|`dateTime` System\.DateTime<br>`sourceTimeZone` System\.TimeZoneInfo|System\.DateTime|Time Zone Info \| Convert Time To UTC
|`FindSystemTimeZoneById`|`id` string|System\.TimeZoneInfo|Time Zone Info \| Find System Time Zone By ID
|`FromSerializedString`|`source` string|System\.TimeZoneInfo|Time Zone Info \| From Serialized String
|`HasSameRules`|`other` System\.TimeZoneInfo|bool|Time Zone Info \| Has Same Rules
|`IsAmbiguousTime`|`dateTime` System\.DateTime|bool|Time Zone Info \| Is Ambiguous Time
|`IsDaylightSavingTime`|`dateTime` System\.DateTime|bool|Time Zone Info \| Is Daylight Saving Time
|`IsInvalidTime`|`dateTime` System\.DateTime|bool|Time Zone Info \| Is Invalid Time

### System\.Type



### System\.Uri



| Property | Type | Read? | Write? | Script |
|----------|------|:-----:|:------:|--------|
|`AbsolutePath`|string|yes|no|Uri \| Get Absolute Path
|`AbsoluteUri`|string|yes|no|Uri \| Get Absolute Uri
|`Authority`|string|yes|no|Uri \| Get Authority
|`Fragment`|string|yes|no|Uri \| Get Fragment
|`Host`|string|yes|no|Uri \| Get Host
|`IsAbsoluteUri`|bool|yes|no|Uri \| Is Absolute Uri
|`PathAndQuery`|string|yes|no|Uri \| Get Path And Query
|`Port`|int|yes|no|Uri \| Get Port
|`Query`|string|yes|no|Uri \| Get Query
|`Scheme`|string|yes|no|Uri \| Get Scheme
|`UserInfo`|string|yes|no|Uri \| Get User Info

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`Uri`|`uriString` string|System\.Uri|Uri \| Create Uri
|`Uri`|`baseUri` System\.Uri<br>`relativeUri` string|System\.Uri|Uri \| Create Uri
|`EscapeDataString`|`stringToEscape` string|string|Uri \| Escape Data String
|`IsBaseOf`|`uri` System\.Uri|bool|Uri \| Is Base Of
|`UnescapeDataString`|`stringToUnescape` string|string|Uri \| Unescape Data String

## Enums

### System\.DateTimeKind



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Unspecified`|0
|`Utc`|1
|`Local`|2
### System\.DayOfWeek



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
### System\.StringComparison



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
