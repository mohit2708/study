```php
$update                   = Model::find($request->id);
$update->dataBase_name    = $request->field_name;
$update->dataBase_name    = $request->field_name;
$update->update();
```

```php
$booking = Booking::where('id',$request->booking_id)->update(["closed_by"=>$user_id]);
```