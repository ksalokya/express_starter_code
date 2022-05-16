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
