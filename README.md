# Koii Namespace Wrapper

## 📝 Project Overview

The Koii Namespace Wrapper is a sophisticated utility package designed to abstract and simplify the complexities of developing and managing tasks on the Koii Network. It provides a unified and standardized API for blockchain interactions, distributed computing, and task node operations.

### 🌟 Key Features

- 🔒 **Secure State Management**: Persistent storage using NeDB for task-specific data
- 🌐 **Blockchain Integration**: Direct interface with Koii Network through Web3.js
- 📂 **Unified File System Operations**: Standardized access for local and distributed environments
- 🔐 **Cryptographic Functions**: Built-in payload signing and verification
- 💰 **Task Distribution Support**: Comprehensive reward and distribution management
- 📝 **Advanced Logging**: Structured logging for debugging and monitoring
- 🚀 **Express Server**: Integrated HTTP server for task communication

## 🗂️ Repository Structure

```
namespace-wrapper/
│
├── src/                    # TypeScript source code
│   ├── index.ts            # Main implementation of NamespaceWrapper
│   └── types.ts            # TypeScript type definitions
│
├── webasm_bincode_deserializer/   # WebAssembly utilities
│   ├── bincode_js.js       # Bincode deserialization logic
│   ├── bincode_js.d.ts     # TypeScript definitions
│   └── zstd.wasm           # WebAssembly module
│
├── .eslintrc.js            # ESLint configuration
├── .gitignore              # Git ignore rules
├── package.json            # NPM package configuration
├── tsconfig.json           # TypeScript compiler configuration
└── yarn.lock               # Yarn dependency lockfile
```

## 🔧 Technical Details

### 💻 Technologies Used

- **Language**: TypeScript
- **Package Manager**: Yarn
- **Blockchain**: Koii Network (Web3.js)
- **Database**: NeDB (Embedded JavaScript database)
- **Web Framework**: Express.js
- **Cryptography**: TweetNaCl for signing and verification
- **Serialization**: Bincode, WebAssembly

### 🏗️ Architecture Overview

The Namespace Wrapper follows a modular architecture designed to:
- Abstract complex blockchain interactions
- Provide standardized interfaces for task development
- Ensure secure and efficient state management
- Enable flexible file system operations
- Support robust communication and validation mechanisms

## 📁 File Contents Description

### `src/index.ts`
- Core implementation of `NamespaceWrapper` class
- Handles task node operations, blockchain interactions, and state management
- Provides methods for:
  - Data storage (storeSet, storeGet)
  - Payload signing
  - Submission validation
  - Task distribution
  - Node communication

### `src/types.ts`
- TypeScript type definitions for:
  - Task states
  - Submission states
  - Critical interface contracts
- Ensures type safety and provides structured typing

### `webasm_bincode_deserializer/`
- WebAssembly and binary code deserialization utilities
- Contains:
  - `bincode_js.js`: Binary deserialization logic
  - `bincode_js.d.ts`: TypeScript type definitions
  - `zstd.wasm`: WebAssembly compression module

## 🚀 Installation

```bash
npm install @_koii/namespace-wrapper
# or
yarn add @_koii/namespace-wrapper
```

## 🧑‍💻 Basic Usage

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper'

// Store and retrieve data
await namespaceWrapper.storeSet('myKey', 'myValue')
const value = await namespaceWrapper.storeGet('myKey')

// Payload signing
const signedPayload = await namespaceWrapper.payloadSigning({
  data: 'example'
})

// Validate submission
const isValid = await namespaceWrapper.validateAndVoteOnNodes(
  async (submissionValue, round, nodePublicKey) => {
    // Custom validation logic
    return true
  },
  currentRound
)
```

## 📚 Documentation

For detailed API documentation, visit the [Koii Network Documentation](https://www.koii.network/docs/develop/write-a-koii-task/namespace-wrapper/the-namespace-object).

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🆘 Support

- 🌍 Website: [Koii Network](https://www.koii.network)
- 💬 Discord: [Koii Network Discord](https://discord.com/invite/koii-network)
- 📄 Documentation: [Koii Docs](https://docs.koii.network)

## 📜 License

Distributed under the ISC License.

## 🏷️ Version

Current Version: 1.0.23

## 📞 Contact

Koii Network - [@koiinetwork](https://twitter.com/koiinetwork)

Project Link: [https://github.com/koii-network/namespace-wrapper](https://github.com/koii-network/namespace-wrapper)