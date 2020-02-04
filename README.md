# Trailing slash experiments

This repo demonstrates the inconsistencies between [now dev](https://github.com/zeit/now),
[serve](https://github.com/zeit/serve-handle) and
[superstatic](https://github.com/firebase/superstatic)
when using the `trailingSlash` configuration option set to `true`

## TLDR:
1) now redirects with a `308` status, serve and superstatic redirects with a `301` status.
2) now will redirect files (eg /style.css) to trailing slash. Serve and
superstatic do not.



## now dev

Running `now dev` command

### CSS FILE:

```
Request URL: http://localhost:3000/style.css
Request method: GET
Status code: 308
```

redirects to =>

```
Request URL:http://localhost:3000/style.css/
Request method: GET
Status code: 200
```

### TEST DIRECTORY:

```
Request URL:http://localhost:3000/test
Request method:GET
Status code: 308
```

redirects to =>


```
Request URL:http://localhost:3000/test/
Request method:GET
Status code: 200
```

## serve & superstatic

Running `serve` or `superstatic` command

### CSS FILE

```
Request URL:http://localhost:3000/style.css
Request method: GET
Status code: 200
```

### TEST DIRECTORY:
```
Request URL:http://localhost:5000/test
Request method:GET
Status code: 301
```

redirects to =>

```
Request URL:http://localhost:5000/test/
Request method:GET
Status code: 200
```
