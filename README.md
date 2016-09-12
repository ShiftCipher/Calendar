# Calendar
Laravel 5 Calendar

##Installation

Require codeapps/calendar in composer.json and run composer update.

```
{
    "require": {
        "laravel/framework": "5.2.*",
        ...
        "codeapps/calendar": "dev-master"
    }
    ...
}
```

Composer will download the package. After the package is downloaded, open config/app.php and add the service provider and alias as below:

```

'providers' => array(
    ...
    'Codeapps\Calendar\CalendarServiceProvider::class',
),



'aliases' => array(
    ...
    'Calendar' => 'Codeapps\Calendar\Facades\Calendar::class',
),

```
Finally you need to publish a configuration file by running the following Artisan command.

```
php artisan vendor:publish
```

Include css in your view

```
<link rel="stylesheet" type="text/css" href="{{ asset('css/calendar.css') }}">

```

Create a Controller 

```
use Codeapps\Calendar\Calendar as Calendar;

public function create()
  {
    $data[] = [
            'label' => 'Label',
            'class' => 'blue',
            'events' => [

            [
            'label' => 'Codeapps',
            'start' => '2015-06-19 08:30:16',
            'end'   => '2015-06-23 10:30:16',
            'class' => '',
            'icon' => 'fa-arrow-down'
            ]
        ]
    ];

    return view('orders.create', compact('data'));
  }
```

Create a View and Add 

```
{!! Calendar::render($data,['title'=>'Codeapps'])!!}
```

