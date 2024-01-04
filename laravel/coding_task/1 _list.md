### Get the list from the database
```php
$customer_data = Model::Orderby('id','asc')->whereNotIn('id', [1])->get();
return view('admin.customer.list',compact('customer_data'));
```