# NodeJS JWT Authentication sample

This is a NodeJS API that supports email and password authentication with JWTs and has APIs that return Chuck Norris phrases. How awesome is that?

## Available APIs

### User APIs

#### POST `/users`

You can do a POST to `/users` to create a new user.

The body must have:

* `email`: The email
* `password`: The password
* `extra`: Some extra information you want to save from the user (It's a string). This could be a color or anything at all.

It returns the following:

```json
{
  "id_token": {jwt},
  "access_token": {jwt}
}
```

The `id_token` and `access_token` are signed with the secret located at the `config.json` file. The `id_token` will contain the `email` and the `extra` information sent, while the `access_token` will contain the `audience`, `jti`, `issuer` and `scope`.

#### POST `/sessions/create`

You can do a POST to `/sessions/create` to log a user in.

The body must have:

* `email`: The email
* `password`: The password

It returns the following:

```json
{
  "id_token": {jwt},
  "access_token": {jwt}
}
```

The `id_token` and `access_token` are signed with the secret located at the `config.json` file. The `id_token` will contain the `email` and the `extra` information sent, while the `access_token` will contain the `audience`, `jti`, `issuer` and `scope`.

## Running it

Just clone the repository, run `npm install` and then `node server.js`. That's it :).

If you want to run it on another port, just run `PORT=3001 node server.js` to run it on port 3001 for example

## Issue Reporting

If you have found a bug or if you have a feature request, please report them at this repository issues section. Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## Author

[Auth0](auth0.com)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.