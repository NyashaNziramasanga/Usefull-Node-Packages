# Useful Node Packages

List of useful node packages

## [Express](https://www.npmjs.com/package/express)

A Node Web framework

Usage:

``` javascript
npm i express --save

const express = require('express')
const app = express()

app.get('/', function (req, res) {
  res.send('Hello World')
})

app.listen(3000)
```

## [Lodash](https://www.npmjs.com/package/lodash)

A modern JavaScript utility library delivering modularity, performance & extras

Usage:

```bash
npm i -g npm
npm i --save lodash
```

## [Mongoose](https://www.npmjs.com/package/mongoose)

MongoDB object modeling tool designed to work in an asynchronous environment

Usage:

```bash
npm i mongoose
```

## [Slugify](https://www.npmjs.com/package/slugify)

Create friendly url names

## [Node-geocoder](https://www.npmjs.com/package/node-geocoder)

Add geocodes from address provided

## [Express fileupload](https://www.npmjs.com/package/express-fileupload)

Middleware for handling file uploads

Usage:

```javascript
npm i express-fileupload

app.post('/upload', function(req, res) {
  console.log(req.files.foo); // the uploaded file object
});
```

## [Colors](https://www.npmjs.com/package/colors)

Styling node.js console logs

Usage:

```javascript
npm i colors

const colors = require('colors');
console.log('test'.green.inverse);
```

## [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)

Usage:

```javascript
npm i jsonwebtoken

const jwt = require('jsonwebtoken');

UserSchema.methods.getSignedJwtToken = function() {
  return jwt.sign(
    { id: this._id,},
    'theosdasdnadaf',
    { expiresIn: 30d }
  );
};
```

## [bcryptjs](https://www.npmjs.com/package/bcryptjs)

Password hashing

Usage:

```javascript
npm i bcryptjs

const bcrypt = require('bcryptjs');

UserSchema.pre('save', async function(next) {
  const salt = await bcrypt.genSalt(10);
  this.password = await bcrypt.hash(this.password, salt);
});
```

## [cookie-parser](https://www.npmjs.com/package/cookie-parser)

Storing/set tokens on cookies

```javascript
npm i cookie-parser

// Cookie parser in Server.js file
const express = require('express')
const cookieParser = require('cookie-parser')

const app = express()
app.use(cookieParser())
```

## [nodemailer](https://www.npmjs.com/package/nodemailer)

Sending emails

```javascript
npm i nodemailer

const nodemailer = require('nodemailer');

const sendEmail = async (options) => {
  const transporter = nodemailer.createTransport({
    host: process.env.SMTP_HOST,
    port: process.env.SMTP_PORT,
    auth: {
      user: process.env.SMTP_EMAIL,
      pass: process.env.SMTP_PASSWORD,
    },
  });

  const message = {
    from: `${process.env.FROM_NAME} <${process.env.FROM_EMAIL}>`,
    to: options.email,
    subject: options.subject,
    text: options.message,
  };

  const info = await transporter.sendMail(message);

  console.log('Message sent: %s', info.messageId);
};

module.exports = sendEmail;

```

## [crypto](https://nodejs.org/api/crypto.html#crypto_determining_if_crypto_support_is_unavailable)

Standard node module for cryptographic functionality (Password resets, tokens)

```javascript
const crypto = require('crypto');

const resetPasswordToken = crypto
 .createHash('sha256')
 .update(req.params.resettoken)
 .digest('hex');
```

## [passport](http://www.passportjs.org/packages/passport-google-oauth/)

Authentication middleware which support username & password, Facebook and Google

```javascript
npm install passport

passport.authenticate('facebook')
```

## [react-chart.js](http://jerairrest.github.io/react-chartjs-2/)

Most popular chart javascript library for bar charts, scatter charts etc

```javascript
npm install react-chartjs-2 chart.js

import { Bar } from 'react-chartjs-2';

<Bar
  data={data}
  width={100}
  height={50}
  options={{ maintainAspectRatio: false }}
/>
```

## [clipboard.js](https://clipboardjs.com/)

A modern approach to copy text to clipboard

```javascript
npm install clipboard
```

## [puppeteer](https://pptr.dev/)

Headless Chrome Node.js API which can be used to control Chrome or Chromium

```javascript
// Downloads recent version of chromium (~170mb)
npm i puppeteer

//Light version which doesn't download chromium
npm i puppeteer-core

const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```

## [depcheck](https://www.npmjs.com/package/depcheck)

Check for unused npm dependencies

```bash
npm install -g depcheck

depcheck [directory] [arguments]
```


## [express-mongo-sanitize](https://www.npmjs.com/package/express-mongo-sanitize) (Security)

Sanitizes user-supplied data to prevent MongoDB Operator Injection

```bash
npm i express-mongo-sanitize
```
```javascript
// Example Vulneralbility
{
    "email":{"$gt":""},
    "password": "123456"
}
```

```javascript
//Usage
 mongoSanitize = require('express-mongo-sanitize');
 app.use(mongoSanitize());
```
## [helmet](https://www.npmjs.com/package/helmet) (Security)

Secure your Express apps by setting various HTTP headers

```bash
npm i helmet
```

```javascript
//Usage
const helmet = require('helmet')
app.use(helmet())
 ```
## [xss-clean](https://www.npmjs.com/package/xss-clean) (Security)

Middleware to sanitize user input coming from POST body, GET queries, and url params

```bash
npm i xss-clean
```

```javascript
//Usage
const xss = require('xss-clean')
app.use(xss())
 ```
 
## [express-rate-limit](https://www.npmjs.com/package/express-rate-limit) (Security)

Basic rate-limiting middleware for Express. Used to limit repeated requests to public APIs 

```bash
npm i express-rate-limit
```

```javascript
//Usage
const rateLimit = require("express-rate-limit");
  
const limiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100 // limit each IP to 100 requests per windowMs
});
 
//  apply to all requests
app.use(limiter);
 ```
 ## [hpp](https://www.npmjs.com/package/hpp) (Security)

Middleware to protect against HTTP Parameter Pollution attacks

```bash
npm i hpp
```

```javascript
//Usage
const hpp = require('hpp');
app.use(hpp());
 ```
 
## [cors](https://www.npmjs.com/package/cors)

middleware that can be used to enable CORS with various options

```bash
npm i cors
```

```javascript
//Usage
const cors = require('cors');
app.use(cors());
 ```
