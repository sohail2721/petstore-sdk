# User

Operations about user

```php
$userController = $client->getUserController();
```

## Class Name

`UserController`

## Methods

* [Create User](../../doc/controllers/user.md#create-user)
* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Login User](../../doc/controllers/user.md#login-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Update User](../../doc/controllers/user.md#update-user)
* [Delete User](../../doc/controllers/user.md#delete-user)


# Create User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```php
function createUser(
    ?int $id = null,
    ?string $username = null,
    ?string $firstName = null,
    ?string $lastName = null,
    ?string $email = null,
    ?string $password = null,
    ?string $phone = null,
    ?int $userStatus = null
): User
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `?int` | Form, Optional | - |
| `username` | `?string` | Form, Optional | - |
| `firstName` | `?string` | Form, Optional | - |
| `lastName` | `?string` | Form, Optional | - |
| `email` | `?string` | Form, Optional | - |
| `password` | `?string` | Form, Optional | - |
| `phone` | `?string` | Form, Optional | - |
| `userStatus` | `?int` | Form, Optional | User Status |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```php
$id = 10;

$username = 'theUser';

$firstName = 'John';

$lastName = 'James';

$email = 'john@email.com';

$password = '12345';

$phone = '12345';

$userStatus = 1;

$result = $userController->createUser(
    $id,
    $username,
    $firstName,
    $lastName,
    $email,
    $password,
    $phone,
    $userStatus
);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Unexpected error | `ApiException` |


# Create Users With List Input

Creates list of users with given input array.

:information_source: **Note** This endpoint does not require authentication.

```php
function createUsersWithListInput(?array $body = null): User
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?(User[])`](../../doc/models/user.md) | Body, Optional | - |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```php
$body = [
    UserBuilder::init()->build()
];

$result = $userController->createUsersWithListInput($body);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Unexpected error | `ApiException` |


# Login User

Log into the system.

:information_source: **Note** This endpoint does not require authentication.

```php
function loginUser(?string $username = null, ?string $password = null): string
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `?string` | Query, Optional | The user name for login |
| `password` | `?string` | Query, Optional | The password for login in clear text |

## Response Type

`string`

## Example Usage

```php
$result = $userController->loginUser();
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `ApiException` |
| Default | Unexpected error | `ApiException` |


# Logout User

Log user out of the system.

:information_source: **Note** This endpoint does not require authentication.

```php
function logoutUser(): void
```

## Response Type

`void`

## Example Usage

```php
$userController->logoutUser();
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Unexpected error | `ApiException` |


# Get User by Name

Get user detail based on username.

:information_source: **Note** This endpoint does not require authentication.

```php
function getUserByName(string $usersname): User
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `usersname` | `string` | Template, Required | The username that needs to be processed |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```php
$usersname = 'usersname0';

$result = $userController->getUserByName($usersname);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiException` |
| 404 | User not found | `ApiException` |
| Default | Unexpected error | `ApiException` |


# Update User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```php
function updateUser(
    string $usersname,
    ?int $id = null,
    ?string $username = null,
    ?string $firstName = null,
    ?string $lastName = null,
    ?string $email = null,
    ?string $password = null,
    ?string $phone = null,
    ?int $userStatus = null
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `usersname` | `string` | Template, Required | The username that needs to be processed |
| `id` | `?int` | Form, Optional | - |
| `username` | `?string` | Form, Optional | - |
| `firstName` | `?string` | Form, Optional | - |
| `lastName` | `?string` | Form, Optional | - |
| `email` | `?string` | Form, Optional | - |
| `password` | `?string` | Form, Optional | - |
| `phone` | `?string` | Form, Optional | - |
| `userStatus` | `?int` | Form, Optional | User Status |

## Response Type

`void`

## Example Usage

```php
$usersname = 'usersname0';

$id = 10;

$username = 'theUser';

$firstName = 'John';

$lastName = 'James';

$email = 'john@email.com';

$password = '12345';

$phone = '12345';

$userStatus = 1;

$userController->updateUser(
    $usersname,
    $id,
    $username,
    $firstName,
    $lastName,
    $email,
    $password,
    $phone,
    $userStatus
);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad request | `ApiException` |
| 404 | user not found | `ApiException` |
| Default | Unexpected error | `ApiException` |


# Delete User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteUser(string $usersname): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `usersname` | `string` | Template, Required | The username that needs to be processed |

## Response Type

`void`

## Example Usage

```php
$usersname = 'usersname0';

$userController->deleteUser($usersname);
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiException` |
| 404 | User not found | `ApiException` |
| Default | Unexpected error | `ApiException` |

