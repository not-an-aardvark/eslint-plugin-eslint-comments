# requires a `eslint-enable` comment for every `eslint-disable` comment (eslint-comments/disable-enable-pair)

`eslint-disable` directive-comments disable ESLint rules in all lines preceded by the comment.
If you forget `eslint-enable` directive-comment, you may overlook ESLint warnings unintentionally.

This rule warns `eslint-disable` directive-comments if the `eslint-enable` directive-comment for that does not exist.

## Rule Details

Examples of :-1: **incorrect** code for this rule:

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */
var foo = bar()
```

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */ "※ Requires 'eslint-enable' directive for 'no-undef'."
var foo = bar()
/*eslint-enable no-unused-vars */
```

Examples of :+1: **correct** code for this rule:

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */
var foo = bar()
/*eslint-enable no-undef, no-unused-vars */
```

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */
var foo = bar()
/*eslint-enable*/
```
