# VHDL Counter: Potential Integer Overflow

This repository demonstrates a potential integer overflow bug in a simple VHDL counter and its solution.

## Bug Description

The `buggy_counter.vhdl` file contains a VHDL counter that increments a signal (`internal_count`) up to 15. However, there's a potential issue: if, due to some unforeseen circumstance, the `internal_count` somehow exceeds 15 (though it's constrained), the behavior is undefined according to the LRM. While this is unusual in this simple example, more complex counters with less-obvious increment conditions or external influences could exhibit subtle and harder-to-debug behavior from this kind of issue. 

## Solution

The `buggy_counter_fixed.vhdl` file provides a corrected version of the counter that explicitly handles the case where `internal_count` reaches the maximum value (15), preventing overflow and ensuring predictable behavior.  A simple check is added to prevent this unexpected condition.