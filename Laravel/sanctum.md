# Laravel Authentication with API using Sanctum

Laravel Sanctum is a simple and lightweight package for authentication in Laravel applications, particularly for single-page applications (SPAs) and mobile applications. It provides an easy-to-use authentication system for issuing API tokens and authenticating requests with those tokens.

## Installation

To install Laravel Sanctum, run the following command:

```
composer require laravel/sanctum
```

After installing the package, run the following command to publish the configuration file:

```
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
```

Next, run the migrations to create the required tables for token management:

```
php artisan migrate
```

## Usage

### Setting Up Authentication

To set up authentication, you need to first add the `HasApiTokens` trait to your user model:

```php
use Laravel\Sanctum\HasApiTokens;

class User extends Authenticatable
{
    use HasApiTokens, Notifiable;
    // ...
}
```

Next, add the `api` guard to the `guards` array in `config/auth.php`:

```php
'guards' => [
    // ...
    'api' => [
        'driver' => 'sanctum',
        'provider' => 'users',
        'hash' => false,
    ],
]
```

### Issuing Tokens

To issue tokens, you can use the `createToken` method on a usermodel instance. This method creates a new token for the user and returns the token instance:

```php
$user = User::find(1);
$token = $user->createToken('Token Name')->plainTextToken;
```

The `plainTextToken` property of the token instance contains the actual token value that you can use for subsequent requests.

### Protecting Routes

To protect routes with authentication, you can use the `auth:sanctum` middleware. For example, to protect an API endpoint, you can define a route like this:

```php
Route::middleware('auth:sanctum')->get('/api/user', function (Request $request) {
    return $request->user();
});
```

This route returns the authenticated user instance for the request. The `auth:sanctum` middleware authenticates the request with the API token and associates the authenticated user instance with the request.

### Revoking Tokens

To revoke an API token, you can use the `tokens()->delete()` method on a user model instance. This method deletes all tokens for the user:

```php
$user->tokens()->delete();
```

You can also revoke a single token by calling the `revoke()` method on the token instance:

```php
$token->revoke();
```

## Conclusion

Laravel Sanctum is a simple and lightweight package for authentication in Laravel applications. By following the instructions in this document, you can easily set up authentication, issue tokens,protect routes, and revoke tokens using Laravel Sanctum.
