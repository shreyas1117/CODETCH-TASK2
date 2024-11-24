# CODETCH-TASK2
NAME :SHREYAS S

COMPANY:CODTECH IT SOLUTIONS

INTERN ID: CT6WDS2311

DOMAIN: VLSI

DURATION:NOVEMBER TO DECEMBER 2024

OVERVIEW OF A PROJECT

A finite state machine (FSM) in Verilog is a powerful method for designing digital systems that transition between different states based on inputs and clock cycles. Verilog, a hardware description language, allows for the implementation of FSMs by defining states, transitions, and outputs using always blocks and case statements. FSMs can be categorized into two types: **Moore machines**, where outputs depend solely on states, and **Mealy machines**, where outputs depend on both states and inputs. By leveraging Verilog's constructs, engineers can create efficient, scalable, and maintainable digital designs that are crucial for various applications, from simple control systems to complex integrated circuits.


Certainly! Here's a description of the given Verilog code for a vending machine:

### Description:
This Verilog module simulates a vending machine that accepts 5 and 10 rupee coins and dispenses items accordingly. The module uses a finite state machine (FSM) with three states: `s0` (0 rupees), `s1` (5 rupees), and `s2` (10 rupees).

**Inputs:**
- `clk`: Clock signal.
- `rst`: Reset signal.
- `in`: 2-bit input representing coins inserted (01 for 5 rupees, 10 for 10 rupees).

**Outputs:**
- `out`: Output signal indicating if an item is dispensed (1 for dispensed, 0 for not dispensed).
- `change`: 2-bit output indicating change returned (01 for 5 rupees, 10 for 10 rupees).

### Working:
1. **State Definitions:** The states represent the total amount inserted.
2. **State Transition Logic:** The `always` block with `posedge clk or posedge rst` handles state transitions and resets the machine to the initial state (`s0`) upon reset.
3. **Next State and Output Logic:** The combinational `always` block determines the next state and output based on the current state and input.
    - **State `s0`:** 
        - If 5 rupees are inserted, transition to `s1`.
        - If 10 rupees are inserted, transition to `s2`.
    - **State `s1`:** 
        - If no additional input, return 5 rupees as change and go back to `s0`.
        - If another 5 rupees are inserted, transition to `s2`.
        - If 10 rupees are inserted, dispense an item and return to `s0`.
    - **State `s2`:** 
        - If no additional input, return 10 rupees as change and go back to `s0`.
        - If 5 rupees are inserted, dispense an item and return to `s0`.
        - If 10 rupees are inserted, dispense an item, return 5 rupees as change, and go back to `s0`.

This FSM ensures the vending machine operates correctly, handling coin inputs, dispensing items, and returning change as needed.
