## Features: (I implemented all features 😊)
- Authentication using Laravel Sanctum
- Developed all API endpoints for authentication, expense management and user management
- Role-based access control for Admins, Managers, Employees using Guards and Policies
- Optimized queries using indexes, eager loading and Redis for caching
- Configured Laravel scheduler and queues via Redis driver for background job processing
- Created a weekly job that sends an expense report in the form of e-mails to all Admins
- Added an audit log trait to track changes to expenses
- Designed feature tests using the Pest framework for expenses logic

## Update .env file
**Note:** Setup your database connection, mail credentials (I used Mailtrap for testing), queue connection and cache store to redis.

CACHE_STORE=redis

CACHE_PREFIX="cache:"

REDIS_CLIENT=predis

REDIS_PREFIX="multitenantexp:"

QUEUE_CONNECTION=redis

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=multi_tenant
DB_USERNAME=
DB_PASSWORD=

MAIL_MAILER=smtp
MAIL_SCHEME=null
MAIL_HOST=sandbox.smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_FROM_ADDRESS="no-reply@multitenant.ng"
MAIL_FROM_NAME="${APP_NAME}"

## Recommended setup instructions
> cp .env.example .env
> composer install
> composer dump-autoload
> php artisan migrate
> php artisan db:seed 

Recommendation: run _php artisan db:seed_ twice

## Run application
> php artisan serve
> php artisan schedule:run && php artisan queue:work 

Note: ensure your redis server is running

## Run tests
> php artisan test
