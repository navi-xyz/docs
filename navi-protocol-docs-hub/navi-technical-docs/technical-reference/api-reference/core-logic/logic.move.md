# logic.move

Core logic functionally that implements state-mutating functions.

## Read Methods

#### `user_health_factor(storage: &mut Storage, oracle: &PriceOracle, user: address): u256`

#### `user_health_collateral_value(oracle: &PriceOracle, storage: &mut Storage, user: address): u256`

#### `user_health_loan_value(oracle: &PriceOracle, storage: &mut Storage, user: address): u256`

#### `user_loan_value(oracle: &PriceOracle, storage: &mut Storage, asset: u8, user: address): u256`

#### `user_collateral_value(oracle: &PriceOracle, storage: &mut Storage, asset: u8, user: address): u256`

#### `user_collateral_balance(storage: &mut Storage, asset: u8, user: address): u256`

#### `user_loan_balance(storage: &mut Storage, asset: u8, user: address): u256`
