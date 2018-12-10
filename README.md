# my-ico

Example of creating a crowdsale with Zeppelin Solidity v2.0

Companion code to the Blogpost [https://blog.zeppelin.solutions/how-to-create-token-and-initial-coin-offering-contracts-using-truffle-openzeppelin-1b7a5dae99b6](https://blog.zeppelin.solutions/how-to-create-token-and-initial-coin-offering-contracts-using-truffle-openzeppelin-1b7a5dae99b6)

```
~/gitrepo/github$ git clone https://github.com/tys-hiroshi/my-ico.git
Cloning into 'my-ico'...
remote: Enumerating objects: 110, done.
remote: Total 110 (delta 0), reused 0 (delta 0), pack-reused 110
Receiving objects: 100% (110/110), 110.11 KiB | 0 bytes/s, done.
Resolving deltas: 100% (60/60), done.
Checking connectivity... done.
~/gitrepo/github$ cd my-ico/
~/gitrepo/github/my-ico$ ls
README.md  contracts  migrations  package-lock.json  package.json  truffle.js
~/gitrepo/github/my-ico$ code .
~/gitrepo/github/my-ico$ npm i
added 1 package from 1 contributor and audited 1 package in 1.42s
found 0 vulnerabilities

~/gitrepo/github/my-ico$ ganache-cli
Ganache CLI v6.2.3 (ganache-core: 2.3.1)
Error: listen EADDRINUSE 127.0.0.1:8545
    at Server.setupListenHandle [as _listen2] (net.js:1360:14)
    at listenInCluster (net.js:1401:12)
    at doListen (net.js:1510:7)
    at _combinedTickCallback (internal/process/next_tick.js:142:11)
    at process._tickCallback (internal/process/next_tick.js:181:9)
    at Function.Module.runMain (module.js:696:11)
    at startup (bootstrap_node.js:204:16)
    at bootstrap_node.js:625:3
~/gitrepo/github/my-ico$ npm i -g ganache-cli
/home/th4/.npm-global/bin/ganache-cli -> /home/th4/.npm-global/lib/node_modules/ganache-cli/cli.js
+ ganache-cli@6.2.3
removed 3 packages and updated 1 package in 3.682s
~/gitrepo/github/my-ico$ truffle compile
Compiling ./contracts/GustavoCoin.sol...
Compiling ./contracts/GustavoCoinCrowdsale.sol...
Compiling ./contracts/Migrations.sol...
Compiling openzeppelin-solidity/contracts/access/Roles.sol...
Compiling openzeppelin-solidity/contracts/access/roles/MinterRole.sol...
Compiling openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol...
Compiling openzeppelin-solidity/contracts/crowdsale/emission/MintedCrowdsale.sol...
Compiling openzeppelin-solidity/contracts/crowdsale/validation/TimedCrowdsale.sol...
Compiling openzeppelin-solidity/contracts/math/SafeMath.sol...
Compiling openzeppelin-solidity/contracts/token/ERC20/ERC20.sol...
Compiling openzeppelin-solidity/contracts/token/ERC20/ERC20Mintable.sol...
Compiling openzeppelin-solidity/contracts/token/ERC20/IERC20.sol...
Compiling openzeppelin-solidity/contracts/token/ERC20/SafeERC20.sol...
Compiling openzeppelin-solidity/contracts/utils/ReentrancyGuard.sol...

Compilation warnings encountered:

/home/th4/gitrepo/github/my-ico/contracts/Migrations.sol:11:3: Warning: Defining constructors as functions with the same name as the contract is deprecated. Use "constructor(...) { ... }" instead.
  function Migrations() {
  ^ (Relevant source part starts here and spans across multiple lines).
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:173:5: Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
    address beneficiary,
    ^-----------------^
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:174:5: Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
    uint256 weiAmount
    ^---------------^
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:216:5: Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
    address beneficiary,
    ^-----------------^
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:217:5: Warning: Unused function parameter. Remove or comment out the variable name to silence this warning.
    uint256 weiAmount
    ^---------------^
,/home/th4/gitrepo/github/my-ico/contracts/Migrations.sol:11:3: Warning: No visibility specified. Defaulting to "public". 
  function Migrations() {
  ^ (Relevant source part starts here and spans across multiple lines).
,/home/th4/gitrepo/github/my-ico/contracts/Migrations.sol:15:3: Warning: No visibility specified. Defaulting to "public". 
  function setCompleted(uint completed) restricted {
  ^ (Relevant source part starts here and spans across multiple lines).
,/home/th4/gitrepo/github/my-ico/contracts/Migrations.sol:19:3: Warning: No visibility specified. Defaulting to "public". 
  function upgrade(address new_address) restricted {
  ^ (Relevant source part starts here and spans across multiple lines).
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:156:3: Warning: Function state mutability can be restricted to pure
  function _preValidatePurchase(
  ^ (Relevant source part starts here and spans across multiple lines).
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:172:3: Warning: Function state mutability can be restricted to pure
  function _postValidatePurchase(
  ^ (Relevant source part starts here and spans across multiple lines).
,openzeppelin-solidity/contracts/crowdsale/Crowdsale.sol:215:3: Warning: Function state mutability can be restricted to pure
  function _updatePurchasingState(
  ^ (Relevant source part starts here and spans across multiple lines).

Writing artifacts to ./build/contracts

~/gitrepo/github/my-ico$ truffle migrate
Using network 'development'.

Running migration: 1_initial_migration.js
  Deploying Migrations...
  ... 0xb4111db28c9557c7228dd51365ffaa109737e3c2d3d8c4d92504e00ff7d26611
  Migrations: 0x1c2c07c9e2392e1d64da74781abdb10c9786e0f4
Saving successful migration to network...
  ... 0xde6d22351fede5343e2522f335c75fd71ec5c47ebd01b3191c56a2626c54eac3
Saving artifacts...
Running migration: 2_deploy_contracts.js
  Running step...
  Deploying GustavoCoin...
  ... 0xf4e523298f111dd795b9f0c701e170a1ccb5e65a3e45bbc4db2d7b8a15c944a1
  GustavoCoin: 0x963dadbbc15aed1251ca387c8ce36fc32dd57d69
  Deploying GustavoCoinCrowdsale...
  ... 0xadb5af674b5a64418936c07e1a89a51914d216e4b34a62f233550ff8b9ca499f
  GustavoCoinCrowdsale: 0xb4602a88ba99e61e194ab24806dafb17c5b785bc
Saving successful migration to network...
  ... 0x7fc1223ddde1104866fee57fe694d2b02af785ede8f48546fa1b556520e5e2a9
Saving artifacts...
~/gitrepo/github/my-ico$ truffle console
truffle(development)> purchaser = web3.eth.accounts[2]
'0x085e0a9446e2c280cc60cf33a2bf7b2da897067c'
truffle(development)> GustavoCoinCrowdsale.deployed().then(inst => { crowdsale = inst })
undefined
truffle(development)> crowdsale.token().then(addr => { tokenAddress = addr } )
undefined
truffle(development)> tokenAddress
'0x963dadbbc15aed1251ca387c8ce36fc32dd57d69'
truffle(development)> gustavoCoinInstance = GustavoCoin.at(tokenAddress)
TruffleContract {
  constructor: 
   { [Function: TruffleContract]
     _static_methods: 
      { setProvider: [Function: setProvider],
        new: [Function: new],
        at: [Function: at],
        deployed: [Function: deployed],
        defaults: [Function: defaults],
        hasNetwork: [Function: hasNetwork],
        isDeployed: [Function: isDeployed],
        detectNetwork: [Function: detectNetwork],
        setNetwork: [Function: setNetwork],
        resetAddress: [Function: resetAddress],
        link: [Function: link],
        clone: [Function: clone],
        addProp: [Function: addProp],
        toJSON: [Function: toJSON] },
     _properties: 
      { contract_name: [Object],
        contractName: [Object],
        abi: [Object],
        network: [Function: network],
        networks: [Function: networks],
        address: [Object],
        transactionHash: [Object],
        links: [Function: links],
        events: [Function: events],
        binary: [Function: binary],
        deployedBinary: [Function: deployedBinary],
        unlinked_binary: [Object],
        bytecode: [Object],
        deployedBytecode: [Object],
        sourceMap: [Object],
        deployedSourceMap: [Object],
        source: [Object],
        sourcePath: [Object],
        legacyAST: [Object],
        ast: [Object],
        compiler: [Object],
        schema_version: [Function: schema_version],
        schemaVersion: [Function: schemaVersion],
        updated_at: [Function: updated_at],
        updatedAt: [Function: updatedAt] },
     _property_values: {},
     _json: 
      { contractName: 'GustavoCoin',
        abi: [Array],
        bytecode: '0x60806040526040805190810160405280600c81526020017f4755535441564f20434f494e000000000000000000000000000000000000000081525060049080519060200190620000519291906200029e565b506040805190810160405280600381526020017f4755530000000000000000000000000000000000000000000000000000000000815250600590805190602001906200009f9291906200029e565b506012600660006101000a81548160ff021916908360ff160217905550620000d633620000dc640100000000026401000000009004565b6200034d565b6200010081600362000146640100000000026200153c179091906401000000009004565b8073ffffffffffffffffffffffffffffffffffffffff167f6ae172837ea30b801fbfcdd4108aa1d5bf8ff775444fd70256b44e6bf3dfc3f660405160405180910390a250565b600073ffffffffffffffffffffffffffffffffffffffff168173ffffffffffffffffffffffffffffffffffffffff16141515156200018357600080fd5b6200019e828262000209640100000000026401000000009004565b151515620001ab57600080fd5b60018260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060006101000a81548160ff0219169083151502179055505050565b60008073ffffffffffffffffffffffffffffffffffffffff168273ffffffffffffffffffffffffffffffffffffffff16141515156200024757600080fd5b8260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060009054906101000a900460ff16905092915050565b828054600181600116156101000203166002900490600052602060002090601f016020900481019282601f10620002e157805160ff191683800117855562000312565b8280016001018555821562000312579182015b8281111562000311578251825591602001919060010190620002f4565b5b50905062000321919062000325565b5090565b6200034a91905b80821115620003465760008160009055506001016200032c565b5090565b90565b6116c7806200035d6000396000f3006080604052600436106100db576000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff16806306fdde03146100e0578063095ea7b31461017057806318160ddd146101d557806323b872dd14610200578063313ce5671461028557806339509351146102b657806340c10f191461031b57806370a082311461038057806395d89b41146103d7578063983b2d561461046757806398650275146104aa578063a457c2d7146104c1578063a9059cbb14610526578063aa271e1a1461058b578063dd62ed3e146105e6575b600080fd5b3480156100ec57600080fd5b506100f561065d565b6040518080602001828103825283818151815260200191508051906020019080838360005b8381101561013557808201518184015260208101905061011a565b50505050905090810190601f1680156101625780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561017c57600080fd5b506101bb600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803590602001909291905050506106fb565b604051808215151515815260200191505060405180910390f35b3480156101e157600080fd5b506101ea610828565b6040518082815260200191505060405180910390f35b34801561020c57600080fd5b5061026b600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610832565b604051808215151515815260200191505060405180910390f35b34801561029157600080fd5b5061029a6109e4565b604051808260ff1660ff16815260200191505060405180910390f35b3480156102c257600080fd5b50610301600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803590602001909291905050506109f7565b604051808215151515815260200191505060405180910390f35b34801561032757600080fd5b50610366600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610c2e565b604051808215151515815260200191505060405180910390f35b34801561038c57600080fd5b506103c1600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610c58565b6040518082815260200191505060405180910390f35b3480156103e357600080fd5b506103ec610ca0565b6040518080602001828103825283818151815260200191508051906020019080838360005b8381101561042c578082015181840152602081019050610411565b50505050905090810190601f1680156104595780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561047357600080fd5b506104a8600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610d3e565b005b3480156104b657600080fd5b506104bf610d5e565b005b3480156104cd57600080fd5b5061050c600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610d69565b604051808215151515815260200191505060405180910390f35b34801561053257600080fd5b50610571600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610fa0565b604051808215151515815260200191505060405180910390f35b34801561059757600080fd5b506105cc600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610fb7565b604051808215151515815260200191505060405180910390f35b3480156105f257600080fd5b50610647600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610fd4565b6040518082815260200191505060405180910390f35b60048054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156106f35780601f106106c8576101008083540402835291602001916106f3565b820191906000526020600020905b8154815290600101906020018083116106d657829003601f168201915b505050505081565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff161415151561073857600080fd5b81600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925846040518082815260200191505060405180910390a36001905092915050565b6000600254905090565b6000600160008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205482111515156108bf57600080fd5b61094e82600160008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b600160008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055506109d984848461107c565b600190509392505050565b600660009054906101000a900460ff1681565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff1614151515610a3457600080fd5b610ac382600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020546040518082815260200191505060405180910390a36001905092915050565b6000610c3933610fb7565b1515610c4457600080fd5b610c4e83836112b6565b6001905092915050565b60008060008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020549050919050565b60058054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610d365780601f10610d0b57610100808354040283529160200191610d36565b820191906000526020600020905b815481529060010190602001808311610d1957829003601f168201915b505050505081565b610d4733610fb7565b1515610d5257600080fd5b610d5b816113f4565b50565b610d673361144e565b565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff1614151515610da657600080fd5b610e3582600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020546040518082815260200191505060405180910390a36001905092915050565b6000610fad33848461107c565b6001905092915050565b6000610fcd8260036114a890919063ffffffff16565b9050919050565b6000600160008473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054905092915050565b60008083831115151561106d57600080fd5b82840390508091505092915050565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205481111515156110c957600080fd5b600073ffffffffffffffffffffffffffffffffffffffff168273ffffffffffffffffffffffffffffffffffffffff161415151561110557600080fd5b611156816000808673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b6000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055506111e9816000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508173ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff167fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef836040518082815260200191505060405180910390a3505050565b60008082840190508381101515156112ac57600080fd5b8091505092915050565b60008273ffffffffffffffffffffffffffffffffffffffff16141515156112dc57600080fd5b6112f18160025461129590919063ffffffff16565b600281905550611348816000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508173ffffffffffffffffffffffffffffffffffffffff16600073ffffffffffffffffffffffffffffffffffffffff167fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef836040518082815260200191505060405180910390a35050565b61140881600361153c90919063ffffffff16565b8073ffffffffffffffffffffffffffffffffffffffff167f6ae172837ea30b801fbfcdd4108aa1d5bf8ff775444fd70256b44e6bf3dfc3f660405160405180910390a250565b6114628160036115ec90919063ffffffff16565b8073ffffffffffffffffffffffffffffffffffffffff167fe94479a9f7e1952cc78f2d6baab678adc1b772d936c6583def489e524cb6669260405160405180910390a250565b60008073ffffffffffffffffffffffffffffffffffffffff168273ffffffffffffffffffffffffffffffffffffffff16141515156114e557600080fd5b8260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060009054906101000a900460ff16905092915050565b600073ffffffffffffffffffffffffffffffffffffffff168173ffffffffffffffffffffffffffffffffffffffff161415151561157857600080fd5b61158282826114a8565b15151561158e57600080fd5b60018260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060006101000a81548160ff0219169083151502179055505050565b600073ffffffffffffffffffffffffffffffffffffffff168173ffffffffffffffffffffffffffffffffffffffff161415151561162857600080fd5b61163282826114a8565b151561163d57600080fd5b60008260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060006101000a81548160ff02191690831515021790555050505600a165627a7a723058200287fbcb1665d7c438699a34480b096c0db99beb22745b36e028cd4b7087d9c30029',
        deployedBytecode: '0x6080604052600436106100db576000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff16806306fdde03146100e0578063095ea7b31461017057806318160ddd146101d557806323b872dd14610200578063313ce5671461028557806339509351146102b657806340c10f191461031b57806370a082311461038057806395d89b41146103d7578063983b2d561461046757806398650275146104aa578063a457c2d7146104c1578063a9059cbb14610526578063aa271e1a1461058b578063dd62ed3e146105e6575b600080fd5b3480156100ec57600080fd5b506100f561065d565b6040518080602001828103825283818151815260200191508051906020019080838360005b8381101561013557808201518184015260208101905061011a565b50505050905090810190601f1680156101625780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561017c57600080fd5b506101bb600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803590602001909291905050506106fb565b604051808215151515815260200191505060405180910390f35b3480156101e157600080fd5b506101ea610828565b6040518082815260200191505060405180910390f35b34801561020c57600080fd5b5061026b600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610832565b604051808215151515815260200191505060405180910390f35b34801561029157600080fd5b5061029a6109e4565b604051808260ff1660ff16815260200191505060405180910390f35b3480156102c257600080fd5b50610301600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803590602001909291905050506109f7565b604051808215151515815260200191505060405180910390f35b34801561032757600080fd5b50610366600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610c2e565b604051808215151515815260200191505060405180910390f35b34801561038c57600080fd5b506103c1600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610c58565b6040518082815260200191505060405180910390f35b3480156103e357600080fd5b506103ec610ca0565b6040518080602001828103825283818151815260200191508051906020019080838360005b8381101561042c578082015181840152602081019050610411565b50505050905090810190601f1680156104595780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561047357600080fd5b506104a8600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610d3e565b005b3480156104b657600080fd5b506104bf610d5e565b005b3480156104cd57600080fd5b5061050c600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610d69565b604051808215151515815260200191505060405180910390f35b34801561053257600080fd5b50610571600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610fa0565b604051808215151515815260200191505060405180910390f35b34801561059757600080fd5b506105cc600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610fb7565b604051808215151515815260200191505060405180910390f35b3480156105f257600080fd5b50610647600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610fd4565b6040518082815260200191505060405180910390f35b60048054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156106f35780601f106106c8576101008083540402835291602001916106f3565b820191906000526020600020905b8154815290600101906020018083116106d657829003601f168201915b505050505081565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff161415151561073857600080fd5b81600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925846040518082815260200191505060405180910390a36001905092915050565b6000600254905090565b6000600160008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205482111515156108bf57600080fd5b61094e82600160008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b600160008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055506109d984848461107c565b600190509392505050565b600660009054906101000a900460ff1681565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff1614151515610a3457600080fd5b610ac382600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020546040518082815260200191505060405180910390a36001905092915050565b6000610c3933610fb7565b1515610c4457600080fd5b610c4e83836112b6565b6001905092915050565b60008060008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020549050919050565b60058054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610d365780601f10610d0b57610100808354040283529160200191610d36565b820191906000526020600020905b815481529060010190602001808311610d1957829003601f168201915b505050505081565b610d4733610fb7565b1515610d5257600080fd5b610d5b816113f4565b50565b610d673361144e565b565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff1614151515610da657600080fd5b610e3582600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925600160003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020546040518082815260200191505060405180910390a36001905092915050565b6000610fad33848461107c565b6001905092915050565b6000610fcd8260036114a890919063ffffffff16565b9050919050565b6000600160008473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054905092915050565b60008083831115151561106d57600080fd5b82840390508091505092915050565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205481111515156110c957600080fd5b600073ffffffffffffffffffffffffffffffffffffffff168273ffffffffffffffffffffffffffffffffffffffff161415151561110557600080fd5b611156816000808673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461105b90919063ffffffff16565b6000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055506111e9816000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508173ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff167fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef836040518082815260200191505060405180910390a3505050565b60008082840190508381101515156112ac57600080fd5b8091505092915050565b60008273ffffffffffffffffffffffffffffffffffffffff16141515156112dc57600080fd5b6112f18160025461129590919063ffffffff16565b600281905550611348816000808573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205461129590919063ffffffff16565b6000808473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508173ffffffffffffffffffffffffffffffffffffffff16600073ffffffffffffffffffffffffffffffffffffffff167fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef836040518082815260200191505060405180910390a35050565b61140881600361153c90919063ffffffff16565b8073ffffffffffffffffffffffffffffffffffffffff167f6ae172837ea30b801fbfcdd4108aa1d5bf8ff775444fd70256b44e6bf3dfc3f660405160405180910390a250565b6114628160036115ec90919063ffffffff16565b8073ffffffffffffffffffffffffffffffffffffffff167fe94479a9f7e1952cc78f2d6baab678adc1b772d936c6583def489e524cb6669260405160405180910390a250565b60008073ffffffffffffffffffffffffffffffffffffffff168273ffffffffffffffffffffffffffffffffffffffff16141515156114e557600080fd5b8260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060009054906101000a900460ff16905092915050565b600073ffffffffffffffffffffffffffffffffffffffff168173ffffffffffffffffffffffffffffffffffffffff161415151561157857600080fd5b61158282826114a8565b15151561158e57600080fd5b60018260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060006101000a81548160ff0219169083151502179055505050565b600073ffffffffffffffffffffffffffffffffffffffff168173ffffffffffffffffffffffffffffffffffffffff161415151561162857600080fd5b61163282826114a8565b151561163d57600080fd5b60008260000160008373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060006101000a81548160ff02191690831515021790555050505600a165627a7a723058200287fbcb1665d7c438699a34480b096c0db99beb22745b36e028cd4b7087d9c30029',
        sourceMap: '98:148:0:-;;;142:35;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;:::i;:::-;;183:28;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;:::i;:::-;;241:2;217:26;;;;;;;;;;;;;;;;;;;;260:22:4;271:10;260;;;:22;;;:::i;:::-;98:148:0;;629:108:4;681:20;693:7;681;:11;;;;;;:20;;;;;:::i;:::-;724:7;712:20;;;;;;;;;;;;629:108;:::o;244:167:3:-;335:1;316:21;;:7;:21;;;;308:30;;;;;;;;353:18;357:4;363:7;353:3;;;:18;;;:::i;:::-;352:19;344:28;;;;;;;;402:4;379;:11;;:20;391:7;379:20;;;;;;;;;;;;;;;;:27;;;;;;;;;;;;;;;;;;244:167;;:::o;725:166::-;809:4;850:1;831:21;;:7;:21;;;;823:30;;;;;;;;866:4;:11;;:20;878:7;866:20;;;;;;;;;;;;;;;;;;;;;;;;;859:27;;725:166;;;;:::o;98:148:0:-;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;:::i;:::-;;;:::o;:::-;;;;;;;;;;;;;;;;;;;;;;;;;;;:::o;:::-;;;;;;;',
        deployedSourceMap: '98:148:0:-;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;142:35;;8:9:-1;5:2;;;30:1;27;20:12;5:2;142:35:0;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;23:1:-1;8:100;33:3;30:1;27:10;8:100;;;99:1;94:3;90:11;84:18;80:1;75:3;71:11;64:39;52:2;49:1;45:10;40:15;;8:100;;;12:14;142:35:0;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;2380:220:9;;8:9:-1;5:2;;;30:1;27;20:12;5:2;2380:220:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;640:83;;8:9:-1;5:2;;;30:1;27;20:12;5:2;640:83:9;;;;;;;;;;;;;;;;;;;;;;;2872:288;;8:9:-1;5:2;;;30:1;27;20:12;5:2;2872:288:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;217:26:0;;8:9:-1;5:2;;;30:1;27;20:12;5:2;217:26:0;;;;;;;;;;;;;;;;;;;;;;;;;;;3611:330:9;;8:9:-1;5:2;;;30:1;27;20:12;5:2;3611:330:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;430:144:10;;8:9:-1;5:2;;;30:1;27;20:12;5:2;430:144:10;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;920:98:9;;8:9:-1;5:2;;;30:1;27;20:12;5:2;920:98:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;183:28:0;;8:9:-1;5:2;;;30:1;27;20:12;5:2;183:28:0;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;23:1:-1;8:100;33:3;30:1;27:10;8:100;;;99:1;94:3;90:11;84:18;80:1;75:3;71:11;64:39;52:2;49:1;45:10;40:15;;8:100;;;12:14;183:28:0;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;468:84:4;;8:9:-1;5:2;;;30:1;27;20:12;5:2;468:84:4;;;;;;;;;;;;;;;;;;;;;;;;;;;;556:69;;8:9:-1;5:2;;;30:1;27;20:12;5:2;556:69:4;;;;;;4397:340:9;;8:9:-1;5:2;;;30:1;27;20:12;5:2;4397:340:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;1637:127;;8:9:-1;5:2;;;30:1;27;20:12;5:2;1637:127:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;364:100:4;;8:9:-1;5:2;;;30:1;27;20:12;5:2;364:100:4;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;1335:150:9;;8:9:-1;5:2;;;30:1;27;20:12;5:2;1335:150:9;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;142:35:0;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;:::o;2380:220:9:-;2445:4;2484:1;2465:21;;:7;:21;;;;2457:30;;;;;;;;2526:5;2494:8;:20;2503:10;2494:20;;;;;;;;;;;;;;;:29;2515:7;2494:29;;;;;;;;;;;;;;;:37;;;;2563:7;2542:36;;2551:10;2542:36;;;2572:5;2542:36;;;;;;;;;;;;;;;;;;2591:4;2584:11;;2380:220;;;;:::o;640:83::-;684:7;706:12;;699:19;;640:83;:::o;2872:288::-;2975:4;3006:8;:14;3015:4;3006:14;;;;;;;;;;;;;;;:26;3021:10;3006:26;;;;;;;;;;;;;;;;2997:5;:35;;2989:44;;;;;;;;3069:37;3100:5;3069:8;:14;3078:4;3069:14;;;;;;;;;;;;;;;:26;3084:10;3069:26;;;;;;;;;;;;;;;;:30;;:37;;;;:::i;:::-;3040:8;:14;3049:4;3040:14;;;;;;;;;;;;;;;:26;3055:10;3040:26;;;;;;;;;;;;;;;:66;;;;3112:26;3122:4;3128:2;3132:5;3112:9;:26::i;:::-;3151:4;3144:11;;2872:288;;;;;:::o;217:26:0:-;;;;;;;;;;;;;:::o;3611:330:9:-;3711:4;3752:1;3733:21;;:7;:21;;;;3725:30;;;;;;;;3802:45;3836:10;3802:8;:20;3811:10;3802:20;;;;;;;;;;;;;;;:29;3823:7;3802:29;;;;;;;;;;;;;;;;:33;;:45;;;;:::i;:::-;3762:8;:20;3771:10;3762:20;;;;;;;;;;;;;;;:29;3783:7;3762:29;;;;;;;;;;;;;;;:86;;;;3880:7;3859:60;;3868:10;3859:60;;;3889:8;:20;3898:10;3889:20;;;;;;;;;;;;;;;:29;3910:7;3889:29;;;;;;;;;;;;;;;;3859:60;;;;;;;;;;;;;;;;;;3932:4;3925:11;;3611:330;;;;:::o;430:144:10:-;522:4;327:20:4;336:10;327:8;:20::i;:::-;319:29;;;;;;;;536:16:10;542:2;546:5;536;:16::i;:::-;565:4;558:11;;430:144;;;;:::o;920:98:9:-;975:7;997:9;:16;1007:5;997:16;;;;;;;;;;;;;;;;990:23;;920:98;;;:::o;183:28:0:-;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;:::o;468:84:4:-;327:20;336:10;327:8;:20::i;:::-;319:29;;;;;;;;528:19;539:7;528:10;:19::i;:::-;468:84;:::o;556:69::-;595:25;609:10;595:13;:25::i;:::-;556:69::o;4397:340:9:-;4502:4;4543:1;4524:21;;:7;:21;;;;4516:30;;;;;;;;4593:50;4627:15;4593:8;:20;4602:10;4593:20;;;;;;;;;;;;;;;:29;4614:7;4593:29;;;;;;;;;;;;;;;;:33;;:50;;;;:::i;:::-;4553:8;:20;4562:10;4553:20;;;;;;;;;;;;;;;:29;4574:7;4553:29;;;;;;;;;;;;;;;:91;;;;4676:7;4655:60;;4664:10;4655:60;;;4685:8;:20;4694:10;4685:20;;;;;;;;;;;;;;;:29;4706:7;4685:29;;;;;;;;;;;;;;;;4655:60;;;;;;;;;;;;;;;;;;4728:4;4721:11;;4397:340;;;;:::o;1637:127::-;1698:4;1710:32;1720:10;1732:2;1736:5;1710:9;:32::i;:::-;1755:4;1748:11;;1637:127;;;;:::o;364:100:4:-;420:4;439:20;451:7;439;:11;;:20;;;;:::i;:::-;432:27;;364:100;;;:::o;1335:150:9:-;1432:7;1456:8;:15;1465:5;1456:15;;;;;;;;;;;;;;;:24;1472:7;1456:24;;;;;;;;;;;;;;;;1449:31;;1335:150;;;;:::o;1078:131:8:-;1136:7;1172:9;1164:1;1159;:6;;1151:15;;;;;;;;1188:1;1184;:5;1172:17;;1203:1;1196:8;;1078:131;;;;;:::o;4937:277:9:-;5029:9;:15;5039:4;5029:15;;;;;;;;;;;;;;;;5020:5;:24;;5012:33;;;;;;;;5073:1;5059:16;;:2;:16;;;;5051:25;;;;;;;;5101:26;5121:5;5101:9;:15;5111:4;5101:15;;;;;;;;;;;;;;;;:19;;:26;;;;:::i;:::-;5083:9;:15;5093:4;5083:15;;;;;;;;;;;;;;;:44;;;;5149:24;5167:5;5149:9;:13;5159:2;5149:13;;;;;;;;;;;;;;;;:17;;:24;;;;:::i;:::-;5133:9;:13;5143:2;5133:13;;;;;;;;;;;;;;;:40;;;;5199:2;5184:25;;5193:4;5184:25;;;5203:5;5184:25;;;;;;;;;;;;;;;;;;4937:277;;;:::o;1272:131:8:-;1330:7;1345:9;1361:1;1357;:5;1345:17;;1381:1;1376;:6;;1368:15;;;;;;;;1397:1;1390:8;;1272:131;;;;;:::o;5541:235:9:-;5622:1;5611:7;:12;;;;5603:21;;;;;;;;5645:23;5662:5;5645:12;;:16;;:23;;;;:::i;:::-;5630:12;:38;;;;5695:29;5718:5;5695:9;:18;5705:7;5695:18;;;;;;;;;;;;;;;;:22;;:29;;;;:::i;:::-;5674:9;:18;5684:7;5674:18;;;;;;;;;;;;;;;:50;;;;5756:7;5735:36;;5752:1;5735:36;;;5765:5;5735:36;;;;;;;;;;;;;;;;;;5541:235;;:::o;629:108:4:-;681:20;693:7;681;:11;;:20;;;;:::i;:::-;724:7;712:20;;;;;;;;;;;;629:108;:::o;741:116::-;796:23;811:7;796;:14;;:23;;;;:::i;:::-;844:7;830:22;;;;;;;;;;;;741:116;:::o;725:166:3:-;809:4;850:1;831:21;;:7;:21;;;;823:30;;;;;;;;866:4;:11;;:20;878:7;866:20;;;;;;;;;;;;;;;;;;;;;;;;;859:27;;725:166;;;;:::o;244:167::-;335:1;316:21;;:7;:21;;;;308:30;;;;;;;;353:18;357:4;363:7;353:3;:18::i;:::-;352:19;344:28;;;;;;;;402:4;379;:11;;:20;391:7;379:20;;;;;;;;;;;;;;;;:27;;;;;;;;;;;;;;;;;;244:167;;:::o;477:170::-;571:1;552:21;;:7;:21;;;;544:30;;;;;;;;588:18;592:4;598:7;588:3;:18::i;:::-;580:27;;;;;;;;637:5;614:4;:11;;:20;626:7;614:20;;;;;;;;;;;;;;;;:28;;;;;;;;;;;;;;;;;;477:170;;:::o',
        source: 'pragma solidity 0.4.24;\n\nimport \'openzeppelin-solidity/contracts/token/ERC20/ERC20Mintable.sol\';\n\ncontract GustavoCoin is ERC20Mintable {\n    string public name = "GUSTAVO COIN";\n    string public symbol = "GUS";\n    uint8 public decimals = 18;\n}',
        sourcePath: '/home/th4/gitrepo/github/my-ico/contracts/GustavoCoin.sol',
        ast: [Object],
        legacyAST: [Object],
        compiler: [Object],
        networks: [Object],
        schemaVersion: '2.0.1',
        updatedAt: '2018-12-10T13:42:15.390Z' },
     setProvider: [Function: bound setProvider],
     new: [Function: bound new],
     at: [Function: bound at],
     deployed: [Function: bound deployed],
     defaults: [Function: bound defaults],
     hasNetwork: [Function: bound hasNetwork],
     isDeployed: [Function: bound isDeployed],
     detectNetwork: [Function: bound detectNetwork],
     setNetwork: [Function: bound setNetwork],
     resetAddress: [Function: bound resetAddress],
     link: [Function: bound link],
     clone: [Function: bound clone],
     addProp: [Function: bound addProp],
     toJSON: [Function: bound toJSON],
     web3: 
      Web3 {
        _requestManager: [Object],
        currentProvider: [Object],
        eth: [Object],
        db: [Object],
        shh: [Object],
        net: [Object],
        personal: [Object],
        bzz: [Object],
        settings: [Object],
        version: [Object],
        providers: [Object],
        _extend: [Object] },
     class_defaults: 
      { from: '0x3f1e4fc517e18f5aa9cbe892da431944846ded44',
        gas: 6721975,
        gasPrice: 100000000000 },
     currentProvider: 
      HttpProvider {
        host: 'http://localhost:8545',
        timeout: 0,
        user: undefined,
        password: undefined,
        headers: undefined,
        send: [Function],
        sendAsync: [Function],
        _alreadyWrapped: true },
     network_id: '1544448291614' },
  abi: 
   [ { constant: true,
       inputs: [],
       name: 'name',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'approve',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: true,
       inputs: [],
       name: 'totalSupply',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'transferFrom',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: true,
       inputs: [],
       name: 'decimals',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'increaseAllowance',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'mint',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: true,
       inputs: [Array],
       name: 'balanceOf',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: true,
       inputs: [],
       name: 'symbol',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'addMinter',
       outputs: [],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: false,
       inputs: [],
       name: 'renounceMinter',
       outputs: [],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'decreaseAllowance',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: false,
       inputs: [Array],
       name: 'transfer',
       outputs: [Array],
       payable: false,
       stateMutability: 'nonpayable',
       type: 'function' },
     { constant: true,
       inputs: [Array],
       name: 'isMinter',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { constant: true,
       inputs: [Array],
       name: 'allowance',
       outputs: [Array],
       payable: false,
       stateMutability: 'view',
       type: 'function' },
     { anonymous: false,
       inputs: [Array],
       name: 'MinterAdded',
       type: 'event' },
     { anonymous: false,
       inputs: [Array],
       name: 'MinterRemoved',
       type: 'event' },
     { anonymous: false,
       inputs: [Array],
       name: 'Transfer',
       type: 'event' },
     { anonymous: false,
       inputs: [Array],
       name: 'Approval',
       type: 'event' } ],
  contract: 
   Contract {
     _eth: 
      Eth {
        _requestManager: [Object],
        getBalance: [Object],
        getStorageAt: [Object],
        getCode: [Object],
        getBlock: [Object],
        getUncle: [Object],
        getCompilers: [Object],
        getBlockTransactionCount: [Object],
        getBlockUncleCount: [Object],
        getTransaction: [Object],
        getTransactionFromBlock: [Object],
        getTransactionReceipt: [Object],
        getTransactionCount: [Object],
        call: [Object],
        estimateGas: [Object],
        sendRawTransaction: [Object],
        signTransaction: [Object],
        sendTransaction: [Object],
        sign: [Object],
        compile: [Object],
        submitWork: [Object],
        getWork: [Object],
        coinbase: [Getter],
        getCoinbase: [Object],
        mining: [Getter],
        getMining: [Object],
        hashrate: [Getter],
        getHashrate: [Object],
        syncing: [Getter],
        getSyncing: [Object],
        gasPrice: [Getter],
        getGasPrice: [Object],
        accounts: [Getter],
        getAccounts: [Object],
        blockNumber: [Getter],
        getBlockNumber: [Object],
        protocolVersion: [Getter],
        getProtocolVersion: [Object],
        iban: [Object],
        sendIBANTransaction: [Function: bound transfer] },
     transactionHash: null,
     address: '0x963dadbbc15aed1251ca387c8ce36fc32dd57d69',
     abi: 
      [ [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object],
        [Object] ],
     name: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        '': [Circular] },
     approve: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,uint256': [Circular] },
     totalSupply: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        '': [Circular] },
     transferFrom: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,address,uint256': [Circular] },
     decimals: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        '': [Circular] },
     increaseAllowance: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,uint256': [Circular] },
     mint: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,uint256': [Circular] },
     balanceOf: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        address: [Circular] },
     symbol: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        '': [Circular] },
     addMinter: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        address: [Circular] },
     renounceMinter: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        '': [Circular] },
     decreaseAllowance: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,uint256': [Circular] },
     transfer: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,uint256': [Circular] },
     isMinter: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        address: [Circular] },
     allowance: 
      { [Function: bound ]
        request: [Function: bound ],
        call: [Function: bound ],
        sendTransaction: [Function: bound ],
        estimateGas: [Function: bound ],
        getData: [Function: bound ],
        'address,address': [Circular] },
     allEvents: [Function: bound ],
     MinterAdded: { [Function: bound ] address: [Function: bound ] },
     MinterRemoved: { [Function: bound ] address: [Function: bound ] },
     Transfer: { [Function: bound ] 'address,address,uint256': [Function: bound ] },
     Approval: { [Function: bound ] 'address,address,uint256': [Function: bound ] } },
  name: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  approve: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  totalSupply: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  transferFrom: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  decimals: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  increaseAllowance: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  mint: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  balanceOf: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  symbol: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  addMinter: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  renounceMinter: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  decreaseAllowance: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  transfer: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  isMinter: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  allowance: 
   { [Function]
     call: [Function],
     sendTransaction: [Function],
     request: [Function: bound ],
     estimateGas: [Function] },
  MinterAdded: { [Function: bound ] address: [Function: bound ] },
  MinterRemoved: { [Function: bound ] address: [Function: bound ] },
  Transfer: { [Function: bound ] 'address,address,uint256': [Function: bound ] },
  Approval: { [Function: bound ] 'address,address,uint256': [Function: bound ] },
  sendTransaction: [Function],
  send: [Function],
  allEvents: [Function: bound ],
  address: '0x963dadbbc15aed1251ca387c8ce36fc32dd57d69',
  transactionHash: null }
truffle(development)> gustavoCoinInstance.addMinter(crowdsale.address)
{ tx: '0x2db0de062d4c3334ee469b6ad094a6438d2062caf4f61b8710c9983dd9e4db3c',
  receipt: 
   { transactionHash: '0x2db0de062d4c3334ee469b6ad094a6438d2062caf4f61b8710c9983dd9e4db3c',
     transactionIndex: 0,
     blockHash: '0xea3aa9695149e95c3b08d5532b8e5535ce46ba80648265a61d1062a13350b678',
     blockNumber: 15,
     from: '0x3f1e4fc517e18f5aa9cbe892da431944846ded44',
     to: '0x963dadbbc15aed1251ca387c8ce36fc32dd57d69',
     gasUsed: 45675,
     cumulativeGasUsed: 45675,
     contractAddress: null,
     logs: [ [Object] ],
     status: '0x1',
     logsBloom: '0x00800000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002000000001000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000000000000000000000008000000000000000000000000000000000020000000000000000000000000000000000000000000204000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001000000000000000000000000000000000000000000000000000000000000000000000000000000000',
     v: '0x1c',
     r: '0x0c8cda8ca6ba881754052d64f77ada92e3bb09d8fa587b5a1bc3f51a6456b6ce',
     s: '0x5628dc2d7b0b85c162886eb64a458527caf9923abc0b40ff65a2a146eef1084c' },
  logs: 
   [ { logIndex: 0,
       transactionIndex: 0,
       transactionHash: '0x2db0de062d4c3334ee469b6ad094a6438d2062caf4f61b8710c9983dd9e4db3c',
       blockHash: '0xea3aa9695149e95c3b08d5532b8e5535ce46ba80648265a61d1062a13350b678',
       blockNumber: 15,
       address: '0x963dadbbc15aed1251ca387c8ce36fc32dd57d69',
       type: 'mined',
       event: 'MinterAdded',
       args: [Object] } ] }
truffle(development)> gustavoCoinInstance.balanceOf(purchaser).then(balance => balance.toString(10))
'0'
truffle(development)> GustavoCoinCrowdsale.deployed().then(inst => inst.sendTransaction({ from: purchaser, value: web3.toWei(5, "ether")}))
{ tx: '0x3312cb89cf1112252043c3783aa0611a82d1fdbc27925fd06635b50f38e13593',
  receipt: 
   { transactionHash: '0x3312cb89cf1112252043c3783aa0611a82d1fdbc27925fd06635b50f38e13593',
     transactionIndex: 0,
     blockHash: '0x29334391aa53f858112da0fba68d1f5a9db76c8d4eef260f64a03561bf9329a1',
     blockNumber: 16,
     from: '0x085e0a9446e2c280cc60cf33a2bf7b2da897067c',
     to: '0xb4602a88ba99e61e194ab24806dafb17c5b785bc',
     gasUsed: 103816,
     cumulativeGasUsed: 103816,
     contractAddress: null,
     logs: [ [Object], [Object] ],
     status: '0x1',
     logsBloom: '0x00000000000000000000000000000000000000000000000000000000000000000080010000000000000000000000000040000000000000002000000001000002000000000004000000000008000000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000010000000000000000000020000000000000000000000002000000000000000000204000000000000000000000000000000000000000000000000000000000000000000000000000002002000000000000000000000000000000000001000000000000000000000000000000000000000000000000000000000000002000000000000000000',
     v: '0x1c',
     r: '0x934e7fb4f79bed783a097b07d1ed35e5662072f5ad02fb2d4e217143f20bb177',
     s: '0x474ce53b4af2541e3fe68bd81391c7dbcfa16a0fb392b5916065094d63f3c28e' },
  logs: 
   [ { logIndex: 1,
       transactionIndex: 0,
       transactionHash: '0x3312cb89cf1112252043c3783aa0611a82d1fdbc27925fd06635b50f38e13593',
       blockHash: '0x29334391aa53f858112da0fba68d1f5a9db76c8d4eef260f64a03561bf9329a1',
       blockNumber: 16,
       address: '0xb4602a88ba99e61e194ab24806dafb17c5b785bc',
       type: 'mined',
       event: 'TokensPurchased',
       args: [Object] } ] }
truffle(development)> gustavoCoinInstance.balanceOf(purchaser).then(balance => purchaserGusTokenBalance = balance.toString(10))
'5000000000000000000000'
truffle(development)> web3.fromWei(purchaserGusTokenBalance, "ether")
'5000'
```