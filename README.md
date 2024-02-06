# BBS for VC Library

Sign, selectively disclose, and verify credentials/presentations with BBS signatures and JavaScript!

This library is an independent implementation of the `bbs-2023` cryptosuite for verifiable credentials. The algorithms and functions are from sections 3.3-3.5 of [Data Integrity ECDSA Cryptosuites v1.0](https://w3c.github.io/vc-di-ecdsa) where they are specified and described.

## High Level API Design

* **Add Base**: unsigned document, key pair, mandatory pointers, generators; optional: proof configuration options, hmac key, proof key pair, stuff for JSON-LD document loading. Returns signed base document.
* **Verify Base**: signed base document, public key (rather than extracting it from document or web), generators; optional: stuff for JSON-LD document loading. Returns true/false.
* **Derive Proof**: signed base document, selective pointers, generators; optional: stuff for JSON-LD document loading. Returns signed derived document.
* **Verify Derived**: signed derived document, public key, generators; optional: stuff for JSON-LD document loading. Returns true/false.

Note: For verification functions the issuers public key as a `Uint8Array` without any multibase prefixes must be furnished. This library does not perform any external requests to obtain key material for verification.

## Examples

See the `examples` directory for usage examples including JSON-LD document (context) loading. Example inputs are in the `examples/input` directory.

# Generated API from JSDoc

<!-- Generated with the command
    npx jsdoc2md lib/signBase.js lib/verifyBase.js lib/derive.js lib/verifyDerived.js > documentation/apiDoc.md
    and then copy and paste below.
-->

## Functions
