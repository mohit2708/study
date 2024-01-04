### Signup 
```php
/**
 * Register a User.
 *
 * @return \Illuminate\Http\JsonResponse
 */
public function register(Request $request) {
    $validator = Validator::make($request->all(), [
        'first_name'    => 'required|string|between:2,100',
        'last_name'     => 'required|string|between:2,100',
        'phone'         => 'nullable|max:20',
        'email'         => 'required|string|email|max:100|unique:users',
        'password'      => 'required|string|min:6',
    ]);
    if($validator->fails()){
        return response()->json(['error' => $validator->errors()->toJson(), 'status' => 400], 400);
    }
    $user = User::create(array_merge(
                $validator->validated(),
                ['password' => bcrypt($request->password)]
            ));
    return response()->json([
        'message' => 'User successfully registered',
        'user' => $user,
        'status' => 200
    ], 200);
}
```