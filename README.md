# Node ES6 REST Template

The purpose of this template is to kick-start your Node.js projects using ES6.
It implements best practices in developing RESTful APIs and Domain-Driven
Design. Features include:

-   Use of the
    [Hexagonal Architecture](http://alistair.cockburn.us/Hexagonal+architecture)
    to arrange the application into logical layers, with well-defined
    responsibilities.
-   RESTful APIs are implemented using the [Express](http://expressjs.com/)
    framework.
-   Persistence is implemented using an in-memory repository layer. This can be
    substituted with any persistence technology of your choice.

## Dev Build

```bash
$ npm install
$ npm start
```

To verify that the application is working correctly, point your browser to
[http://localhost:8080/api/books/design-patterns](http://localhost:8080/api/books/design-patterns) -
you should see a response with one books in JSON format.

## Production Build

```bash
$ npm run build
$ npm serve
```

## Folder Structure

```
/src
    /adapters
    /services
    /repositories
```

The source folder contains sub-folders that arrange the application into logical
layers as suggested by the
[Hexagonal Architecture](http://alistair.cockburn.us/Hexagonal+architecture)
(a.k.a. the
[Onion Architecture](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/)):

-   `routes:` This is the adapter layer of the Hexagonal Architecture. It adapts
    the HTTP transforms the HTTP requests from the external world to the service
    layer and transforms the objects returned by the service layer to HTTP
    responses.

-   `services`: The service layer coordinates high-level activities such as
    creation of domain objects and asking them to perform tasks requested by the
    external world. It interacts with the repository layer to save and restore
    objects.

-   `repositories`: The repository layer is responsible for persisting domain
    objects and performing CRUD operations on them. This template uses in-memory
    persistence, however it can be easily replaced to use a relational or NoSQL
    database.

-   The `utils` folder contains useful utilities and helpers.
