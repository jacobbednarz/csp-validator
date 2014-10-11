# Content security policy validator

While rolling out a content security policy, I failed to find any good validators on the interwebz that managed to pick up things like deprecation warnings and best practices. Here is my solution.

### Installation

    git clone git@github.com:jacobbednarz/csp-validator.git

### Usage

The executable accepts either a URL or a string inline. Examples:

```sh
# As an inline string
./validate-csp "default-src *; img-src cdn.domain.com assets.domain.com"

# URL of a page.
./validate-csp http://google.com
```

### Checks

The following checks are run:

- Ensure a 'default-src' is available (for any missing directives).
- Malformed URL's.
- Deprecation of directives.

### Example

    $ ./validate-csp http://example.com

    [ ✔︎ ] 'default-src' is present.
    [ ✔︎ ] 'script-src' was found.
    [ ✔︎ ] 'object-src' was found.
    [ ✔︎ ] 'img-src' was found.
    [ ✔︎ ] 'media-src' was found.
    [ ✔︎ ] 'frame-src' was found.
    [ ✔︎ ] 'font-src' was found.
    [ ✔︎ ] 'frame-ancestors' was found.
    [ ✔︎ ] 'connect-src' was found.
    [ ✔︎ ] 'style-src' was found.
    [ ✻ ] 'frame-src' is being deprecated in favour of 'child-src' - See http://bit.ly/1uTJ3Ye.
    [ ✔︎ ] Violation reporting endpoint found.
