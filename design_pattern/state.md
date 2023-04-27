# Laravel Eloquent Scopes

With query scopes, you can have shorter, more meaningful and more beautiful queries in Eloquent.
We have two types of scopes. Global Scope and Local Scope.


Global Scope:
```bash
<?php

namespace App\Scopes;

use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\Scope;
use Illuminate\Database\Eloquent\Builder;

class Published implements Scope
{
    public function apply(Builder $builder, Model $model)
    {
        // return $builder->where('status', 'published');
    }
}
```

```bash
<?php

namespace App\Models;

// ...
use App\Scopes\Published;

class Post extends Model
{
    // ...

    protected static function booted()
    {
        static::addGlobalScope(new Published());
    }
}
```

```bash
Post::all(); //select * from `post` where `status` = "published"
```


Local Scope:

```bash
<?php

namespace App\Models;

// ...
use App\Scopes\Published;

class Post extends Model
{
    // ...

    public function scopePublished($query)
    {
      return $query->where('status', 'published');
    }
}
```

```bash
Post::published()->get();
```
