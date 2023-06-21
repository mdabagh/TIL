1. If statement: The if statement is used to execute a block of code if a certain condition is true. The basic syntax of an if statement is:
```
if (condition) {
  // code to be executed if the condition is true
}
```
Here's an example:
```
$age = 18;
if ($age >= 18) {
  echo "You are an adult.";
}
```

2. If-else statement: The if-else statement is used to execute a block of code if a certain condition is true, and another block of code if that condition is false. The basic syntax of an if-else statement is:
```
if (condition) {
  // code to be executed if the condition is true
} else {
  // code to be executed if the condition is false
}
```
Here's an example:
```
$age = 16;
if ($age >= 18) {
  echo "You are an adult.";
} else {
  echo "You are not an adult.";
}
```

3. If-elseif-else statement: The if-elseif-else statement is used to execute a block of code if a certain condition is true, another block of code if a different condition is true, and a default block of code if none of the conditions are true. The basic syntax of an if-elseif-else statement is:
```
if (condition1) {
  // code to be executed if condition1 is true
} elseif (condition2) {
  // code to be executed if condition2 is true
} else {
  // code to be executed if neither condition1 nor condition2 is true
}
```
Here's an example:
```
$age = 20;
if ($age < 18) {
  echo "You are a minor.";
} elseif ($age >= 18 && $age < 21) {
  echo "You are a young adult.";
} else {
  echo "You are an adult.";
}
```

4. While loop: The while loop is used to execute a block of code repeatedly while a certain condition is true. The basic syntax of a while loop is:
```
while (condition) {
  // code to be executed while the condition is true
}
```
Here's an example:
```
$i = 1;
while ($i <= 10) {
  echo $i;
  $i++;
}
```

5. For loop: The for loop is used to execute a block of code a specific number of times. The basic syntax of a for loop is:
```
for (initialization; condition; increment) {
  // code to be executed
}
```
Here's an example:
```
for ($i = 1; $i <= 10; $i++) {
  echo $i;
}
```

6. Foreach loop: The foreach loop is used to iterate over the elements of an array. The basic syntax of a foreach loop is:
```
foreach ($array as $value) {
  // code to be executed for each value in the array
}
```
Here's an example:
```
$fruits = array("apple", "banana", "orange");
foreach ($fruits as $fruit) {
  echo $fruit;
}
```

7. Switch statement: The switch statement is used to perform different actions based on different conditions. The basic syntax of a switch statement is:
```
switch (expression) {
  case value1:
    // code to be executed if expression matches value1
    break;
  case value2:
    // code to be executed if expression matches value2
    break;
  default:
    // code to be executed if none of the values match expression
}
```
Here's an example:
```
$day = "Monday";
switch ($day) {
  case "Monday":
    echo "Today is Monday.";
    break;
  case "Tuesday":
    echo "Today is Tuesday.";
    break;
  default:
    echo "Today is not Monday or Tuesday.";
}
```
