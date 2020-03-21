# ClojureScript Nodejs export bug

The latest version of ClojureScript does not export correctly for NodeJS target.

Bug manifest after commit:

> `e25ced97af3c15a87afcb15165508aa23e54a3fa`

Seems to be related to the changes in commit:

> `3a0c07477ae781bf521bdc2b074ed7b783bb93f3`

## Examples

The following works.

```
$ clj -A:build:works
$ node run.js
```

This doesn't work.

```
$ clj -A:build:broke
$ node run.js
```

Browser target seems fine. This works:

```
$ clj -A:build-browser:broke
$ http-server
```