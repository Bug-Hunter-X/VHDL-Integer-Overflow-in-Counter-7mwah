# VHDL Integer Overflow Bug
This repository demonstrates a common bug in VHDL code involving integer overflow in a counter. The `buggy_counter.vhdl` file contains the buggy code, while `fixed_counter.vhdl` provides a corrected version.

## Bug Description
The original VHDL code implements a simple counter using the `integer` type.  However, the `integer` type in VHDL is unbounded, and assigning a value beyond its allowed range causes unexpected behavior or simulation errors.  When the counter reaches its maximum value (15 in this case), incrementing it leads to undefined behavior. This is especially problematic in synthesis, potentially resulting in unpredictable hardware behavior.

## Solution
The `fixed_counter.vhdl` uses `unsigned` type instead of `integer` to ensure that overflow is handled correctly by the hardware.  The `unsigned` type is a fixed-size, bounded type, ensuring that the counter wraps around properly without causing errors.