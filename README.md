# Calendar
Laravel 5 Calendar

##Installation

Require codeapps/calendar in composer.json and run composer update.

```
{
    "require": {
        "laravel/framework": "5.1.*",
        ...
        "codeapps/calendar": "*"
    }
    ...
}
```

Composer will download the package. After the package is downloaded, open config/app.php and add the service provider and alias as below:

```

'providers' => array(
    ...
    'Codeapps\Calendar\CalendarServiceProvider',
),



'aliases' => array(
    ...
    'Calendar' => 'Codeapps\Calendar\Facades\Calendar',
),

```
Finally you need to publish a configuration file by running the following Artisan command.

```
php artisan vendor:publish --tag=public --force
```

Include css in your view

```
<link href="/public/vendor/codeapps/calendar.css" rel="stylesheet" type="text/css">

```
