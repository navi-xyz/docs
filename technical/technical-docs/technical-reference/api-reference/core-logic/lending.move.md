# lending.move

Core lending operation.

## Events

```
struct DepositEvent has copy, drop {
    reserve: u8,
    user: address,
    amount: u64,
}

struct WithdrawEvent has copy, drop {
    reserve: u8,
    user: address,
    to: address,
    amount: u64,
}

struct BorrowEvent has copy, drop {
    reserve: u8,
    user: address,
    amount: u64,
}

struct RepayEvent has copy, drop {
    reserve: u8,
    user: address,
    amount: u64,
}

struct LiquidationCallEvent has copy, drop {
    reserve: u8,
    user: address
}
```

## Public Methods

#### `deposit<CoinType>(clock: &Clock, storage: &mut Storage, pool: &mut Pool, asset: u8, deposit_coin: Coin, amount: u64, ctx: &mut TxContext)`

Deposits `amount` of a `deposit_coin` into the protocol, minting the same `amount` of corresponding tokens to a `pool`

Emits a `DepositEvent`

#### `withdraw<CoinType>(clock: &Clock, oracle: &PriceOracle, storage: &mut Storage, pool: &mut Pool, asset: u8, amount: u64, to: address, ctx: &mut TxContext)`

Withdraws `amount` of the underlying `deposit_coin`, to the `to` account, i.e. redeems the underlying token and burns the tokens in the `pool`.

Emits a `WithdrawEvent`

#### `borrow<CoinType>(clock: &Clock, oracle: &PriceOracle, storage: &mut Storage, pool: &mut Pool, asset: u8, deposit_coin: Coin, amount: u64, ctx: &mut TxContext)`

Borrows `amount` of `deposit_coin` with, sending the `amount` to the `tx_context::sender(ctx)` sender account

Emits a `BorrowEvent`

#### `repay<CoinType>(clock: &Clock, oracle: &PriceOracle, storage: &mut Storage, pool: &mut Pool, asset: u8, repay_coin: Coin, amount: u64, ctx: &mut TxContext)`

Repays a debt `amount` of `repay_coin` for the `tx_context::sender(ctx)` sender account

Emits a `RepayEvent`
