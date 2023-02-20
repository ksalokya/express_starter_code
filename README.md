```js
const express = require("express");
const bodyParser = require("body-parser");

const port = process.env.PORT || 5000;
const app = express();

app.use(bodyParser.urlencoded({extended: true}));
app.use(bodyParser.json());

app.get("/", function (req, res) {
    res.send("Hello World");
});

app.get("*", function (req, res) {
    res.redirect("/");
});

app.listen(port, function () {
    console.log(`Serve at http://localhost:${port}`);
});
```
```js
{
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "nodemon index.js"
  },
  "dependencies": {
    "body-parser": "^1.20.0",
    "dotenv": "^16.0.0",
    "express": "^4.18.1",
    "mongoose": "^6.3.3",
    "nodemon": "^2.0.16"
  }
}
```
