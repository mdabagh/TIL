# Session and Cookie in Laravel

## Introduction
Session and Cookie are two important mechanisms used for storing user information on the server side. In Laravel, Session is used to maintain user login status, while Cookie is used to store a unique identifier that allows Laravel to retrieve the user's Session information. 

## Session and Cookie
Session is a mechanism for storing user information on the server side. It allows for the storage of user information across multiple requests and pages. In Laravel, Session information is stored in a temporary file on the server, typically in the `tmp` directory. By default, Sessions are destroyed after a set amount of time (usually 20 minutes) or when the user logs out. 

On the other hand, a Cookie is a small file that is stored on the user's computer and contains information that can be read by the server. In Laravel, a Cookie is used to store a unique identifier that allows Laravel to retrieve the user's Session information.

## Session and Cookie Interaction
When a user logs in, Laravel creates a new Session and stores the user's login status in the Session. Additionally, Laravel sends a Cookie with a unique identifier to the user's browser. When the user visits other pages on the site, the identifier in the Cookie is sent with the request, and Laravel uses it to retrieve the user's Session information. 

When the user logs out, Laravel destroys the Session on the server side and removes the Cookie from the user's browser. This ensures that the user's login status is completely removed from the system.

## Laravel Login Persistence
To keep the user logged in for an extended period of time, Laravel uses the `remember me` feature. This feature allows Laravel to create a long-lived Cookie that is valid for a set amount of time (usually 30 days). This Cookie is used to automatically log the user back in when they revisit the site, even if they have closed their browser or their Session has expired.

```php
// Creating a new Session
session(['user_id' => 1]);

// Retrieving Session data
$user_id = session('user_id');

// Creating a new Cookie
$response->cookie('laravel_session', $session_id, 60);

// Retrieving Cookie data
$session_id = $request->cookie('laravel_session');

// Using the 'remember me' feature
Auth::attempt(['email' => $email, 'password' => $password], $remember);
```

## Conclusion
Sessions and Cookies are important mechanisms for storing user information on the server side. In Laravel, Sessions are used to maintain user login status, while Cookies are used to store a unique identifier that allows Laravel to retrieve the user's Session information. By working together, Sessions and Cookies provide a seamless user experience. In addition, Laravel uses the `remember me` feature to keep the user logged in for an extended period of time.

# سشن و کوکی در لاراول

## مقدمه
سشن و کوکی دو مکانیزم مهم برای ذخیره اطلاعات کاربر در سمت سرور هستند. در لاراول، سشن برای نگهداری وضعیت لاگین کاربران استفاده می‌شود، در حالی که کوکی برای ذخیره یک شناسه منحصر به فرد استفاده می‌شود که به لاراول امکان بازیابی اطلاعات سشن کاربر را می‌دهد. 

## سشن و کوکی
سشن یک مکانیزم برای ذخیره اطلاعات کاربر در سمت سرور است. این مکانیزم امکان ذخیره اطلاعات کاربر را برای درخواست‌ها و صفحات متعدد فراهم می‌کند. در لاراول، اطلاعات سشن در یک فایل موقت در سمت سرور ذخیره می‌شود که معمولاً در دایرکتوری `tmp` قرار دارد. پس از گذشت زمانی مشخص (معمولاً ۲۰ دقیقه) یا در صورت خروج کاربر، سشن از حافظه سرور حذف می‌شود.

از سوی دیگر، کوکی یک فایل کوچک است که در کامپیوتر کاربر ذخیره می‌شود و شامل اطلاعاتی است که می‌تواند توسط سرور خوانده شود. در لاراول، کوکی برای ذخیره یک شناسه منحصر به فرد استفاده می‌شود که به لاراول امکان بازیابی اطلاعات سشن کاربر را می‌دهد.

## تعامل سشن و کوکی
سشن و کوکی هنگامی که کاربر لاگین می‌کند، تعامل دارند. لاراول یک سشن جدید ایجاد کرده و وضعیت لاگین کاربر را در سشن ذخیره می‌کند. به علاوه، لاراول یک کوکی با یک شناسه منحصر به فرد به مرورگر کاربر ارسال می‌کند. وقتی کاربر صفحات دیگری در سایت را باز می‌کند، شناسه موجود در کوکی با درخواست ارسال می‌شود و لاراول از آن برای بازیابی اطلاعات سشن کاربر استفاده می‌کند. 

هنگامی که کاربر خارج می‌شود، لاراول سشن را در سمت سرور حذف می‌کند و کوکی را از مرورگر کاربر حذف می‌کند. این اطمینان می‌دهد که وضعیت لاگین کاربر به صورت کامل از سیستم حذف می‌شود.

## حفظ وضعیت لاگین در لاراول
برای حفظ وضعیت لاگین کاربر به مدت طولانی، لاراول از ویژگی `remember me` استفاده می‌کند. این ویژگی به لاراول امکان ایجاد یک کوکی با مدت اعتبار مشخص (معمولاً ۳۰ روز) را می‌دهد. این کوکی برای ورود خودکار کاربر به سایت در صورت بازدید مجدد از سایت استفاده می‌شود، حتی اگر کاربر مرورگر خود را بسته یا سشن آن منقضی شده باشد.

```php
// ایجاد یک سشن جدید
session(['user_id' => 1]);

// بازیابی اطلاعات سشن
$user_id = session('user_id');

// ایجاد یک کوکی جدید
$response->cookie('laravel_session', $session_id, 60);

// بازیابی اطلاعات کوکی
$session_id = $request->cookie('laravel_session');

// استفاده از ویژگی 'remember me'
Auth::attempt(['email' => $email, 'password' => $password], $remember);
```

## نتیجه‌گیری
سشن و کوکی به عنوان دو مکانیزم مهم برای ذخیره اطلاعات کاربر در سمت سرور، بسیار مهم هستند. در لاراول، سشن برای نگهداری وضعیت لاگین کاربران استفاده می‌شود، در حالی
