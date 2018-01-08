# ixo
ixo.js is a blockchain designed to be light weight and efficient. The purpose of ixo was to server as a immutable datastore that can be proven and to maintain privacy for your companies needs. We are building the first ever plug and play blockchain that once setup will run at exceptionally fast speeds.

### Installation
```
npm install ixo
```

### Basic Usage
```
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