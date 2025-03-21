# Koii Namespace Wrapper

## Project Overview

The Koii Namespace Wrapper is a utility package designed to simplify task development and management within the Koii Network ecosystem. It provides a comprehensive abstraction layer for interaction with Koii task infrastructure, enabling developers to create decentralized tasks with enhanced functionality and seamless blockchain integration.

### Key Features

- **Flexible Task Node Management**: Supports both task node-administered and local testing environments
- **Blockchain Interaction**: Simplified methods for blockchain-related operations
- **Database Management**: Integrated database handling with NeDB
- **File System Abstraction**: Cross-environment file system operations
- **Submission and Distribution Workflows**: Built-in methods for task submissions, audits, and reward distributions
- **Cryptographic Utilities**: Signature verification and payload signing
- **Environment Adaptability**: Seamless switching between task node and local development modes

## Repository Structure

```
namespace-wrapper/
│
├── src/                       # Source code directory
│   ├── index.ts               # Main implementation of NamespaceWrapper
│   └── types.ts               # TypeScript type definitions
│
├── webasm_bincode_deserializer/  # WebAssembly and Bincode related utilities
│   ├── bincode_js.js
│   ├── bincode_js.d.ts
│   └── zstd.wasm
│
├── package.json               # Project configuration and dependencies
├── tsconfig.json              # TypeScript compiler configuration
└── README.md                  # Project documentation
```

## Technical Details

### Technologies Used

- **Language**: TypeScript
- **Runtime**: Node.js
- **Blockchain**: Koii Network (K2)
- **Database**: NeDB (Embedded JavaScript Database)
- **Cryptography**: 
  - TweetNaCl for signature operations
  - bs58 for base58 encoding/decoding

### Architecture Overview

The Namespace Wrapper follows a modular and adaptive architecture:

1. **Core Class (`NamespaceWrapper`)**: 
   - Central class managing task-related operations
   - Supports both task node-administered and local testing modes
   - Provides methods for blockchain interactions, file system operations, and task management

2. **Generic Handler**:
   - Facilitates communication between the task and the Koii task node
   - Handles cross-environment method invocations
   - Provides fallback mechanisms for testing and development

3. **Environment Adaptability**:
   - Dynamically adjusts functionality based on the execution context
   - Supports seamless transition between task node and local environments

## Core Functionalities

### Key Methods

- `storeGet(key)`: Retrieve values from the embedded database
- `storeSet(key, value)`: Store key-value pairs in the database
- `payloadSigning(body)`: Sign payloads for blockchain submission
- `verifySignature(signedMessage, pubKey)`: Verify cryptographic signatures
- `validateAndVoteOnNodes()`: Validate task submissions across nodes
- `selectAndGenerateDistributionList()`: Manage reward distribution workflows

## Installation

```bash
npm install @_koii/namespace-wrapper
```

## Usage Example

```typescript
import { namespaceWrapper } from '@_koii/namespace-wrapper';

async function myTask() {
  // Store a value
  await namespaceWrapper.storeSet('key', 'value');
  
  // Retrieve a value
  const storedValue = await namespaceWrapper.storeGet('key');
  
  // Sign a payload
  const signedPayload = await namespaceWrapper.payloadSigning({ data: 'example' });
}
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the ISC License.

## Contact

For more information, visit [Koii Network](https://www.koii.network)