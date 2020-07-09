
# Calendar Lib

Calendar Lib to get and check the holidays in Japan.

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
```
