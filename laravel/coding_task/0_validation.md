### Add validation
```php
$validator = Validator::make($credentials, [
    'first_name'    => 'required|string|max:255',
    'email'         => 'required|string|email|max:255|unique:users',
    'phone_number'  => 'required|unique:users,phone',   # phone number already exist.
    'password'      => 'required|string|min:6|max:50'
    'password' => [
                'required',
                'string',
                'min:6',
                'max:50',
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

if ($validator->fails()) {
    return response()->json(['error' => $validator->messages()], 200);
}
```