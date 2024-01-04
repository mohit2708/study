### Login Api
```php
use Illuminate\Support\Facades\Auth;
use Illuminate\Http\Request;
use Validator;
use JWTAuth;

/**
 * User Login.
 *
 * @return \Illuminate\Http\JsonResponse
 */
public function login(Request $request)
{
    $credentials = $request->only('email', 'password');
    $loginDetails = User::where('email',$credentials['email'])->first();

    //valid credential
    $validator = Validator::make($credentials, [
        'email' => 'required|email',
        'password' => 'required|string|min:6|max:50'
    ]);
    if ($validator->fails()) {
        return response()->json(['error' => $validator->messages(), 'status' => 442], 422);
    }

    //Creat token
    try {
        // $token = Auth::attempt($credentials);
        if (!$token = JWTAuth::attempt($credentials)) {
            return response()->json([
                'success' => false,
                'message' => 'Login credentials are invalid.',
                'status' => 401
            ], 401);
        }
        //Token created, return with success response and jwt token
        $loginDetails['success'] = true;
        $loginDetails['token'] = $token;
        return response()->json([
            'loginDetails' => $loginDetails,
            'status' => 200
        ]);
        
    } catch (JWTException $e) {
    return $credentials;
        return response()->json([
            'success' => false,
            'message' => 'Could not create token.',
            'status' => 500
        ], 500);
    }        
    
}
```
