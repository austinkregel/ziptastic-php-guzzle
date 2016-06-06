[![Build Status](https://travis-ci.org/austinkregel/ziptastic-php-guzzle.svg?branch=master)](https://travis-ci.org/austinkregel/ziptastic-php-guzzle)

# Ziptastic PHP with Guzzle

This library is a [Guzzle](http://docs.guzzlephp.org/en/latest/) based interface for the [Ziptastic API](https://getziptastic.com/).

Using Ziptastic requires an API key, you can get one by signing up with Ziptastic.

## Installing

Ziptastic PHP can be installed via composer:

````
composer require kregel/ziptastic
````

## Usage

There are two different ways to use this package with the same end result.

The first way to use this is by using `Zipper` which will be using a more "plain english" oriented syntax
````php
<?php

include "vendor/autoload.php";

use Kregel\Ziptastic\Zipper;

$results = (new Zipper)->in('US')->withPostalCode(48867)->andWithKey($key)->find();
echo $results->response;
?>
````

If that isn't your cup of tea or you just want to get things done, you can use `Ziptastic`

````php
<?php

include "vendor/autoload.php";

use Kregel\Ziptastic\Ziptastic;

$results = (new Ziptastic(23042,'us'))->setKey($key)->find();

echo $results->response;
?>
````

## Using results
If you wanted to, you can access any and all of the results of the api call via calling the item you want from the api response.
The first way to use this is by using `Zipper` which will be using a more "plain english" oriented syntax
````php
<?php

include "vendor/autoload.php";

use Kregel\Ziptastic\Zipper;

$results = (new Zipper)->in('US')->withPostalCode(48867)->andWithKey($key)->find();
echo $results->city, ', ',$results->state,' ',$results->postal_code;
?>
````
And in that example the only one set by default is the postal code, the others are from the response.


Ziptastic PHP is licensed under the [MIT license](https://opensource.org/licenses/MIT/).