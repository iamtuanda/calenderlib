# Calendar Lib
Calendar Lib to get and check the holidays in Japan.
## Describe
```
function getHolidays()
```
- Get the holiday from the url as a JSON file and return an array containing the holidays.
```
function checkHoliday($ymd_date)
```
- Check if a day is a holiday or not, if it is a holiday, it will return a non-holiday day and vice versa return it.
-  Input param:

$ymd_date: Any day of the year.

## How to use

To use this library, you must first call the **namespace**. There are two ways to declare:

* [use](https://www.php.net/manual/en/language.namespaces.importing.php) - The use syntax (more popular):

```php
use My\Full\Classname
```
* [new](https://techblog.vn/bai-11-namespace-trong-php) - The new syntax:

```php
new namespaceName\className();
```
The **namespace** load declaration must also be placed on top of a file, if in a file the namespace and **use** are used, the **use** will be placed under the **namespace**.

Access method of class:

* Access in class

To access the methods of the class while we are still in the class, we use the following syntax:

```php
$this->methodName(); 

//or if there are arguments 
$this->methodName(argument);
```

* Accessed outside the class

For method calls while outside the class, you just need to use the following syntax:

```php
$newClass = new className();
$newClass->methodName;
//or
$newClass = (new className)->methodName();
```

## Method Summary

`file_get_contents()` - Reads entire file into a string

`ksort()` - Sort an array by key

`date_format()` - Returns date formatted according to given format

`json_decode()` - Decodes a JSON string

## Method Detail

### file_get_contents()
```php
file_get_contents(string $filename [, bool $use_include_path = FALSE [, resource $context[, int $offset = 0 [, int $maxlen ]]]]) : string
```
Reads entire file into a string

#### Parameters
`filename`: Name of the file to read.

`use_include_path`: The **`FILE_USE_INCLUDE_PATH`** constant can be used to trigger [include path](https://www.php.net/manual/en/ini.core.php#ini.include-path) search. This is not possible if [strict typing](https://www.php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration.strict) is enabled, since **`FILE_USE_INCLUDE_PATH`** is an [int](https://www.php.net/manual/en/language.types.integer.php). Use **`TRUE`** instead.

`context`: A valid context resource created with  [stream_context_create()](https://www.php.net/manual/en/function.stream-context-create.php). If you don't need to use a custom context, you can skip this parameter by  **`NULL`**.

`offset`:  The offset where the reading starts on the original stream. Negative offsets count from the end of the stream. Seeking (`offset`) is not supported with remote files. Attempting to seek on non-local files may work with small offsets, but this is unpredictable because it works on the buffered stream.

`maxlen`: Maximum length of data read. The default is to read until end of file is reached. Note that this parameter is applied to the stream processed by the filters.

#### examples

Get and output the source of the homepage of a website:

```php
<?php  
$homepage = file_get_contents('http://www.testtest.com/');  
echo $homepage;  
?>
```

### ksort()

```php
ksort (array &$array [, int $sort_flags = SORT_REGULAR ]) : bool
```

Sort an array by key

#### Parameters

`array`: The input array.

`sort_flags`: You may modify the behavior of the sort using the optional parameter  `sort_flags`, for details see  [sort()](https://www.php.net/manual/en/function.sort.php).

#### examples

```php
<?php  
$subject = array("php"=>"1", "css"=>"2", "js"=>"3", "html"=>"4");  
ksort($subject);  
foreach ($subject as $key => $val) {  
echo "$key = $val\n";  
}  
?>
```
The above example will output:
```
css = 2
html = 4
js = 3
php = 1
```

### date_format()

```php
date_format($object, $format) : string
```

 Returns date formatted according to given format

#### Parameters

`object`: Procedural style only: A  [DateTime](https://www.php.net/manual/en/class.datetime.php)  object returned by  [date_create()](https://www.php.net/manual/en/function.date-create.php)

`format`: Format accepted by  [date()](https://www.php.net/manual/en/function.date.php).

#### examples

Object oriented style:

```php
<?php  
$date = new DateTime('2020-07-10');  
echo $date->format('Y-m-d H:i:s');  
?>
```

### json_decode()

```php
json_decode(string, assoc, depth, options)
```

Takes a JSON encoded string and converts it into a PHP variable.

#### Parameters

`string`: Required. Specifies the value to be encoded.

`assoc`: Optional. Specifies a Boolean value. When set to **true**, the returned object will be converted into an associative **array**. When set to **false**, it returns an **object**. **False** is default.

`depth`: Optional. Specifies the recursion depth. Default recursion depth is 512.

`options`: Optional. Specifies a bitmask (**JSON_BIGINT_AS_STRING**, **JSON_INVALID_UTF8_IGNORE**, J**SON_INVALID_UTF8_SUBSTITUTE**,  **JSON_OBJECT_AS_ARRAY**, **JSON_THROW_ON_ERROR**)

#### examples

Store JSON data in a PHP variable, and then decode it into a PHP associative array:

```php
<?php  
$jsonobj = '{"tuan":23,"huy":24,"nam":28}';  
var_dump(json_decode($jsonobj, true));  
?>
```

The above example will output:

```php
array(3) {
  ["tuan"]=>
  int(23)
  ["huy"]=>
  int(24)
  ["nam"]=>
  int(28)
}
```
