# About this content

- hey
- look
- this is written in markdown  

<br>

```javascript
// what's going on here
() => {console.log("here is a codeblock")}
const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
  bodyParser.parse(req, (error, body) => {
    res.end(body)
  })
}).listen(3000)
```

<br>

## Text block heading
We author plain documentation in a text format.


