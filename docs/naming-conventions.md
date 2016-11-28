## Naming convention for services & GitHub repos

- `sammler-*` - Core services
- `sammler-nodelib-*` - node.js libraries
- `sammler-golib-*` - GoLang libraries.
- `sammler-middleware-*` - Pluggable middleware
- `sammler-middleware-{service}-db` - Storage for the given middleware.
- `sammler-middleware-{service}-{dep}` - Other dependent service for the given middleware.