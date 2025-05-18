# ALU Interview - Minimum Operations

This project contains a solution for the "Minimum Operations" coding challenge.

## Task: 0. Minimum Operations

In a text file, there is a single character `H`. Your text editor can execute only two operations in this file: `Copy All` and `Paste`. Given a number `n`, write a method that calculates the fewest number of operations needed to result in exactly `n` `H` characters in the file.

### Requirements
- Prototype: `def minOperations(n)`
- Returns an integer.
- If `n` is impossible to achieve or `n <= 1`, return `0`.

### Example
For `n = 9`:
`H` => `Copy All` => `Paste` => `HH` (2 ops)
`HH` => `Paste` => `HHH` (3 ops total)
`HHH` => `Copy All` => `Paste` => `HHHHHH` (5 ops total)
`HHHHHH` => `Paste` => `HHHHHHHHH` (6 ops total)
Result: 6 operations.

### Approach
The problem can be solved by finding the sum of the prime factors of `n`.
If we have `k` characters and want to achieve `k * f` characters (where `f` is a factor):
1. `Copy All`: 1 operation (clipboard now holds `k` characters).
2. `Paste` (`f-1` times): `f-1` operations.
This step takes a total of `1 + (f-1) = f` operations to multiply the current character count by `f`.
Thus, to get `n` characters starting from 1, if `n = p1 * p2 * ... * pk` (prime factorization), the total minimum operations will be `p1 + p2 + ... + pk`.

### File Structure
- `minimum_operations/`: Directory containing the solution.
  - `0-minoperations.py`: Python script with the `minOperations` function.
  - `0-main.py`: Main file for testing (as provided in the problem).

### Usage
To test the solution:
1. Ensure `0-minoperations.py` and `0-main.py` are in the `minimum_operations` directory.
2. Make the files executable:
   ```bash
   chmod +x minimum_operations/0-main.py
   chmod +x minimum_operations/0-minoperations.py
   ```
3. Run the main test file (e.g., from the root of the `alu-interview` project):
   ```bash
   ./minimum_operations/0-main.py
   ```

### Constraints
- Python 3.4.3
- PEP 8 style
- All files start with `#!/usr/bin/python3`
- All files end with a newline 