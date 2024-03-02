# Solidity Notes

## Introduction

Solidity is a statically typed, contract-oriented programming language designed for developing smart contracts on blockchain platforms, particularly Ethereum. It was influenced by JavaScript, C++, and Python and is used to write code for executing smart contracts on decentralized applications (DApps).

## 🚀 Why Solidity

- **Blockchain Development**: Solidity is specifically designed for blockchain development, making it well-suited for creating smart contracts and DApps.
- **Smart Contracts**: Solidity allows developers to define and deploy smart contracts that can automatically execute predefined functions when certain conditions are met.
- **Ethereum Ecosystem**: Solidity is the primary language used for writing smart contracts on the Ethereum blockchain, which is one of the largest blockchain ecosystems.
- **Security**: Solidity includes features such as type safety, access control, and error handling to help developers write secure smart contracts.
- **Interoperability**: Solidity contracts can interact with other contracts on the Ethereum blockchain and with external systems, enabling complex decentralized applications.

## Advantages of Solidity

- **Turing Completeness**: Solidity is a Turing-complete language, meaning it can express any computation that can be performed by a computer, making it powerful and versatile.
- **Smart Contract Deployment**: Solidity contracts can be deployed on public blockchains, allowing for trustless execution without the need for intermediaries.
- **Immutable Contracts**: Once deployed, Solidity contracts are immutable and cannot be altered, providing transparency and security.
- **Decentralized Applications**: Solidity enables the development of decentralized applications (DApps) that run on blockchain networks, offering censorship resistance and trustlessness.
- **Community Support**: Solidity has a large and active developer community, providing resources, libraries, and tools to support developers in building smart contracts and DApps.
- **EVM Compatibility**: Solidity is compatible with the Ethereum Virtual Machine (EVM), allowing smart contracts to execute on the Ethereum network.

## 🛠️ Where Solidity is Used

- **Decentralized Finance (DeFi)**: Solidity is widely used in DeFi applications for creating smart contracts that facilitate lending, borrowing, trading, and other financial transactions.
- **Non-Fungible Tokens (NFTs)**: Solidity is used for creating NFT smart contracts that represent unique digital assets, such as art, collectibles, and in-game items.
- **Decentralized Exchanges (DEXs)**: Solidity powers the smart contracts behind decentralized exchanges, allowing users to trade cryptocurrencies without the need for intermediaries.
- **Decentralized Autonomous Organizations (DAOs)**: Solidity is used to create DAO smart contracts that govern decentralized organizations and make decisions based on predefined rules.
- **Tokenization**: Solidity is used to create custom tokens on the Ethereum blockchain, enabling projects to raise funds through initial coin offerings (ICOs) or token sales.
- **Supply Chain Management**: Solidity can be used to create smart contracts for tracking and managing supply chain processes, providing transparency and traceability.

## Types

- Solidity is a statically typed language, which means that the type of each variable (state and local) needs to be specified. Solidity provides several elementary types which can be combined to form complex types.

> The concept of “undefined” or “null” values does not exist in Solidity, but newly declared variables always have a default value dependent on its type.

### Value Types

- Value-type data stores information directly in the memory. The variables that are then associated with these value types allow duplication in assignments or functions. Despite being duplicated, value-type data can maintain an independent copy of each of the duplicated variables.

- This means that if you make changes in the value of the duplicated variable, the original variable remains unaffected. Some common examples of value types in Solidity are listed as follows.

#### 1. Addresses

- Addresses are used to store Ethereum addresses. They are 20-byte values and are capable of storing Ethereum addresses of contracts or external accounts.
- There are two different types of address values – “address” and “address Payable.”
- Fundamentally, they both serve the same purpose, except for the fact that “address payable” can be used to assist in transferring Ether.

```solidity
address public myAddress = 0x1234567890123456789012345678901234567890;
```

#### 2. Enums

- Enums, abbreviated from enumerators, are the basic value types in Solidity. This data type is specifically used for defining constant values. Enums are used for improving the readability and maintenance of a smart contract.

```solidity
enum State { Pending, Approved, Rejected }
State public currentState = State.Pending;
```

#### 3. Booleans

- The Boolean value data type is an integral part of Solidity, used primarily for data types with binary results. Any “bool” data type can have two fixed values – (True/False, Yes/No). In Solidity, the default value of Boolean is false. Solidity supports all commonly used Boolean logic.
- The language, however, does not support the translation of boolean data types into integers.

```solidity
bool public isApproved = true;
```

#### 4. Signed Integers

- A signed integer is used to store positive/negative values in smart contracts and is usually declared using the “int” keyword. Abbreviated from “int256”, it takes up to 32 bytes of storage by default.
- If you choose to reduce the byte storage, you can specify the number of bits you want each integer to take up (int64, int8, etc.). It is important that you classify the number of bits in steps of 8!

```solidity
int8 public myInt8 = -10;    // 8-bit signed integer (-128 to 127)

int16 public myInt16 = -500; // 16-bit signed integer (-32,768 to 32,767)

int32 public myInt32 = -20000; // 32-bit signed integer (-2,147,483,648 to 2,147,483,647)

int64 public myInt64 = -5000000; // 64-bit signed integer (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807)

int256 public myInt256 = -123456789; // 256-bit signed integer (-2^255 to 2^255 - 1)
```

#### 5. Unsigned Integers

- Unsigned integers in Solidity are used to store non-negative values (0 and above). Declared by using the keyword “uint,” Unsigned Integers also take up to 32 bytes of storage by default.
- Just like signed integers, you can specify the storage unsigned integers can take by specifying the number of bits (in steps of 8) that can be allocated to them.

```solidity
uint8 public myUint8 = 255;    // 8-bit unsigned integer (0 to 255)

uint16 public myUint16 = 500;  // 16-bit unsigned integer (0 to 65,535)

uint32 public myUint32 = 20000; // 32-bit unsigned integer (0 to 4,294,967,295)

uint64 public myUint64 = 5000000; // 64-bit unsigned integer (0 to 18,446,744,073,709,551,615)

uint256 public myUint256 = 123456789; // 256-bit unsigned integer (0 to 2^256 - 1)
```

#### 6. Bytes

- The Byte data type points to 8-bit signed integers. The Byte value type facilitates data storage in binary values (1s and 0s). The default value of a byte type is 0x00.

```solidity
bytes32 public myBytes = 0x1234567890123456789012345678901234567890123456789012345678901234;
```
