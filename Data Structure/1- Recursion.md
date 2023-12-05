تابع بازگشتی (Recursion)

```
c
#include <stdio.h>

int factorial(int n) {
    if(n == 0)
        return 1;
    else
        return n * factorial(n-1);
}

int main() {
    int num = 5;
    int result = factorial(num);
    printf("Factorial of %d is %d\n", num, result);
    return 0;
}
```

```
php
function factorial($n) {
    if($n == 0)
        return 1;
    else
        return $n * factorial($n-1);
}

$num = 5;
$result = factorial($num);
echo "Factorial of $num is $result";
```
