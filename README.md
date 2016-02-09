## Laravel Resque

This package allows you to connect to Resque when using `Queue`.

This is a fork of deedod's [laravel-resque-ex](https://github.com/deedod/laravel-resque-ex) modified to work with [Laravel 5 Command Bus](https://laravel.com/docs/5.0/bus).

Also adds automatic exponential backoff with default delay of 30 seconds and max delay of 2 hours.

## Requirements
- PHP 5.4+

## Installation

Add the following to your project's `composer.json`:

    "require": {
    	"deboorn/laravel-resque-ex": "1.0.*"
    }

Now you need to run the following to install the package:

	composer update

Next you need to add the following service provider to your `app/config/app.php`:

    'Resque\ServiceProviders\ResqueServiceProvider'

Now you need to add the following to your `/app/config/queue.php` "connections" section:

    "resque" => [
    	"driver" => "resque"
    ]

If you wish to use this driver as your default Queue driver you will need to set the following as your "default" drive in `app/config/queue.php`:

    "default" => "resque",


### Enqueing a Job

Same as [Laravel Command Bus Queued Commands](https://laravel.com/docs/5.0/bus#queued-commands).

### Starting Resque Listener

Execute `resque:listen` command with comma seperated list of queue names:

    php artisan resque:listen --queue=default
    

## Further Documentation

- [PHP-Resque](https://github.com/kamisama/php-resque-ex)
- [PHP-Resque-Scheduler](https://github.com/kamisama/php-resque-ex-scheduler)

## License

Laravel Resque is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
