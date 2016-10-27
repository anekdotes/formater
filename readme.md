# Anekdotes Formatter

[![Latest Stable Version](https://poser.pugx.org/anekdotes/formatter/v/stable)](https://packagist.org/packages/anekdotes/formatter)
[![Build Status](https://travis-ci.org/anekdotes/formatter.svg?branch=master)](https://travis-ci.org/anekdotes/formatter)
[![codecov.io](https://codecov.io/gh/anekdotes/formatter/coverage.svg)](https://codecov.io/gh/anekdotes/formatter?branch=master)
[![StyleCI](https://styleci.io/repos/63600389/shield?style=flat)](https://styleci.io/repos/63600389)
[![License](https://poser.pugx.org/anekdotes/formatter/license)](https://packagist.org/packages/anekdotes/formatter)
[![Total Downloads](https://poser.pugx.org/anekdotes/formatter/downloads)](https://packagist.org/packages/anekdotes/formatter)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/50134febcefe4cc78daf07ca45969728)](https://www.codacy.com/app/Grasseh/formatter?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=anekdotes/formatter&amp;utm_campaign=Badge_Grade)

Utility to format whole Input using provided rules

## Installation

Install via composer into your project:

    composer require anekdotes/formatter

## Usage

To use the formatter, include its namespace through Composer, then call its namespace and provide it with an data input and a rule input.

Exemple :

```php
    use Anekdotes\Formatter\Formatter;
    $input = ["formPhoneNumber" => "1234567890"];
    $rules = ["formPhoneNumber" => ["phoneNumber"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["formPhoneNumber" => "(123) 456-7890"]

```

## Rules

  Here's a list of the usable rules : 

### postalCode

Convert into a postal code following this format : A1A 1A1

```php
    use Anekdotes\Formatter\Formatter;
    $input = ["form" => "j6z1b2"];
    $rules = ["form" => ["postalCode"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["formPhoneNumber" => "J6Z 1B2"]
```

### phoneNumber

Convert into a phone number following the format 111, 111-1111 or (111) 111-1111
```php
    use Anekdotes\Formatter\Formatter;
    $input = ["formPhoneNumber" => "1234567890"];
    $rules = ["formPhoneNumber" => ["phoneNumber"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["form" => "(123) 456-7890"]
```

### float
Cuts the characters following a float

```php
    use Anekdotes\Formatter\Formatter;
    $input = ["form" => "122.2abc"];
    $rules = ["form" => ["float"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["form" => "122.2"]
```

### int
Cuts the character following an integer
```php
    use Anekdotes\Formatter\Formatter;
    $input = ["form" => "122.2abc"];
    $rules = ["form" => ["int"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["form" => "122"]
```

### integer
```php
    use Anekdotes\Formatter\Formatter;
    $input = ["form" => "122.2abc"];
    $rules = ["form" => ["integer"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["form" => "122"]
```

### website
Append an http:// to a website.
```php
    use Anekdotes\Formatter\Formatter;
    $input = ["form" => "www.anekdotes.com"];
    $rules = ["form" => ["website"]];
    $formattedOutput = Formatter::make($input, $rules);
    // $formattedOutput is now ["form" => "http://www.anekdotes.com"]
```

## Combining Rules
```php

```
