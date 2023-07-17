# pool.move

## Error Codes

```
POOL_CALLER_NOT_OWNER: u64 = 42001;
```

## Events

```
struct PoolCreate has copy, drop {
    creator: address,
}

struct PoolBalanceRegister has copy, drop {
    sender: address,
    amount: u64,
    new_amount: u64,
    pool: String,
}

struct PoolDeposit has copy, drop {
    sender: address,
    amount: u64,
    pool: String,
}

struct PoolWithdraw has copy, drop {
    sender: address,
    recipient: address,
    amount: u64,
    pool: String,
}

struct PoolOwnerSetting has copy, drop {
    sender: address,
    owner: u256,
    value: bool,
}

struct PoolAdminSetting has copy, drop {
    sender: address,
    admin: u256,
    value: bool,
}
```

## Write Methods

#### `create_pool<CoinType>(ctx: &mut TxContext)`

Creates a new pool for a specific coin type.&#x20;

Emits: `PoolCreate`

## Admin Methods

#### `set_owner(pool_admin_cap: &mut PoolAdminCap, owner: u256, val: bool, ctx: &mut TxContext)`

Sets the owner of a pool

Emits: `PoolOwnerSetting`

#### `set_admin(pool_admin_cap: &mut PoolAdminCap, admin: u256, val: bool, ctx: &mut TxContext)`

Sets the admin of a pool

Emits: `PoolAdminSetting`
