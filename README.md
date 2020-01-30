## Introduction

Horizon Horizon is based on the official [Laravel Horizon](https://github.com/laravel/horizon) package.The web UI is also included.

If you prefer a pure restful api and want to customize the UI, you can refer to [Lumen-horizon](https://github.com/servocoder/lumen-horizon) by servocoder.

## Installation

1. Run composer to add the dependency.

```
composer require kinsolee/horizon-lumen
```

2. Install the horizon or publish the assets only
```php
php artisan horizon:install // This will copy the config file to the config directory
php artisan horizon:assets
```
## Problems
* If you get the follow errors when you run `horizon:assets`/`horizon:install`:
```
Type error: Argument 1 passed to Laravel\Horizon\Repositories\RedisMasterSupervisorRepository::__construct() must implement interface Illuminate\Contr
  acts\Redis\Factory, instance of Redis given
```
Make sure you register `Illuminate\Redis\RedisServiceProvider::class` in your `boorstrap/app.php` file.

* If you deploy horizon-lumen on sub-directory, please specific `base_path` in config/horizon.php

* If you occur error: `ERROR: RuntimeException: A facade root has not been set.`, please uncomment `$app->withFacades();` in `bootstrap/app.php` 
## Official Documentation

Documentation for Horizon can be found on the [Laravel website](https://laravel.com/docs/horizon).

## Contributing

Thank you for considering contributing to Horizon! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

Please review [our security policy](https://github.com/laravel/horizon/security/policy) on how to report security vulnerabilities.

## License

Laravel Horizon is open-sourced software licensed under the [MIT license](LICENSE.md).
