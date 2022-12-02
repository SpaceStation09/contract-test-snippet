# Contract Test Snippet

This is a vscode snippet to help developers to write test files in more convenient way (for hardhat framework with ethers.js). It includes several commonly used functions.

## Language Support

- typescript

## Available Snippets

### `getRevertMsg`

prefix: "revert", "revertMsg", "getRevertMsg"

```typescript
const getRevertMsg = (msg: string): string =>
  `VM Exception while processing transaction: reverted with reason string '${msg}'`;
```

### `expectRevert`

prefix: "er", "expectRevert", "revert"

```typescript
await expect().to.be.revertedWith(getRevertMsg("Example Error Msg"));
```

### `takeSnapshot`

prefix: "takesnapshot", "tsnapshot"

```typescript
async function takeSnapshot() {
  return network.provider.send("evm_snapshot", []);
}
```

### `revertToSnapShot`

prefix: "rs", "revertsnapshot"

```typescript
async function revertToSnapShot(id: string) {
  await network.provider.send("evm_revert", [id]);
}
```

### `advanceTime`

prefix: "advance", "at"

```typescript
async function advanceTime(time: number) {
  await network.provider.send("evm_increaseTime", [time]);
}
```

### `advanceBlock`

prefix: "advance", "ab"

```typescript
async function advanceBlock() {
  await network.provider.send("evm_mine", []);
}
```

### `advanceTimeAndBlock`

prefix: "advance", "atb"

```typescript
async function advanceTimeAndBlock(time: number): Promise<providers.Block> {
  await advanceTime(time);
  await advanceBlock();
  return Promise.resolve(ethers.provider.getBlock("latest"));
}
```

### `numberToBytes32Hex`

prefix: "n2b", "number2bytes", "nb"

```typescript
hexZeroPad(hexlify(number), 32);
```

### `newTestCase`

prefix: "it"

```typescript
it("", async () => {});
```

### `newTestCategory`

prefix: "describe"

```typescript
describe("", () => {});
```

## Contribute

Any contribution is welcomed to make it better.

If you have any questions, please create an [issue](https://github.com/SpaceStation09/contract-test-snippet/issues).

**Enjoy!**
