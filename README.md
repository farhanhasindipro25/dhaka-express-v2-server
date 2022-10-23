### SERVER SIDE Setup
**dhaka-express-v2-server**

1. Make a directory and change directory to the project file.

```
$ mkdir dhaka-express-v2-server
$ cd dhaka-express-v2-server
```

2. Initialize the node package manager (npm).
**This will open a 'package.json' file**

```
$ npm init -y
```

3. Make an 'index.js' file.
4. Install the node.js framework express.js

```
npm i express
```

5. Write the following code in the 'index.js' file.

```
const express = require("express");
const app = express();
const port = process.env.PORT || 5000;

app.get("/", (req, res) => {
  res.send("News API Running");
});

app.listen(port, () => {
  console.log("Dhaka Express Server running on port:", port);
});

```

6. Turn on the Node Monitor.

```
nodemon index.js
```

7. Make a folder 'data'. Make a file 'categories.json' inside the 'data' folder.

8. In the 'index.js' file, add:

```
const categories = require("./data/categories.json");

app.get("/news-categories", (req, res) => {
  res.send(categories);
});
```

### Loading/Fetching data from the server side API on the Client Side.

1. Install CORS
2. In the 'index.js' file,

```
const cors = require('cors');
app.use(cors());
```