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

### Configuration
Many of Pulse's configuration options can be controlled using environment variables. To see the available options, register new recorders, or configure advanced options, you may publish the `config/pulse.php` configuration file:

``` 
php artisan vendor:publish --tag=pulse-config
```

### Dashboard Access & Authorization
The Pulse dashboard may be accessed via the `/pulse` route. By default, you will only be able to access this dashboard in the local environment, so you will need to configure authorization for your production environments by customizing the `viewPulse` authorization gate. You can accomplish this within your application's `app/Providers/AuthServiceProvider.php` file:

``` 
use App\Models\User;
use Illuminate\Support\Facades\Gate;
 
/**
 * Register any authentication / authorization services.
 */
public function boot(): void
{
    Gate::define('viewPulse', function (User $user) {
        return $user->isAdmin();
    });
 
    // ...
}
```

### See [Laravel Pulse](https://laravel.com/docs/10.x/pulse) for more details
