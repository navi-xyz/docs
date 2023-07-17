# calculator.move

Interest and pool rate calculation.

### Public Methods

#### `caculate_utilization(storage: &mut Storage, asset: u8, amount: u256): u256`

Returns the utilisation rate of a pool.

$$
U = B_a / (C_a + B_a)
$$

Where `B` and `C` are the total borrows and total cash of asset `a`

#### `calculate_borrow_rate(storage: &mut Storage, asset: u8, amount: u256): u256`

Get the borrow rate of a pool's asset

#### `calculate_supply_rate(storage: &mut Storage, asset: u8, amount: u256): u256`

Get the supply rate of a pool's asset

#### `calculate_compounded_interest(current_timestamp: u64, last_update_timestamp: u64, rate: u256): u256`

Compound interest calculation implementation

#### `calculate_linear_interest(current_timestamp: u64, last_update_timestamp: u64, rate: u256): u256`

Linear interest calculation implementation
