### `concat`

`concat` is a method in the `Illuminate\Support\Collection` class that allows you to merge two collections together and create a new collection.

For example, using `concat`, you can merge two collections together and create a new collection that contains all elements of these two collections.

```php
$collection1 = collect(['apple', 'banana', 'orange']);
$collection2 = collect(['grape', 'mango', 'kiwi']);
$mergedCollection = $collection1->concat($collection2);
```

In this example, we create two collections and then merge them together using `concat`. The resulting collection contains all elements of the two collections, "apple", "banana", "orange", "grape", "mango" and "kiwi".
