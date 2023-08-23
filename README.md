## Laravel Nova Daterange picker
### Description
This package adds a new custom daterange picker field to [Laravel Nova](https://nova.laravel.com/).

### Example
![2018-10-01 11_28_00](https://thumbs.gfycat.com/KaleidoscopicThoroughFennecfox-size_restricted.gif)

### Usage
To add a new daterange field, simply add it to your array of fields, providing the "from-to" attributes as parameters.
``` php
namespace App\Nova;

// ...

use Kpolicar\DateRange\DateRange;

class Reservation extends Resource
{
    // ...
    
    public function fields(Request $request)
    {
        return [
            // ...
            
            DateRange::make(['From', 'To']),
            // or DateRange::make('Between', ['from', 'to']),
            
            // ...
        ];
    }
}
```
You should also ensure the Eloquent model that your resource represents is casting the used attributes as dates.
``` php
namespace App\Nova;

// ...

class Reservation extends Model
{
    protected $dates = [
        'from',
        'to',
    ];

    protected $casts = [
        'from' => 'date',
        'to' => 'date',
    ];
}

```

### Installation
You can install this package in to a Laravel app that uses Nova via composer:
```
composer require kpolicar/nova-date-range
```

### License
The MIT License. Please see [License File](LICENSE) for more information.
