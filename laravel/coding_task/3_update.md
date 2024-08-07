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

```php
$booking = Booking::where('id',$request->booking_id)->update(["closed_by"=>$user_id]);
```


### blade file
```php
# text box
<div class="form-group">
    <label>First Name: <span style="color: red;">*</span></label>
    <input type="text" name="first_name"
        class="form-control @error('first_name') is-invalid @enderror"
        id="first_name" value="{{ $data_admin->first_name }}"
        placeholder="Enter your first name">
    @error('first_name')
    <span class="invalid-feedback" role="alert">
        <strong>{{ $message }}</strong>
    </span>
    @enderror
</div>

# Select option
<label>Duration Type:<span style="color: red;">*</span></label>
<select class="form-control @error('duration_type') is-invalid @enderror"
    id="duration_type" name="duration_type"
    value="{{ $data_plan->duration_type }}">
    <option value="">-- Select your Duration Type --</option>
    <option value="day" {{ ( $data_plan->duration_type == 'hour' ) ? 'selected' : '' }}>Hour</option>
    <option value="day" {{ ( $data_plan->duration_type == 'day' ) ? 'selected' : '' }}>Day </option>
    <option value="month" {{ ( $data_plan->duration_type == 'month' ) ? 'selected' : '' }}>Month </option>
    <option value="year" {{ ( $data_plan->duration_type == 'year' ) ? 'selected' : '' }}>Year </option>
</select>
```

# Update or create
```php
$deviceUpdate = DeviceInfo::updateOrCreate(
                ['location_id' => $request->location_id],
                ['device_id'=> $request->device_id, 'merchant_id'=> $request->merchant_id]
            );
```