
## Environment Variables

- `PORT` - Defines the by default exposed port (defaults to a specific port as documented in the project).
- `NODE_ENV` - For node.js services (defaults to `development`).

## Labels

- `io.sammler.env` - Environment (used for logging purposes)

## Paths

### Installation Path

- `/opt/<app-name>` - Location for custom apps
- `/opt/<app-name>/config` - Custom configuration files (if needed)

References:

- [Filesystem Hierarchy Standard](http://refspecs.linuxfoundation.org/FHS_2.3/fhs-2.3.html)
- [Linux Standard Base](http://en.wikipedia.org/wiki/Linux_Standard_Base)
- [Stackoverflow discussion](https://unix.stackexchange.com/questions/127076/into-which-directory-should-i-install-programs-in-linux)