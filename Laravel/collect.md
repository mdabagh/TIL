### `collect`

`collect` is a class in the Laravel framework that allows you to perform operations such as filtering, sorting, pattern matching, and more on arrays and collections.

For example, using `collect`, you can convert an array of Eloquent models into a collection and perform operations such as filtering, sorting, and more on them in a chained manner.

```php
$users = User::all()->where('active', true);
$usersCollection = collect($users);
$activeUsers = $usersCollection->filter(function ($user) {
    return $user->is_active;
})->sortBy('name');
```

In this example, we first retrieve all active users from the database. Then, we convert them into a collection using `collect`. Finally, we filter the active users and sort them by their names using `filter` and `sortBy` functions respectively.
