## DID-SDK

This SDK aims to help the development of integrations with DidStorage smart-contracts that use JavaScript.

### Contents

- [`src/did-client-core.js`](./src/did-client-core.js) - sdk uses TonClient(<a href="https://github.com/tonlabs/ton-client-js">@tonclient/core</a>) for node js and web front

### Example use did-core for Node js

[Specification](./docs/spec-did-core.md)

```javascript

const { libNode } = require("@tonclient/lib-node");

const core = require('../src/did-client-core.js');


async function main() {

  core.initSettings("devNet", client);
  
  const did = 'did:everscale:5214b9f26c13a9258245d86995f5b93c34eb9a2c982420cda871919f454ca194';
  
  res = await core.resolveDIDDocument(did);

  console.log(res);
}
```

### Example use did-core for Web

[Specification](./docs/spec-did-core.md)

```javascript

import { libWeb } from "@tonclient/lib-web";

import core from '../src/did-client-core.js';

async function main() {

  core.initSettings("devNet", client);
  
  const did = 'did:everscale:5214b9f26c13a9258245d86995f5b93c34eb9a2c982420cda871919f454ca194';
  
  res = await core.resolveDIDDocument(did);

  console.log(res);
}
```

### Example use did-core for Node js or Web
[Check file](./test/run.js)


### How to install

```shell
npm install
```

### How to test

set params (address and keys) for giver contract in [test/GiverContract.json](./test/GiverContract.json) file and run

```shell
npm run test
```

Output
```

tests are completed
Result of tests
start tests: success
Test 1 - Create did smart-contract: success
Test 2 - resolve did: success
Test 3 - update json did document: success
Test 4 - update status of did document smart-contract: success
Test 5 - update Issuer Address of did document smart-contract: success
Test 6 - delete did document smart-contract: success
Test 7 - sign data: success
Test 8 - verify signature: success

```