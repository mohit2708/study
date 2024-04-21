### Ques. What is a Route?
* A route is basically an endpoint specified by a URI (Uniform Resource Identifier).
* We create the routes of the website in **web.php** and **APIs routes** in api.php inside the **routes folder**.
* The route is a way of creating a request URL for your application.
*  These routes are assigned to the web middleware group, providing features like session state and CSRF protection.
```php
Route::get('/', function (){      
    return view ('welcome');
}); 
```

### Redirect Routes?
* If we are defining a route that redirects to another URI, you may use the Route::redirect method.
```php
Route::redirect('/here', '/there');
```
* By default, Route::redirect returns a 302 status code. You may customize the status code using the optional third parameter:
```php
Route::redirect('/here', '/there', 301);
```

### View Routes?
* If your route only needs to return a view, you may use the Route::view method.
```php
Route::view('/welcome', 'welcome');
```

### The Route List?
* The route:list Artisan command can easily provide an overview of all of the routes that are defined by your application:
```php
php artisan route:list
```

### Named Routes?
* Named routes allow the convenient generation of URLs or redirects for specific routes. You may specify a name for a route by chaining the name method onto the route definition:
```php
Route::get('/user/profile', [UserProfileController::class, 'show'])->name('profile');
```

### Route Groups?
* Route groups allow you to share route attributes, such as middleware, across a large number of routes without needing to define those attributes on each individual route.
* We can assign middleware to all routes within a group,
```php
Route::middleware(['first', 'second'])->group(function () {
    Route::get('/', function () {
        // Uses first & second middleware...
    });
 
    Route::get('/user/profile', function () {
        // Uses first & second middleware...
    });
});
```

### Group Controllers?
* We use the controller method to define the common controller for all of the routes within the group.
```php
use App\Http\Controllers\OrderController;
 
Route::controller(OrderController::class)->group(function () {
    Route::get('/orders/{id}', 'show');
    Route::post('/orders', 'store');
});
```

### Fallback Routes?
* Using the Route::fallback method, you may define a route that will be executed when no other route matches the incoming request.
* Typically, unhandled requests will automatically render a "404" page via your application's exception handler. However, 
* You would typically define the fallback route within your routes/web.php file, all middleware in the web middleware group will apply to the route. You are free to add additional middleware to this route as needed:
```php
Route::fallback(function () {
    // ...
});

# OR
Route::fallback('/create-payment', [ControllerName::class]);\
# under controlle class 
public function __invoke(){
    return view();
}
```

### Rate Limiting?
* Go to **App\Providers\RouteServiceProvider** and write the code
```php
protected function configureRateLimiting()
{
    RateLimiter::for('api', function (Request $request) {
        return Limit::perMinute(60)->by($request->user()?->id ?: $request->ip());
    });

    RateLimiter::for('customeRateLimit', function (Request $request) {
        return Limit::perMinute(6);
    });
}
```
* Apply in routes
```php
RateLimiter::for('check-rate-limit', function () {
    return "hi";
})->middalware('throttle:customeRateLimit');
```

### Accessing the Current Route
```php
use Illuminate\Support\Facades\Route;
 
$route = Route::current(); // Illuminate\Routing\Route
$name = Route::currentRouteName(); // string
$action = Route::currentRouteAction(); // string
```



### CSRF TOKEN?
* Laravel automatically generates a CSRF "token" for each active user session managed by the application.
* This token is used to verify that the authenticated user is the person actually making the requests to the application. 
* This token is stored in the user's session and changes each time the session is regenerated.
```php
<form method="POST" action="{{route('pay')}}">
    @csrf
</form>
# OR
<form method="POST" action="{{route('pay')}}">
    <input type="hidden" name="_token" value="{{ csrf_token() }}" />
</form>
```

### X-CSRF-TOKEN?
* store the token in an HTML meta tag:
```php
<meta name="csrf-token" content="{{ csrf_token() }}">

$.ajaxSetup({
    headers: {
        'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
    }
});
```