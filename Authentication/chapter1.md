### Convert simple password to hash

```javascript
const express = require("express");
const app = express();

const bcrypt = require("bcryptjs");

let userName = "Abhinish Kumar";
let password = "12345";

async function hashPasword() {
  let pass = await bcrypt.hash(password, 12);
  console.log(pass); //$2a$12$jKWox4OWq5ERx1HXPJRrqeK/GlryLNMdjndnIDDBL3cltRoqdRzkG
}

hashPasword();  

app.listen(3300);

```

Store this hashed password in Database

### Cmpare password to the password store in dataBase


```javascript

const express = require("express");
const app = express();

const bcrypt = require("bcryptjs");

let dbPassword = "$2a$12$.YSUsNFYJXzYVb.cVgXI7Oo1pTYTZ0sBgkOPIZPt0K33LgoFeofFK";

let userName = "Abhinish Kumar";
let password = "12345";

async function isValidUser(params) {
  let isValid = false;

  isValid = await bcrypt.compare(password, dbPassword);
  console.log(isValid); //true
}

isValidUser();

// async function isValidUser(params) {
//             let isValid = false;

//             isValid = await bcrypt.compare(
//               "12345",
//               "$2a$12$.YSUsNFYJXzYVb.cVgXI7Oo1pTYTZ0sBgkOPIZPt0K33LgoFeofFK"
//             );
//             console.log(isValid);
//           }

app.listen(3300);

```











