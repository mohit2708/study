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


public function register(Request $request){
    $validator = $this->validateRegistration($request);

    if ($validator->fails()) {
        return response()->json(['errors' => $validator->errors()], 422);
    }

    try {
        DB::beginTransaction();

        // Create a new customer
        $user = User::create([
            'first_name' => $request->first_name,
            'last_name' => $request->last_name,
            'phone' => $request->phone_number,
            'email' => $request->email,
            'password' => Hash::make($request->password),
        ]);

        $userdetails = UserDetail::create([
            'user_id' => $user->id,
            'additional_phone' => $request->additional_phone
        ]);

        DB::commit();

        return response()->json(['message' => 'User registered successfully', 'user' => $user], 201);
    } catch (\Exception $e) {
        DB::rollBack();
        return response()->json(['error' => 'Registration failed', 'message' => $e->getMessage()], 500);
    }
}

public function validateRegistration(Request $request){
    return Validator::make($request->all(), [
        'first_name' => 'required|string|max:255',
        'email' => 'required|string|email|max:255|unique:users',
        // 'password' => [
        //     'required',
        //     'string',
        //     'min:6',
        //     'regex:/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).+$/'
        // ],
        'password' => [
            'required',
            'string',
            'min:6',
            function ($attribute, $value, $fail) {
                if (!preg_match('/[A-Z]/', $value)) {
                    $fail('The ' . $attribute . ' must contain at least one uppercase letter.');
                }
                if (!preg_match('/[a-z]/', $value)) {
                    $fail('The ' . $attribute . ' must contain at least one lowercase letter.');
                }
                if (!preg_match('/\d/', $value)) {
                    $fail('The ' . $attribute . ' must contain at least one number.');
                }
                if (!preg_match('/[!@#$%^&*()\-_=+{};:,<.>]/', $value)) {
                    $fail('The ' . $attribute . ' must contain at least one special character.');
                }
            },
        ],
        'confirm_password' => 'required|string|same:password',
    ]);
}

```