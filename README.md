# trailing slash experiments

This repo demonstrates the inconsistencies between `now dev` and `serve` when
using the `trailingSlash` configuration option set to `true`

## TLDR:
1) Now redirects with a `308` status, serve redirects with a `301` status.
2) Now will redirect files (eg /style.css) to trailing slash. Serve does not.



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

## serve

Running `serve` command

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
