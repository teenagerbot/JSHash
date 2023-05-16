# JSHash

Using this library, you can encrypt any text and digital data both on the client and on the server, javascript and Node.js are supported

## Data encryption on the client:
To encrypt data on the client, we can include a file:
```html
...
<script src="https://cdn.jsdelivr.net/npm/js-hash-encoding@1.0.4/index.min.js"></script>
<script>
  //create an instance of the encryption object
  const hashLib = new JSHash();
  //and now we encrypt the data
  console.log(hashLib.encode("hello world")) // 26496
  console.log(hashLib.encode(1)) // 3328
  console.log(hashLib.encode("")) // 0
  console.log(hashLib.encode(true)) // 8666
  console.log(hashLib.encode(false)) // 12250
  console.log(hashLib.encode()) // 17985
  console.log(hashLib.encode({
    user: "bot"
  })) // 33447
  console.log(hashLib.encode([1, -344, "j", [4, "k"]])) // 16821
  //get hash code of string, object, array, number:
  console.log(hashLib.getHashCode([8])) // 89280
</script>
```

Please note that this library turns any data types into a number and this library encrypts data in one direction, creating a so-called hash, so it is impossible to decrypt it back, there is no algorithm:
```js
typeof(hashLib.encode()) // Number
```

## Data encryption on the server:

```js
const hashLib = require("js-hash-encoding");
console.log(hashLib.encode("hello world")) // 26496
console.log(hashLib.getHashCode([8])) // 89280
```

You can also import and generate a random user agent on the server (useful for parsing):
```js
const userAgent = require("@node_dev_php/useragent-js");
console.log(userAgent.getRandomUserAgent()) // "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:30.0) Gecko/20100101 Firefox/30.0"
```
