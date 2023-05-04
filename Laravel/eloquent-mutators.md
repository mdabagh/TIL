### `getFullNameAttribute`

To define the `getFullNameAttribute` accessor, you can add the following code to the `User` model:

```php
public function getFullNameAttribute()
{
    return "{$this->first_name} {$this->last_name}";
}
```

In this code, `getFullNameAttribute` combines the `first_name` and `last_name` attributes of the `User` model using string interpolation and returns the full name as a string.

To call this accessor for an instance of the `User` model, you can do this:

```php
$user = User::find(1);
$fullName = $user->full_name;
```

This will return the full name of the user with `id` of `1`.

### `getFirstParentUserAttribute`

To define the `getFirstParentUserAttribute` accessor, you can add the following code to the `User` model:

```php
public function getFirstParentUserAttribute()
{
    return $this->parentUser;
}
```

In this code, `getFirstParentUserAttribute` uses the `parentUser` relationship to find the user whose `id` matches the current user's `id_parent_user`, and then returns the parent user as the result.

To call this accessor for an instance of the `User` model, you can do this:

```php
$user = User::find(2);
$firstParentUser = $user->first_parent_user;
```

This will return the parent user of the current user. If the current user has no parent user, it will return `null`.

### `getFirstChildUserAttribute`

To define the `getFirstChildUserAttribute` accessor, you can add the following code to the `User` model:

```php
public function getFirstChildUserAttribute()
{
    return $this->childUsers()->first();
}
```

In this code, `getFirstChildUserAttribute` uses the `childUsers` relationship to find the users whose `id_parent_user` matches the current user's `id`, and then returns the first user found as the result.

To call this accessor for an instance of the `User` model, you can do this:

```php
$user = User::find(1);
$firstChildUser = $user->first_child_user;
```

This will return the first user whose `id_parent_user` matches the current user's `id`. If no such user exists, it will return `null`.
