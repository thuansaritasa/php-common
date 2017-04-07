# PHP Common classes

Common Saritasa classes and helpers, that can be used universally in any application.
This package should not depend on any framework or library.

## Usage

Install the ``saritasa/php-common`` package:

```bash
$ composer require saritasa/php-common
```

Add the BladeDirectivesServiceProvider service provider ``config/app.php``:

```php
'providers' => array(
    // ...
    Saritasa\Laravel\BladeDirectivesServiceProvider::class,
)
```

## Available classes

### Enum
Alternative for [SplEnum](http://php.net/manual/ru/class.splenum.php) class.
Designed to be container for repeatedly used set of constants.

**Example**:
```php
class Gender extends Saritasa\Enum
{
    const MALE = 'Male';
    const FEMALE = 'Female';
}
```
then somewere in code:
```php
$allGenders = Gender::getConstants();
$gender = new Gender($stringValue); // Will throw UnexpectedValueException on unknown value;
function getGenderDependentValue(Gender $gender) { ... }
```

## Exception Definitions
### ConfigurationException
Throw this, if you find erroneous configuration.

**Example**:
```
$payPalKey = config('services.paypal_key');
if (!$payPalKey) {
    throw new ConfigurationException("PayPal key is not configured");
}

```

## Contributing

### Requirements
This package must:
* Do not depend on any framework or library
* Do not depend on other Saritasa packages
* Do not register any providers

1. Create fork
2. Checkout fork
3. Develop locally as usual. **Code must follow [PSR-1](http://www.php-fig.org/psr/psr-1/), [PSR-2](http://www.php-fig.org/psr/psr-2/)**
4. Update README.md to describe new or changed functionality. Add changes description to CHANGE file.
5. When ready, create pull request

## Resources

* [Bug Tracker](http://github.com/saritasa/php-blade-directives/issues)
* [Code](http://github.com/saritasa/php-blade-directives)
