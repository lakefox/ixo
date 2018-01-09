# ixo
ixo.js is a blockchain designed to be light weight and efficient. The purpose of ixo was to server as a immutable datastore that can be proven and to maintain privacy for your companies needs. We are building the first ever plug and play blockchain that once setup will run at exceptionally fast speeds.

### Installation
```
npm install ixo
```

### Basic Usage
``` javascript
var ixo = require("ixo");

//Int the ixo object
var i = new ixo();

//Create new block and put data in it
i.block(0, "Some Data");
i.block(0, "More Data");

//Create new block and put data in it
i.block(1, "Some Data");
i.block(1, "More Data");

//Sign each block
i.sign(0, "0 password");
i.sign(1, "1 password");

//Read an item from the chain
console.log(i.read(0, "0 password"));

//Export the blockchain to a string
console.log(i.export());
```

### Break down

First things first you have to include the libary, luckly this is easy, just use require. (make sure ixo is installed first!)
``` javascript
var ixo = require("ixo");
```

After you have the libary included you have to initiate the blockchain. We chose to do it this way because it allows you to create multiple blockchain instances in one Node.JS app. This object will be where you modify your blockchain.
``` javascript
var i = new ixo();
```

Adding unsigned blocks to the chain is made easy with the block function. This stores the ASCII text data in a "block", a block is just a container that store information think of it like a SQL table row where you can put anything in it.
``` javascript
i.block(0, "Some Data");
i.block(0, "More Data");
```


``` javascript