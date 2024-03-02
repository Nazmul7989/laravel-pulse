# Laravel Telescope

### Installation
Since Pulse is currently in beta, you may need to adjust your application's `composer.json` file to allow beta package releases to be installed:
``` 
"minimum-stability": "beta",
"prefer-stable": true
```
Then, you may use the Composer package manager to install Pulse into your Laravel project:
``` 
composer require laravel/pulse
```
Next, you should publish the Pulse configuration and migration files using the vendor:publish Artisan command:
``` 
php artisan vendor:publish --provider="Laravel\Pulse\PulseServiceProvider"
```
Finally, you should run the migrate command in order to create the tables needed to store Pulse's data:

``` 
php artisan migrate
```

### See [Laravel Pulse](https://laravel.com/docs/10.x/pulse) for more details
