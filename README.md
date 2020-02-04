# trailing slash experiments

This repo demonstrates the inconsistencies between `now dev` and `serve` when
using the `trailingSlash` configuration option set to `true`


## now Dev

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

## serve

```
Request URL:http://localhost:3000/style.css
Request method: GET
Status code: 200
`








