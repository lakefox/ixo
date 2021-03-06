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

This is when the block get "signed" or encrypted, all the data in the block is insecure. You can have multiple blocks that are signed and unsigned on the chain but when you export the chain it will only export the signed blockchain, the rest of the data will stay in the chain till signed and exported. Be careful you can not sign a block that is before another block, if you do the whole chain will be corupt and your data will be lost!
``` javascript
i.sign(0, "0 password");
```

With the read function you can decrypt a signed block anywhere on the chain. 
``` javascript
console.log(i.read(0, "0 password"));
>>> ["Some Data","More Data"]
```

Export and Read are mean for exactly what there name imply, they export and read the blockchain. Export can be used to save the chain to a file so you can make a hard copy of the data. Read can be used to restore a blockchain that you have prevously exported.
``` javascript
console.log(i.export());
>>> "h1RGQkdnYHIEYmEACrbxetxZaZaRKdkDKyaSGnGTiCkbs7Kh hPhhxbkXY3o3HDPz3ZkSriCGdzCy2USLkidKPIrIk1aPY1YG"

var x = new ixo();
x.import("h1RGQkdnYHIEYmEACrbxetxZaZaRKdkDKyaSGnGTiCkbs7Kh hPhhxbkXY3o3HDPz3ZkSriCGdzCy2USLkidKPIrIk1aPY1YG");
```
