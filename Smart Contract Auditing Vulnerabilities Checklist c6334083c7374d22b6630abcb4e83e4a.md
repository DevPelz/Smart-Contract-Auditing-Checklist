# Smart Contract Auditing Vulnerabilities / Checklist

### Bare minimum audit checklist:

| Vulnerability | Severity | Description |
| --- | --- | --- |
| External Calls to Arbitrary Addresses | High | Allowing external calls to arbitrary addresses, exposing the contract to potential exploits. |
| Checks-Effects-Interactions Pattern Violation / Reentrancy | High, Medium | Violating the Checks-Effects-Interactions pattern, potentially leading to reentrancy attacks. |
| Missing Validation / Input Validation Violation | High, Medium | Failing to validate inputs, leading to unexpected behavior and potential |
| Flashloan Attack | High | Vulnerabilities related to flashloan mechanisms, allowing malicious manipulation. |
| Inconsistent Data | High, Medium | Inconsistencies in data handling, leading to potential security risks. |
| Floating Pragma | Low | Insecure usage of pragma directives, potentially leading to vulnerabilities. |
| Ether Theft | High | Vulnerabilities allowing unauthorized access leading to ether theft. |
| Timestamp dependence | High | Reliance on timestamps, exposing the contract to timestamp manipulation attacks. |
| Divide before multiply | High/Medium | Arithmetic vulnerabilities due to incorrect order of divide and multiply operations. |
| ERC’s conformance | Medium | Non-compliance with ERC standards, potentially leading to interoperability issues. |
| Strict equality | Medium | Risks associated with using strict equality checks in certain contexts. |
| Using delegatecall | High/Medium | Risks associated with using delegatecall, allowing potential code execution vulnerabilities. |
| Use of tx.origin | High | Security risks associated with the use of tx.origin. |
| Arithmetic correctness | High/Medium | Ensuring correct arithmetic operations to prevent vulnerabilities. |
| Logical issues | Medium | Identifying and addressing logical issues in contract design and execution. |
| Centralization of control | Medium | Risks associated with a centralized control structure in the smart contract. |
| Missing zero address validation | Low | Failing to validate zero addresses, leading to potential vulnerabilities. |
| Return values of low level calls | Medium | Risks associated with handling return values of low-level calls. |
| Access control | High/Medium | Ensuring proper access control mechanisms to prevent unauthorized actions. |
| Malicious libraries/outdated versions | High/Medium | Risks associated with using malicious or outdated external libraries. |
| Sandwich attacks (front-running/back-running) | High | Manipulation of transaction order to exploit price discrepancies. |
| Block stuffing | Medium | Deliberate insertion of unnecessary operations to increase block size. |
| Metamorphic contracts (bytecode mutation) | High | Smart contracts that can change their bytecode, making analysis challenging. |
| Signature replay attacks | High | Reuse of valid signatures to execute unauthorized transactions. |
| Short address attacks (Solidity <0.5.0) | Medium | Exploiting the lack of input validation in early Solidity versions. |
| Token approval griefing | Medium | Exploiting vulnerabilities in token approval mechanisms. |
| Force-feeding attacks | High | Manipulating contract state through forced transactions. |
| Weak on-chain randomness  | High | Exploitable randomness generation in smart contracts. |
| Unbounded gas consumption by returning a lot of data | High | Consuming excessive gas by returning large data sets. |
| Default enum values | Medium | Security risks associated with default enum values. |
| Storage collisions with delegate call | High | Unintended data corruption due to storage collisions. |
| Function selector collisions (zero selectors) | Medium | Collisions in function selectors leading to unexpected behavior. |
| Hash collisions with dynamic types (packed ABI encoding | High | Vulnerabilities arising from hash collisions in dynamic types. |
| Vulnerable Rebalancing/Buyback Mechanics | High | Risks associated with flawed token rebalancing/buyback strategies. |
| Problems with ERC20 decimals | Medium | Security issues related to ERC20 token decimals. |
| DoS with revert or infinite gas consumption | High | Denial-of-Service attacks through revert or infinite gas usage. |
| DoS due to Underflow | High | Denial-of-Service attacks exploiting underflow vulnerabilities. |
| Unbounded loops (pagination) | High | Potential gas exhaustion due to unbounded loops. |
| Duplicate array elements | Medium | Risks associated with arrays containing duplicate elements. |
| Unlimited Token allowance | Medium | Risks arising from unlimited token allowances. |
| Misinitialization of contracts (ownership/proxy) | High | Security risks due to incorrect contract initialization. |
| Asserting contract from Code Size | Medium | Vulnerabilities related to assertions based on code size. |
| Unsafe Typecast | High | Risks associated with unsafe typecasting in smart contracts. |
| Message call with hard-coded gas | Medium | Security issues with message calls having hard-coded gas values. |
| Improper Array Deletion | Medium | Security vulnerabilities arising from improper array deletion. |
| Dirty High Order Bits | Medium | Risks associated with manipulation of high-order bits. |
| Transaction order manipulation | High | Exploiting vulnerabilities in the order of transaction execution. |
| Uninitialized Proxies | High | Security issues related to uninitialized proxy contracts. |
| Reinitialization Vulnerability | High/Medium | Risks associated with contract reinitialization. |
| Flawed Math- Transaction Replay Attack | High | Risks related to flawed mathematical operations leading to replay attacks. |
| Incorrect Special Character Handling | Medium | Security vulnerabilities due to mishandling of special characters. |
| Governance Takeovers | High | Risks associated with potential takeover of governance mechanisms. |

### Additional Checks

- Check for Business Logic Vulnerabilities
- Check for correct inheritance
- Check if the spot price from an `AMM` as an oracle is used
- Check for tokens that use too many or too few decimals
- Check if internal accounting is mixed with actual balances
- Check if the Contract approves tokens before `transferFrom` to avoid revert
- Check if state variable layout is followed when using delegate-call in proxy contracts
- Check if events are emitted on critical functions