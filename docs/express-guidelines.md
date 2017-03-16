Some guidelines for the node.js services, implementing a REST interface:

## File structure

```sh
PROJECT
  |-- src
    |-- config
    |-- helper
    |-- modules
      - moduleA
        - moduleA.controller.js
        - moduleA.model.js
        - moduleA.routes.js
  

```

## Environment:

- Settings environments: https://github.com/KunalKapadia/express-mongoose-es6-rest-api/tree/develop/config

## Error Handling

- [Use error middleware](https://expressjs.com/en/advanced/best-practice-performance.html)
- Customized Errors: https://github.com/KunalKapadia/express-mongoose-es6-rest-api
- Express Error Handler: https://github.com/ericelliott/express-error-handler

## Performance

- [Always use compression](https://expressjs.com/en/advanced/best-practice-performance.html)

## Security

- Use [helmet](https://github.com/helmetjs/helmet) to secure the express app
- Use TLS: https://strongloop.com/strongblog/best-practices-for-express-in-production-part-one-security/

## Documentation

## Logging

## HATEOAS

- https://www.npmjs.com/package/hyperjson
- https://github.com/kevinswiber/siren
- https://github.com/collection-json/spec
- http://json-ld.org/

## Future ideas:

- Follow json-api ?

## References

The guidelines above are created based on the following resources:

- Security: https://strongloop.com/strongblog/best-practices-for-express-in-production-part-one-security/
- Error Handling: https://strongloop.com/strongblog/async-error-handling-expressjs-es7-promises-generators/
- Best practices apps:
  - https://github.com/madhums/node-express-mongoose-demo
  - https://github.com/KunalKapadia/express-mongoose-es6-rest-api