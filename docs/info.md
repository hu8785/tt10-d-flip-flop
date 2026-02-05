<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than 512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This project implements a simple D flip-flop using Verilog. A D flip-flop is a fundamental sequential logic element that captures the value of the D input at a specific clock edge and holds it stable on the output.

The design features:
- Single data input (din) connected to ui_in[0]
- Single data output (q) connected to uo_out[0]
- Synchronous reset (active low) via rst_n
- Clock input

The flip-flop captures the input value on the rising edge of the clock when reset is not active (rst_n = 1). When reset is active (rst_n = 0), the output is cleared to 0.

## How to test

To test the D flip-flop:

1. Apply reset (set rst_n = 0) and verify that the output q = 0
2. Release reset (set rst_n = 1)
3. Set the input din (ui_in[0]) to 1
4. Apply a clock pulse and verify that output q (uo_out[0]) becomes 1
5. Change input din to 0
6. Apply another clock pulse and verify that output q becomes 0
7. Verify that the output only changes on clock edges, not when the input changes

The testbench (test/test.py) includes automated tests that verify this behavior.

## External hardware

No external hardware is required for basic operation. You can observe the flip-flop behavior using:
- An input switch or button connected to ui_in[0] for the data input
- An LED connected to uo_out[0] to observe the output state
- The onboard clock signal
