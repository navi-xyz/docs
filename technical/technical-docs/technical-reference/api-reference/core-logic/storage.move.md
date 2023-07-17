# storage.move

## Error Codes

```
STORAGE_CALLER_NOT_OWNER: u64 = 43001
STORAGE_CALLER_NOT_CONFIGURATOR: u64 = 43002
STORAGE_NO_MORE_RESERVES_ALLOWED: u64 = 43003
STORAGE_INVALID_INDEX: u64 = 43004
STORAGE_AMOUNT_NOT_ENOUGH: u64 = 43005
STORAGE_DUPLICATE_RESERVE: u64 = 43006
```

#### `pause(storage: &Storage): bool`

Check if protocol is in `paused` state

#### `get_supply_cap_ceiling(storage: &mut Storage, asset: u8): u256`

Retuns the supply cap of an asset

#### `get_borrow_cap_ceiling_ratio(storage: &mut Storage, asset: u8): u256`

Retuns the borrow cap of an asset

#### `get_total_supply(storage: &mut Storage, asset: u8): (u256, u256)`

Returns the total supplied of an asset

#### `get_index(storage: &mut Storage, asset: u8): (u256, u256)`

Returns the `borrow_index` and the `supply_index` of an asset

#### `get_borrow_rate_factors(storage: &mut Storage, asset: u8): (u256, u256, u256, u256, u256)`

Returns the parameters of the Interest Rate Model of a specific asset, e.g.:

* `base_rate`
* `multiplier`
* `jump_rate_multiplier`
* `reserve_factor`&#x20;
* `optimal_utilization`

For a comprehensive overview of these parameters, refer to [this article](https://ianm.com/posts/2020-12-20-understanding-compound-protocols-interest-rates#interest-rate-spikes)

#### `get_liquidation_factors(storage: &mut Storage, asset: u8): (u256, u256, u256)`

Returns the liquidation parameters of an asset, e.g.:

* `ratio`
* `bonus` i.e. the bonus discount given to the liquidator
* `threshold` i.e. the liquidation threshold below which a position gets liquidated

#### `get_last_update_timestamp(storage: &Storage, asset: u8): u64`

Get the latest timestamp at which the borrow rate was updated

#### `get_current_rate(storage: &mut Storage, asset: u8): (u256, u256)`

Returns the `supply_rate` and `borrow_rate` of an asset

#### `get_user_balance(storage: &mut Storage, asset: u8, user: address): (u256, u256)`

Returns a user's `borrow_balance` and `supply_balance`

#### `get_user_assets(storage: &Storage, user: address): (vector, vector)`

Returns two `vectors` with the user's `collateral` assets and `loans` assets

#### `get_asset_ltv(storage: &Storage, asset: u8): u256`

Returns an `asset`'s LTV

#### `get_coin_type(storage: &Storage, asset: u8): String`

Returns a coin's type
