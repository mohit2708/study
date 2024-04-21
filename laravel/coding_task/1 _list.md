### Get the list from the database
```php
$customer_data = Model::Orderby('id','asc')->whereNotIn('id', [1])->get();
return view('admin.customer.list',compact('customer_data'));
```


### Blade file
```php
@if($getTransctionByLocation->count() > 0)
    @foreach ($getTransctionByLocation as $transaction)
    <tr>
        <td>{{$transaction['first_name']}} {{$transaction['last_name']}}</td>
        <td>$&nbsp;{{number_format((float)$transaction['amount'], 2, '.', '')}}</td>
        <td>{{$transaction['created_at']->format('m/d/Y')}} / {{$transaction['created_at']->format('h:m A')}}</td>
        <td>{{ \Carbon\Carbon::parse($startDate)->format('m/d/Y') }}</td>
    </tr>
    @endforeach
    @else
    <tr>
        <td colspan="4" style="text-align:center">No data found</td>
    </tr>
@endif
```