## Description

This package adds [Cross-Origin Resource Sharing](www.w3.org/TR/cors/) (CORS) support to your Laravel application.

## Install

```
composer require neomerx/cors-illuminate
```

Add to your applications CORS provider by adding the following line to your `config/app.php` file
```php
<?php

return [

    ...

    'providers' => [

        ...

        \Neomerx\CorsIlluminate\Providers\LaravelServiceProvider::class,

    ],
    
    ...

];
```

Then you will configure CORS. Firstly create a config file by executing

```
php artisan vendor:publish --provider="Neomerx\CorsIlluminate\Providers\LaravelServiceProvider"
```

it will create `config/cors-illuminate.php` file in you application.

[This file](config/cors-illuminate.php) is extensively commented so it will be easy for you to set up it for your needs. First settings you need to configure are server origin (URL) and allowed origins
```php
    ...
    
    /**
     * Could be string or array. If specified as array (recommended for
     * better performance) it should be in parse_url() result format.
     */
    Settings::KEY_SERVER_ORIGIN => [
        'scheme' => 'http',
        'host'   => 'localhost',
        'port'   => 1337,
    ],

    /**
     * A list of allowed request origins (lower-cased, no trail slashes).
     * Value `true` enables and value `null` disables origin.
     * If value is not on the list it is considered as not allowed.
     * Environment variables could be used for enabling/disabling certain hosts.
     */
    Settings::KEY_ALLOWED_ORIGINS => [
        'http://localhost:4200' => true,
    ],
    
    ...
```

## Testing

```
composer test
```

## Contributing

Pull requests for documentation and code improvements (PSR-2, tests) are welcome.

## Versioning

This package is using [Semantic Versioning](http://semver.org/).

## License

Apache License (Version 2.0). Please see [License File](LICENSE) for more information.