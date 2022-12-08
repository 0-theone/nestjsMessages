## Description
Basic CRUD API - Nest.js

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).

## Technical Information
Automatic Validation
- Use global validation
- Class that describes the different properties that the request body should have (DTO)
- Use validation rules in the class
- Apply class to the request handler

Packages
- class-transformer -> is a simple package that takes a plain object and converts it into an instance of a class.
link: https://www.npmjs.com/package/class-transformer

- class-validator -> allows use of decorator and non-decorator based validation. Internally uses validator.js to perform validation. Class-validator works on both browser and node.js platforms.
link: https://www.npmjs.com/package/class-validator

How validation works?
- Use class-transformer to turn the body into an instance of the DTO class
- Use class-validator to validate the instance
- If there are validation errors repsond immediately otherwise provide body to request handler. 

tsconfig.json
- "experimentalDecorators" -> this line of code in this configuration file allows a very small amount of type information to "make it" from the typescript world to the javascript world. 

Services
- It is a class
- #1 place to put any business logic
- Uses one or more repositories to find or store data

Repositories
- It is a class
- #1 place to put storage-related logic
- Usually ends up being a TypeORM entity, a Mongoose schema or similar

SOLID
- I -> Inversion of Control Principle: Classes should not create instances of its dependencies on its own

Nest Dependency Injection Container/Injector
- Contains list of classes and their dependencies (list: class1 -> dependencies1, class2 -> dependencies2, and so on...)
- Contains list of created instances

DI Container Flow
 - At startup, register all classes with the container
 - Container will figure out what each dependency each class has
 - Ask the container to create an instance of a class
 - Container creates all required dependencies and returns the instance
 - Container will hold onto the created dependency instances and reuse them if needed
 (The payout of all of these DI stuff is shown while writing tests =P)
