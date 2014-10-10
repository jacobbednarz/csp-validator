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
