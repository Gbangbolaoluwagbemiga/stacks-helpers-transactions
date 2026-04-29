# gbangbola-stx-transactions

[![npm version](https://img.shields.io/npm/v/gbangbola-stx-transactions.svg)](https://www.npmjs.com/package/gbangbola-stx-transactions)

STX transfers, fee estimation, and transaction confirmation for **Stacks L2**.

| | Link |
|---|------|
| **npm** | [`gbangbola-stx-transactions`](https://www.npmjs.com/package/gbangbola-stx-transactions) |
| **Repository** | [Gbangbolaoluwagbemiga/gbangbola-stx-transactions](https://github.com/Gbangbolaoluwagbemiga/gbangbola-stx-transactions) |

## Install

```bash
npm install gbangbola-stx-transactions
```

Depends on `@stacks/transactions`, `@stacks/network`, and `richiey1-stacks-helpers-types`.

## Usage

```typescript
import { transferSTX, estimateFee, waitForConfirmation } from "gbangbola-stx-transactions";

// Transfer STX
const result = await transferSTX({
  recipient: "SP...",
  amount: 1000000n,
  senderKey: "your-private-key",
});

// Estimate fees
const fees = await estimateFee("token_transfer");
// Returns: { low: 2500, medium: 3750, high: 5000 }

// Wait for transaction confirmation
const confirmation = await waitForConfirmation("0x...");
// Returns: { success: true, status: "success" }
```

## API

### `transferSTX(options)`

Send STX to a recipient. Options:

- `recipient` — Address to send to
- `amount` — Amount in uSTX (bigint)
- `senderKey` — Sender's private key
- `network?` — Stacks network (default: mainnet)
- `nonce?` — Transaction nonce
- `fee?` — Transaction fee in uSTX

### `estimateFee(txType, networkUrl?)`

Estimate fees for a transaction type. Returns `{ low, medium, high }`.

### `waitForConfirmation(txid, networkUrl?, timeoutMs?, pollMs?)`

Poll for transaction confirmation. Returns `{ success, status }`.

## Development

```bash
npm install
npm run build
```

## License

MIT

## Author

gbangbolaoluwagbemiga
