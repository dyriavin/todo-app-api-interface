+--------+-----------+-----------------------------------------+-----------------------------------+---------------------------------------------------------------------------+------------+
| Domain | Method    | URI                                     | Name                              | Action                                                                    | Middleware |
+--------+-----------+-----------------------------------------+-----------------------------------+---------------------------------------------------------------------------+------------+
|        | GET|HEAD  | /                                       |                                   | Closure                                                                   | web        |
|        | POST      | api/login                               |                                   | App\Http\Controllers\Api\AuthController@login                             | api        |
|        | POST      | api/register                            |                                   | App\Http\Controllers\Api\AuthController@register                          | api        |
|        | POST      | api/todos                               | todos.store                       | App\Http\Controllers\TodoController@store                                 | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/todos                               | todos.index                       | App\Http\Controllers\TodoController@index                                 | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/todos/create                        | todos.create                      | App\Http\Controllers\TodoController@create                                | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | DELETE    | api/todos/{todo}                        | todos.destroy                     | App\Http\Controllers\TodoController@destroy                               | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | PUT|PATCH | api/todos/{todo}                        | todos.update                      | App\Http\Controllers\TodoController@update                                | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/todos/{todo}                        | todos.show                        | App\Http\Controllers\TodoController@show                                  | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/todos/{todo}/edit                   | todos.edit                        | App\Http\Controllers\TodoController@edit                                  | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | POST      | api/todos/{todo}/status                 |                                   | App\Http\Controllers\TodoController@updateStatus                          | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | POST      | api/todos/{todo}/user                   |                                   | App\Http\Controllers\TodoController@updateUser                            | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | POST      | api/users                               | users.store                       | App\Http\Controllers\UsersController@store                                | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/users                               | users.index                       | App\Http\Controllers\UsersController@index                                | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/users/create                        | users.create                      | App\Http\Controllers\UsersController@create                               | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/users/{user}                        | users.show                        | App\Http\Controllers\UsersController@show                                 | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | PUT|PATCH | api/users/{user}                        | users.update                      | App\Http\Controllers\UsersController@update                               | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | DELETE    | api/users/{user}                        | users.destroy                     | App\Http\Controllers\UsersController@destroy                              | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | api/users/{user}/edit                   | users.edit                        | App\Http\Controllers\UsersController@edit                                 | api        |
|        |           |                                         |                                   |                                                                           | auth:api   |
|        | GET|HEAD  | oauth/authorize                         | passport.authorizations.authorize | Laravel\Passport\Http\Controllers\AuthorizationController@authorize       | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | DELETE    | oauth/authorize                         | passport.authorizations.deny      | Laravel\Passport\Http\Controllers\DenyAuthorizationController@deny        | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | POST      | oauth/authorize                         | passport.authorizations.approve   | Laravel\Passport\Http\Controllers\ApproveAuthorizationController@approve  | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | POST      | oauth/clients                           | passport.clients.store            | Laravel\Passport\Http\Controllers\ClientController@store                  | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | GET|HEAD  | oauth/clients                           | passport.clients.index            | Laravel\Passport\Http\Controllers\ClientController@forUser                | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | DELETE    | oauth/clients/{client_id}               | passport.clients.destroy          | Laravel\Passport\Http\Controllers\ClientController@destroy                | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | PUT       | oauth/clients/{client_id}               | passport.clients.update           | Laravel\Passport\Http\Controllers\ClientController@update                 | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | POST      | oauth/personal-access-tokens            | passport.personal.tokens.store    | Laravel\Passport\Http\Controllers\PersonalAccessTokenController@store     | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | GET|HEAD  | oauth/personal-access-tokens            | passport.personal.tokens.index    | Laravel\Passport\Http\Controllers\PersonalAccessTokenController@forUser   | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | DELETE    | oauth/personal-access-tokens/{token_id} | passport.personal.tokens.destroy  | Laravel\Passport\Http\Controllers\PersonalAccessTokenController@destroy   | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | GET|HEAD  | oauth/scopes                            | passport.scopes.index             | Laravel\Passport\Http\Controllers\ScopeController@all                     | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | POST      | oauth/token                             | passport.token                    | Laravel\Passport\Http\Controllers\AccessTokenController@issueToken        | throttle   |
|        | POST      | oauth/token/refresh                     | passport.token.refresh            | Laravel\Passport\Http\Controllers\TransientTokenController@refresh        | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | GET|HEAD  | oauth/tokens                            | passport.tokens.index             | Laravel\Passport\Http\Controllers\AuthorizedAccessTokenController@forUser | web        |
|        |           |                                         |                                   |                                                                           | auth       |
|        | DELETE    | oauth/tokens/{token_id}                 | passport.tokens.destroy           | Laravel\Passport\Http\Controllers\AuthorizedAccessTokenController@destroy | web        |
|        |           |                                         |                                   |                                                                           | auth       |
+--------+-----------+-----------------------------------------+-----------------------------------+---------------------------------------------------------------------------+------------+
