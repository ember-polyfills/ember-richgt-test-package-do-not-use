# ember-richgt-test-package-do-not-use

[![CI](https://github.com/ember-polyfills/ember-richgt-test-package-do-not-use/workflows/CI/badge.svg)](https://github.com/ember-polyfills/ember-richgt-test-package-do-not-use/actions)
[![npm version](https://badge.fury.io/js/ember-richgt-test-package-do-not-use.svg)](http://badge.fury.io/js/ember-richgt-test-package-do-not-use)
[![Download Total](https://img.shields.io/npm/dt/ember-richgt-test-package-do-not-use.svg)](http://badge.fury.io/js/ember-richgt-test-package-do-not-use)
[![Ember Observer Score](https://emberobserver.com/badges/ember-richgt-test-package-do-not-use.svg)](https://emberobserver.com/addons/ember-richgt-test-package-do-not-use)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![Dependabot enabled](https://img.shields.io/badge/dependabot-enabled-blue.svg?logo=dependabot)](https://dependabot.com/)
[![dependencies Status](https://david-dm.org/ember-polyfills/ember-richgt-test-package-do-not-use/status.svg)](https://david-dm.org/ember-polyfills/ember-richgt-test-package-do-not-use)
[![devDependencies Status](https://david-dm.org/ember-polyfills/ember-richgt-test-package-do-not-use/dev-status.svg)](https://david-dm.org/ember-polyfills/ember-richgt-test-package-do-not-use?type=dev)

Polyfill for [RFC 566 "@cached decorator"][rfc-566].

[rfc-566]: https://github.com/emberjs/rfcs/pull/566

## Installation

```bash
ember install ember-richgt-test-package-do-not-use
```

For addons, pass the `-S` flag.

## Compatibility

- Ember.js v3.13 or above
- Ember CLI v2.13 or above
- Node.js v10 or above

## Summary

Add a `@cached` decorator for memoizing the result of a getter based on
autotracking. In the following example, `fullName` would only recalculate if
`firstName` or `lastName` is updated.

```js
import { tracked, cached } from '@glimmer/tracking';

class Person {
  @tracked firstName = 'Jen';
  @tracked lastName = 'Weber';

  @cached
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  }
}
```

For detailed usage instructions, refer to the
[RFC 566 "@cached decorator"][rfc-566].

## TypeScript Usage

TypeScript's normal type resolution for an import from `@glimmer/tracking`
will **not** find the types provided by this polyfill, since the actual
`@glimmer/tracking` package does not include an export for `cache`.

In order for TypeScript to recognize the extra `cache` export, add an import
like this somewhere in your codebase (like `app.ts` or `test-helper.ts`):

```ts
import 'ember-richgt-test-package-do-not-use';
```

Once the upstream types have been updated to reflect RFC 566, this will no
longer be necessary.
