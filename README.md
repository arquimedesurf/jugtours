# Angular and Spring Boot CRUD Example

This example app shows how to create a Spring Boot API and CRUD (create, read, update, and delete) its data with an Angular app.

**Prerequisites:** [Java 17](http://sdkman.io) and [Node.js 18+](https://nodejs.org/)

* [Getting Started](#getting-started)
* [Links](#links)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/oktadev/auth0-spring-boot-angular-crud-example.git jugtours
cd jugtours
```

This will get a copy of the project installed locally. To install all of its dependencies and start each app, follow the instructions below.

To run the server, run:

```bash
mvn spring-boot:run
```

To run the client, cd into the `app` folder and run:

```bash
npm i && npm start
```

### Use Auth0 for OpenID Connect

Install the [Auth0 CLI](https://github.com/auth0/auth0-cli) and run `auth0 login` in a terminal.

Next, run `auth0 apps create`:

```shell
auth0 apps create \
  --name "Spring Boot 3.1" \
  --description "So Bootiful" \
  --type regular \
  --callbacks http://localhost:8080/login/oauth2/code/okta \
  --logout-urls http://localhost:8080 \
  --reveal-secrets
```

Copy the results from the CLI into an `okta.env` file:

```shell
export OKTA_OAUTH2_ISSUER=https://<your-auth0-domain>/
export OKTA_OAUTH2_CLIENT_ID=<your-client-id>
export OKTA_OAUTH2_CLIENT_SECRET=<your-client-secret>
```

If you're on Windows, name the file `okta.env.bat` and use `set` instead of `export`:

```shell
set OKTA_OAUTH2_ISSUER=https://<your-auth0-domain>/
set OKTA_OAUTH2_CLIENT_ID=<your-client-id>
set OKTA_OAUTH2_CLIENT_SECRET=<your-client-secret>
```

Then, run `source okta.env` (or run `okta.env.bat` on Windows) to set the environment variables. Start your app and log in at `http://localhost:8080`:

```shell
source okta.env
mvn spring-boot:run -Pprod
```

NOTE: You can also use your [Auth0 dashboard](https://manage.auth0.com) to configure your application. Just make sure to use the same URLs specified above.

## Links

This example uses the following open source libraries:

* [Angular](https://angular.io)
* [Spring Boot](https://spring.io/projects/spring-boot)
* [Spring Security](https://spring.io/projects/spring-security)

## Help

Please post any questions as comments on the [blog post](...), or visit our [Auth0 Community Forums](https://community.auth0.com/).

## License

Apache 2.0, see [LICENSE](LICENSE).
