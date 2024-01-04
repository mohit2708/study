### update data by DB
```php
DB::table('table_name')
    ->where('id', $request->job_id)
    ->update(['cal_add_job' => 1,'cal_add_job' => 1]);
```



# Project

```php
# Controll file

/**
* Update the specified resource in storage.
*
* @param  int  $id
* @return Response
*/
use Illuminate\Validation\Rule;

public function update(Request $request){
    try{
        $request->validate([
            'first_name'        => 'required|string|between:2,100',
            'email' => ['required','string','email','max:100',Rule::unique('users')->ignore($request->id),],
            'phone' => 'required|max:20',
            'beachlocation' => 'required'
        ]);
        $update_staff                 = User::find($request->id);
        $update_staff->location_id    = $request->beachlocation;
        $update_staff->email          = $request->email;
        $update_staff->update();
        return redirect('staff/list')->with('success', 'Staff updated successfully!');
    }catch (Exception $e) {
        Log::error($e->getMessage(), $e->getTrace());
    }	
}
```