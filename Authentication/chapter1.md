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














