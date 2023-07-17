# validation.move

## Error Codes

```
VALIDATION_INVALID_AMOUNT: u64 = 44001
VALIDATION_NO_ACTIVE_RESERVE: u64 = 44002
VALIDATION_RESERVE_FROZEN: u64 = 44003
VALIDATION_MAX_SUPPLY_CAP: u64 = 44004
VALIDATION_MAX_BORROW_CAP: u64 = 44004
VALIDATION_BALANCE_NOT_ENOUGH: u64 = 44005
```

## Read Methods

Validation of user actions

#### `validate_deposit(storage: &mut Storage, asset: u8, amount: u64)`

#### `validate_borrow(storage: &mut Storage, asset: u8, amount: u64)`

#### `validate_repay(_storage: &mut Storage, _asset: u8, amount: u64)`
