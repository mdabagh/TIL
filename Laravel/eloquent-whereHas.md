## Example of using `whereHas` in Laravel's Eloquent ORM

Let's say you have a `Post` model that has relationships with `User` and `Category` models. You want to retrieve only the posts that are related to a specific user ID and also belong to a category with a specific name. To achieve this, you can use the `whereHas` method in Laravel's Eloquent ORM. Here's an example code:

```php
$userSelected = $request->input('userSelected');
$categoryName = $request->input('categoryName');

$posts = \App\Models\Post::whereHas('user', function($query) use ($userSelected) {
    $query->where('id', $userSelected);
})->whereHas('category', function($query) use ($categoryName) {
    $query->where('name', $categoryName);
})->get();
```

In this code, we're using `whereHas` to filter the `Post` model based on its relationships. With `function($query)`, we create a separate query for each relationship. Here, with `whereHas('user', ...)`, we filter the `User` relationship and retrieve models where the user ID matches `$userSelected`. Then, with `whereHas('category', ...)`, we filter the `Category` relationship and retrieve models where the category name matches `$categoryName`.

Finally, by calling `get()`, we create a collection of filtered `Post` models. These models are returned as an instance of the `Illuminate\Database\Eloquent\Collection` class. You can perform further operations on this collection as needed. For more information, you can refer to the Laravel documentation on [Querying Relationship Existence](https://laravel.com/docs/8.x/eloquent-relationships#querying-relationship-existence).
