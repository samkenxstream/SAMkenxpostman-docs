---
title: "FQL function reference"
updated: 2023-03-22
---

All [Flows Query Language](/docs/postman-flows/flows-query-language/introduction-to-fql/) (FQL) functions are documented below.

## Contents

* [General functions](#general-functions)
* [Array functions](#array-functions)
* [Numeric functions](#numeric-functions)
* [Date and time functions](#date-and-time-functions)

## General functions

### assert

Throws an error with the message if a condition is false.

``` javascript
$assert($cond: bool, $msg: string) => error
```

#### Basic usage

``` javascript
$assert(user.age <18, “error:  user cannot vote!”)
```

### average

Returns the average value of a numeric array.

``` javascript
$average($array: array<num>) => number
```

#### Basic usage

``` javascript
$average([1,2,3,4,5]) -> 3
```

### boolean

Casts an argument to its effective boolean value.

``` javascript
$boolean($arg: any) => bool
```

#### Basic usage

``` javascript
$boolean(0) ->  false
$boolean(10) ->  true
$boolean('') ->  false
$boolean('abc') ->  true
```

### contains

Returns true if a string contains a pattern.

``` javascript
$contains($str: string, $pattern: string | regex) => bool
```

#### Basic usage

``` javascript
$contains("hello, world", "lo") -> true
$contains("hello world", "ab") -> false
```

### decodeUrl

Decodes string from a URL.

``` javascript
$decodeUrl($val: string) => string
```

#### Basic usage

``` javascript
$decodeUrl("https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B") -> "https://mozilla.org/?x=шеллы"
```

### decodeUrlComponent

Decodes a string from a component previously created with `encodeUrlComponent`.

``` javascript
$decodeUrlComponent($val: string) => string
```

#### Basic usage

``` javascript
$decodeUrlComponent("%3Fx%3Dtest") -> "?x=test"
```

### each

Applies a function to each key/value pair of an object.

``` javascript
$each($obj: object, func: ($val, $key) : any)
```

#### Basic usage

``` javascript
"Address": {
    "Street": "Hursley Park",
    "City": "Winchester",
    "Postcode": "SO21 2JN"
}
$each(Address, fn($v, $k) {$k & ": " & $v}) ->
 [
        "Street: Hursley Park",
        "City: Winchester",
        "Postcode: SO21 2JN"
 ]
```

### encodeUrl

Encodes a value into a URL.

``` javascript
$encodeUrl($val: string) => string
```

#### Basic usage

``` javascript
$encodeUrl("https://mozilla.org/?x=шеллы") -> "https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B"
```

### encodeUrlComponent

Encodes a value into a component for a URL.

``` javascript
$encodeUrlComponent($val: string) => string
```

#### Basic usage

``` javascript
$encodeUrlComponent("?x=test")  -> "%3Fx%3Dtest"
```

### eval

Evaluates an expression.

``` javascript
$eval($val:string) => any
```

#### Basic usage

``` javascript
$eval('[1,$string(2),3]') -> [1,"2",3]
```

### exists

Returns true if a value is not null or undefined.

``` javascript
$exists($val: any) => bool
```

#### Basic usage

``` javascript
$exists(“hello”) -> true
$exists([1,2,3]) -> true
$exists({“a” : 1, “b”: 2}) -> true
$exists(null) -> false
$exists(blah) -> false
```

### filter

Returns an array of elements which satisfy the predicate defined in a function.

``` javascript
$filter($arr: array, $func: ($e, $index?: number?, $ar: array )=> boolean) => array
```

#### Basic usage

``` javascript
$filter([1,2,3,4,5], fn($e){ $e>3}) -> [4, 5]
```

### join

Joins the elements of an array into a string using the optional separator string.

``` javascript
$join($arr: array<string>, $separator?: string) => string
```

#### Basic usage

``` javascript
$join(["hello", "world"]) -> "helloworld"
$join(["hello", "world"], "-") → "hello-world"
$join([1,2,3], "..") -> "1..2..3"
```

### json

Converts an object to a JSON string.

``` javascript
$json($val:any) => string
```

#### Basic usage

``` javascript
json({'a': 1, 'b' : "hello"}) ->  "{"a":1,"b":"hello"}"
```

### jsonParse

Parses a JSON string into an object.

``` javascript
$jsonParse($val:string) => object
```

#### Basic usage

``` javascript
$jsonParse('{"one": 1, "two": [3, "four"]}') -> {"one": 1,"two": [ 3,"four"]}
```

### keys

Returns an array of the keys in an object.

``` javascript
$keys($obj: object) => array<string>
```

#### Basic usage

``` javascript
"Product": [
    {
        "Product Name": "Bowler Hat",
        "ProductID": 858383,
        "SKU": "0406654608",
        "Description": {
            "Colour": "Purple",
            "Width": 300,
            "Height": 200,
            "Depth": 210,
            "Weight": 0.75
        },
        "Price": 34.45,
        "Quantity": 2
    }
]
$keys(Product) -> ["Product Name","ProductID","SKU","Description","Price","Quantity"]
```

### length

Returns the length of a string.

``` javascript
$length($str: string) => number
```

#### Basic usage

``` javascript
$length(“abc”) -> 3
$length(““) -> 0
```

### lookup

Returns the value of a key in an object.

``` javascript
$lookup($obj: object, $key: string) => any
```

#### Basic usage

``` javascript
($o := { "name" : "John", "email": "john@gmail.com"}; $lookup($o, "name")) -> "John"
```

### lowercase

Returns the lowercase version of a string.

``` javascript
$lowercase($str: string) => string
```

#### Basic usage

``` javascript
$loweCase("Hello World") -> "hello world"
```

### map

Maps each element of an array using a function and returns a new array with all the mapped elements.

``` javascript
$map($arr: array, $func: ($e, $index?: number?, $ar: array ) : array
```

#### Basic usage

``` javascript
$map([1,2,3,4,5], fn($e){ $e *2}) -> [2,4,6,8,10]
```

### max

Returns the maximum value from a numeric array.

``` javascript
$max($array) => number
```

#### Basic usage

``` javascript
$max([9,2,17,3]) -> 17
```

### match

Returns an array of strings that match a pattern.

``` javascript
$match($str: string, $pattern: string | regex) => array<string>
```

#### Basic usage

``` javascript
$match("ababbabbbcc",/a(b+)/) -> ["ab", "abb", "abbb"]
```

### merge

Returns a new object with the properties of each object in an array of objects merged into it.

``` javascript
$merge($arr: array<object>) => object
```

#### Basic usage

``` javascript
$merge([{"a":1},{"b":2}]) -> {"a": 1,"b": 2}
```

### not

Returns true if a value is false, or false otherwise.

``` javascript
$not($x: any) => bool
```

#### Basic usage

``` javascript
$not(true) -> false
$not(false) -> true
$not(null) -> true
$not(0) -> true
$not(100) -> false
$not(““) -> true
$not(“hello”) -> false
```

### pad

Returns a copy of a string padded to a length with $pad (if provided).

``` javascript
$pad($str: string, $length: number, $pad?: string) => string
```

#### Basic usage

``` javascript
$pad("example", 5) -> "example  "
$pad("example", 5, "-") -> "example--"
```

### partition

Partitions an array into an array of arrays of size $n.

``` javascript
$partition($array:any, $n: numbers) => array
```

#### Basic usage

``` javascript
$partition([1,2,3,4,5,6,7,8,9,10], 2) -> [[1,2], [3,4], [5,6], [7,8], [9,10]]
$partition([1,2,3,4,5,6,7,8,9,10], 3) -> [[1,2,3], [4,5,6], [7,8,9], [10]]
```

### replace

Returns a string with all occurrences of a pattern replaced by a replacement string.

``` javascript
$replace($str: string, $pattern: string | regex, $replacement: string) => string
```

#### Basic usage

``` javascript
$replace("Hello World", "World", "Everyone") -> “Hello Everyone”
$replace("the cat sat on the mat", "at", "it") -> “the cit sit on the mit”
```

### reduce

Reduces an array to some value using a function.

``` javascript
$filter($arr: array, $func: ($e, $index?: number?, $ar: array )=> boolean) => any
```

#### Basic usage

``` javascript
$reduce([1,2,3,4], fn($prev, $cur) { $prev*$cur}) ) -> 24
```

### split

Splits a string into an array of strings using a pattern.

``` javascript
$split($str: string, $pattern: string | regex, $flags?: string) => array<string>
```

#### Basic usage

``` javascript
$split("so many words", " ") -> [ "so", "many", "words" ]
$split("so many words", " ", 2) -> [ "so", "many" ]
$split("too much, punctuation. hard; to read", /[ ,.;]+/) -> ["too", "much", "punctuation", "hard", "to", "read"]
```

### spread

Returns an array of objects with a single key/value pair, where the key is the name of the property and the value is the value of the property.

``` javascript
$spread($val: any) => array<object>
```

#### Basic usage

``` javascript
$spread({ "a": 1, "b": 2}) -> [ { "a" : 1}, {"b": 2}]
```

### string

Returns the string representation of the input value; if $prettify is true, the output string is formatted for readability.

``` javascript
$string($value: any, $prettify? true | false) => string
```

#### Basic usage

``` javascript
$string({"a": 1, "b": 2}) -> “{”a”:1, ”b” : 2}”
$string(5) -> “5”
$string([1,2,3]) -> [“1”, “2”, “3”]
```

### substring

Returns a substring of a string starting at $start and with length $length (if provided).

``` javascript
$substring($str: string, $start: number, $length?: number) => string
```

#### Basic usage

``` javascript
$substring("hello world", 0, 5) -> “hello”
$substring("hello world", -5, 5) -> “world”
```

### substringAfter

Returns the substring of a string after the first occurrence of a separator.

``` javascript
$substringAfter($str: string, $separator: string) => string
```

#### Basic usage

``` javascript
$substringAfter(“abc@gmail.com”, “@”) -> “gmail.com”
```

### substringBefore

Returns the substring of a string before the first occurrence of a separator.

``` javascript
$substringBefore($str: string, $separator: string) => string
```

#### Basic usage

``` javascript
$substringBefore( “john@gmail.com”, “@”) -> “john”
```

### sum

Returns the sum of the values of a numeric array.

``` javascript
$sum($array) => number
```

#### Basic usage

``` javascript
$sum([1,2,3,4]) -> 10
```

### trim

Returns a copy of a string with leading and trailing whitespace removed.

``` javascript
$trim($str: string) => string
```

#### Basic usage

``` javascript
$trim(" Hello \n World ") -> "Hello World"
```

### type

Returns the type of a value.

``` javascript
$type($val: any) => string
```

#### Basic usage

``` javascript
$type(“hello”) -> ”string”
$type(1) -> “number”
$type({}) -> “object”
$type([]) -> “array”
$type(null) -> “null”
```

### uppercase

Returns the uppercase version of a string

``` javascript
$uppercase($str: string) => string
```

#### Basic usage

``` javascript
$uppercase(“hello”) -> “HELLO”
```

### uuid

Returns a unique id (UUID version 4) as a string.

``` javascript
$uuid => string
```

#### Basic usage

``` javascript
$uuid -> "503c5a9f-b8fb-402a-b0d7-fae17490bdf6"
```

## Array functions

### append

Returns a new array with a value appended (added) to an array.

``` javascript
$append($arr: array, $val: any) => array
```

#### Basic usage

``` javascript
$append([1,2,3], [5,6]) -> [1,2,3,4,5,6]
$append([1,2,3], 5) -> [1,2,3,5]
```

### count

Returns the number of elements in an array.

``` javascript
$count($array) => number
```

#### Basic usage

``` javascript
$count([1,2,3,4,5]) -> 5
$count([]) -> 0
```

### distinct

Returns a new array with the distinct elements of $arr with duplicates eliminated.

``` javascript
$distinct($arr: array) => array
```

#### Basic usage

``` javascript
$distinct([“a”, “b”, “b”, “c”]) -> [“a”, “b”, “c”]
```

### reverse

Returns a new array with the elements of an array in reverse order.

``` javascript
reverse($arr: array) => array
```

#### Basic usage

``` javascript
$reverse([1,2,3,4,5]) -> [5,4,3,2,1]
```

### shuffle

Returns a new array with the elements of an array in random order.

``` javascript
shuffle($arr: array) => array
```

#### Basic usage

``` javascript
$shuffle([1,2,3,4]) -> [3,1,4,2]
```

### sort

A higher-order function that sorts the elements of an array using the $swapFn function. The comparator function takes two arguments. If it returns true, the elements will be swapped.

``` javascript
$sort($arr: array, $swapFn: ($l, $r)) => boolean
```

#### Basic usage

``` javascript
$sort([13,2,8,6,15], fn($l, $r) { $l > $r }) -> [2,6,8,13,15]
$sort([13,2,8,6,15], fn($l, $r) { $l < $r }) -> [15,13,8,6,2]
```

### zip

Takes two or more arrays and convolves (zips) each value from a set of arrays.

``` javascript
$zip($ar1:Array, $ar2:Array, $ar3;Array, ...) => Array
```

#### Basic usage

``` javascript
$zip([1,2,3],[4,5,6]) -> [[1,4],[2,5],[3,6]]
```

## Numeric functions

### abs

Returns the absolute value of a number.

``` javascript
$abs(n:number) : number
```

#### Basic usage

``` javascript
$abs(-1) ->  1
```

### ceil

Returns the smallest integer greater than or equal to a number.

``` javascript
$ceil($num: number) => number
```

#### Basic usage

``` javascript
$ceil(3.4) -> 4
```

### floor

Returns the largest integer less than or equal to a number.

``` javascript
$floor($num: number) => number
```

#### Basic usage

``` javascript
$floor(3.4) -> 3
```

### formatBase

Converts a number to a string in the optional base number system, if a base is not supplied, base 10 is used to create the string.

``` javascript
$formatBase($num: number, $base?: number) => string
```

#### Basic usage

``` javascript
$formatBase(100, 2) -> "1100100"
```

### number

Converts a value to a number.

``` javascript
$number($x: string | number | bool) => number
```

#### Basic usage

``` javascript
$number(“-0.05”) -> -0.05
$number(false) -> 0
$number(true) -> 1
```

### power

Returns $num raised to the $exp power.

``` javascript
$power($num: number, $exp: number) => number
```

#### Basic usage

``` javascript
$power(2, 3) -> 8
$power(3,4) -> 81
```

### round

Rounds a number to the optional precision number of decimal places. If precision is negative, then its value specifies which column to round to on the left side of the decimal place.

``` javascript
$round($num: number, $precision?: number) => number
```

#### Basic usage

``` javascript
$round(123.456) -> 123
$round(123.456, 2) -> 123.46
$round(123.456, -1) -> 120
$round(123.456, -2) -> 100
$round(125, -1) -> 120
$round(125.456,-1) -> 130
```

### sqrt

Returns the square root of a number.

``` javascript
$sqrt($num: number) => number
```

#### Basic usage

``` javascript
$sqrt(16) -> 4
```

## Date and time functions

### year

Extracts the year component from a timestamp and returns it as a number.

``` javascript
$year($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$year(“2023-02-08T07:56:14.747+00:00”) -> 2023
```

### month

Extracts the month component from a timestamp.

``` javascript
$month($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$month(“2023-02-08”) -> 2
```

### dayOfTheWeek

Returns the day of the week as a number [1=Monday, ... 6=Saturday, 7= Sunday].

``` javascript
$dayOfTheWeek($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$dayOftheWeek('2023-02-08') -> 3
$dayOftheWeek('2023-02-07') -> 2
```

### day

Extracts the day from a timestamp and returns it as a number.

``` javascript
$day($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$day(“2023-02-08”) -> 8
```

### hours

Extracts the local hour component from a timestamp and returns it as a number.

``` javascript
$hours($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$hours(“2023-02-08T07:56:14.747+00:00”) -> 7
```

### minutes

Extracts the minutes component from a timestamp and returns it as a number.

``` javascript
$minutes($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$minutes(“2023-02-08T07:56:14.747+00:00”) -> 56
```

### seconds

Extracts the local seconds component from a timestamp and returns it as a number.

``` javascript
$seconds($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$seconds(“2023-02-08T07:56:14.747+00:00”) -> 14
```

### milliSeconds

Extracts the milliseconds from a timestamp and returns it as a number.

``` javascript
$milliSeconds($timestamp: string |number) => number
```

#### Basic usage

``` javascript
$milliSeconds(“2023-02-08T07:56:14.747+00:00”) -> 747
```

### dateEquals

Returns true if the two timestamps are the same, false otherwise.

``` javascript
$equals($timestamp1: string |number, $timestamp2: string |number) => boolean
```

#### Basic usage

``` javascript
$dateEquals("2023-02-08", “2023-02-08”) -> true
$dateEquals("2023-02-08", “2023-02-07”) -> false
```

### hasSameDate

Returns true if the components specified in $units of  the two timestamps are the same, false otherwise.  $units is an array with one or more strings from ['years', 'months', 'days', 'hours', 'minutes', 'seconds', 'milliseconds'].

``` javascript
$hasSameDate($timestamp1: string |number, $timestamp2: string |number, units?: Array<string>) => boolean
```

#### Basic usage

``` javascript
$hasSameDate("23-02-08", "2019-02-08", ["month", "day"]) -> true
$hasSameDate('2023-02-01', '2023-02-08', ['month', 'year']) -> true
$hasSameDate("23-02-01", "2023-02-08", ["month", "year"]) -> true
$hasSameDate('2023-02-01T07:15:54.730Z', '2023-02-01T14:00:22.340Z', ['year','month', 'day']) -> true
```

### beforeDate

Returns true if $timestamp1 is before $timestamp2, false otherwise.

``` javascript
$beforeDate($timestamp1: string |number, $timestamp2: string |number) => boolean
```

#### Basic usage

``` javascript
$beforeDate(“2023-02-07”, “2023-02-08”) -> true
$beforeDate(“2023-02-08”, “2023-02-08”) -> false
```

### afterDate

Returns true if $timestamp1 is after $timestamp2, false otherwise.

``` javascript
$afterDate($timestamp1: string |number, $timestamp2: string |number) => boolean
```

#### Basic usage

``` javascript
$afterDate(“2023-02-09”, “2023-02-08”) -> true
$afterDate(“2023-02-08”, “2023-02-08”) -> false
```

### datePlus

Adds a duration of type $units which can be one of ['years', 'months', 'days', 'hours', 'minutes', 'seconds', 'milliseconds'],  to a $timestamp and returns the new timestamp. If $duration if less than zero, then the it will be subtracted from the $timestamp.

``` javascript
$datePlus($timestamp1: string |number, $duration: number, $units, ) => number
```

#### Basic usage

``` javascript
$datePlus(“2023-02-07”, 2, “days”) -> 1675900800000
$datePlus(“2023-02-07”, 2, “months”) -> 1680825600000
```

### diffDate

Returns the difference between two timestamps in the units specified which can be one of ['years', 'months', 'days', 'hours', 'minutes', 'seconds', 'milliseconds'].

``` javascript
$diffDate($timestamp1: string |number, $timestamp2: string |number, $units : string, ) => number
```

#### Basic usage

``` javascript
$diffDate("2023-02-08", "2023-01-22", "days") -> 17
$diffDate("2023-02-08", "2023-01-22","hours") -> 408
```

### fromMillis

Converts a number of milliseconds since the epoch to a string. $picture is optional, if not provided it will default to ISO format. Picture specs are as per Unicode date format standards.

``` javascript
$fromMillis($val:number, $picture?: string) => string
```

#### Basic usage

``` javascript
$fromMillis(1521801216617, 'dd/M/yyyy') -> "23/3/2018"
$fromMillis(1522616700000, 'E EEEE') -> "7 Sunday"
```

### toMillis

Converts a string to a number of milliseconds since the epoch. $picture is optional, if not provided it will default to ISO format. Picture specs are as per Unicode date format standards.

``` javascript
$toMillis($val:string, $picture?: string) => number
```

#### Basic usage

``` javascript
$toMillis("1970-01-01T00:00:00.001Z")  -> 1
$toMillis('2018-03-27', 'yyyy-MM-dd') -> 1522108800000
toMillis('21 August 2017', 'dd MMMM yyyy') -> 1503273600000
```
