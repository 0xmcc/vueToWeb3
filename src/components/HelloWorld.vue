<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links keccak256</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
//import { MerkleTree } from 'merkletreejs';
///import keccak256 from 'keccak256';
////import { createAlchemyWeb3 } from "@alch/alchemy-web3"
//nst createAlchemyWeb3 = require('@alch/alchemy-web3');
import { createAlchemyWeb3 } from "@alch/alchemy-web3";

//const abi = require('../utils/abi.js');

const contractAddress = "0x1224536fd4b7DE15240Fa1b548dEc72dCF2B98b7";
const API_URL = 'https://eth-ropsten.alchemyapi.io/v2/I0zG-OuWm-0z3MOGj7lHLtkUf54wI7Xk'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    console.log("MOUNTED")
    this.importContract()
  },

  methods: {
    importContract() {
      console.log("hi", API_URL)
      console.log(contractAddress)
      const web3 = createAlchemyWeb3(API_URL)
      console.log("here")
      const contract = new web3.eth.Contract(abi, this.contractAddress);
      console.log("CONTRACT", contract)

    }
  }
}

const abi = [
  {
    inputs: [[Object]],
    stateMutability: 'nonpayable',
    type: 'constructor',
    constant: undefined,
    payable: undefined
  },
  {
    anonymous: false,
    inputs: [[Object], [Object], [Object]],
    name: 'ApprovalForAll',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0x17307eab39ab6107e8899845ad3d59bd9653f200f220920489ca2b5937696c31'
  },
  {
    anonymous: false,
    inputs: [[Object], [Object]],
    name: 'OwnershipTransferred',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0x8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e0'
  },
  {
    anonymous: false,
    inputs: [[Object], [Object]],
    name: 'PermanentURI',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0xa109ba539900bf1b633f956d63c96fc89b814c7287f7aa50a9216d0b55657207'
  },
  {
    anonymous: false,
    inputs: [[Object], [Object], [Object], [Object], [Object]],
    name: 'TransferBatch',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0x4a39dc06d4c0dbc64b70af90fd698a233a518aa5d07e595d983b8c0526c8f7fb'
  },
  {
    anonymous: false,
    inputs: [[Object], [Object], [Object], [Object], [Object]],
    name: 'TransferSingle',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0xc3d58168c5ae7397731d063d5bbf3d657854427343f4c083240f7aacaa2d0f62'
  },
  {
    anonymous: false,
    inputs: [[Object], [Object]],
    name: 'URI',
    type: 'event',
    constant: undefined,
    payable: undefined,
    signature: '0x6bb7ff708619ba0610cba295a58592e0451dee2622938c8755667688daf3529b'
  },
  {
    inputs: [[Object], [Object]],
    name: 'balanceOf',
    outputs: [[Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x00fdd58e'
  },
  {
    inputs: [[Object], [Object]],
    name: 'balanceOfBatch',
    outputs: [[Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x4e1273f4'
  },
  {
    inputs: [[Object], [Object]],
    name: 'isApprovedForAll',
    outputs: [[Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0xe985e9c5'
  },
  {
    inputs: [[Object], [Object]],
    name: 'mint',
    outputs: [],
    stateMutability: 'payable',
    type: 'function',
    constant: undefined,
    payable: true,
    signature: '0xba41b0c6'
  },
  {
    inputs: [],
    name: 'owner',
    outputs: [[Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x8da5cb5b'
  },
  {
    inputs: [],
    name: 'renounceOwnership',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0x715018a6'
  },
  {
    inputs: [[Object], [Object]],
    name: 'royaltyInfo',
    outputs: [[Object], [Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x2a55205a'
  },
  {
    inputs: [[Object], [Object], [Object], [Object], [Object]],
    name: 'safeBatchTransferFrom',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0x2eb2c2d6'
  },
  {
    inputs: [[Object], [Object], [Object], [Object], [Object]],
    name: 'safeTransferFrom',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0xf242432a'
  },
  {
    inputs: [[Object], [Object]],
    name: 'setApprovalForAll',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0xa22cb465'
  },
  {
    inputs: [[Object], [Object]],
    name: 'setClaimlistActive',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0x73446dfc'
  },
  {
    inputs: [[Object], [Object]],
    name: 'setRoyalties',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0x5de42985'
  },
  {
    inputs: [[Object], [Object], [Object], [Object], [Object], [Object]],
    name: 'setURI',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0x0633b84f'
  },
  {
    inputs: [[Object]],
    name: 'supportsInterface',
    outputs: [[Object]],
    stateMutability: 'pure',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x01ffc9a7'
  },
  {
    inputs: [[Object]],
    name: 'tokens',
    outputs: [[Object], [Object], [Object], [Object], [Object], [Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x4f64b2be'
  },
  {
    inputs: [[Object]],
    name: 'transferOwnership',
    outputs: [],
    stateMutability: 'nonpayable',
    type: 'function',
    constant: undefined,
    payable: undefined,
    signature: '0xf2fde38b'
  },
  {
    inputs: [[Object]],
    name: 'uri',
    outputs: [[Object]],
    stateMutability: 'view',
    type: 'function',
    constant: true,
    payable: undefined,
    signature: '0x0e89341c'
  }
]
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
