### `unique`

`unique` is a method in the `Illuminate\Support\Collection` class that allows you to remove all duplicate records in a collection and keep only one instance of each record.

For example, using `unique`, you can compare all values in a column of a table and remove all duplicate records from the table.

```php
$users = collect([
    ['name' => 'John Doe', 'email' => 'john@example.com'],
    ['name' => 'Jane Doe', 'email' => 'jane@example.com'],
    ['name' => 'John Doe', 'email' => 'john.doe@example.com'],
    ['name' => 'Bob Smith', 'email' => 'bob@example.com'],
]);

$uniqueUsers = $users->unique('name');
```

In this example, we have a collection of users with some of them having the same name. We use `unique` to remove all duplicate users based on their names. As a result, we get a new collection with only two users, "John Doe" and "Jane Doe".
