This repository contains an RTL implementation of a Universal Asynchronous Receiver/Transmitter (UART) based on AXI4-Stream interfaces.
UART is one of the most widely used communication protocols in digital systems. It transmits serial data with start/stop framing bits and is often used in FPGA/SoC systems for debugging, console communication, and device interfacing.

This project is adapted from the verilog-uart
 repository by Alex Forencich.

Project Structure

uart_rx.v – UART receiver

uart_tx.v – UART transmitter

README.md – Documentation (this file)

UART RX (uart_rx.v)

The receiver (uart_rx.v) implementation remains unchanged.
It samples incoming serial data (rxd), reconstructs bytes, and drives them out over an AXI4-Stream interface.

Features:

Start/stop bit detection

Frame error and overrun detection

Configurable prescaler for baud rate

UART TX (uart_tx.v)

The transmitter (uart_tx.v) accepts data over AXI4-Stream and serializes it onto the txd line.

 Original Bug

In the transmit logic, when new data was accepted (s_axis_tvalid high), the following code was present:

s_axis_tready_reg <= !s_axis_tready_reg;


This caused s_axis_tready to toggle instead of being cleared.
Result:

Handshake instability with AXI4-Stream

Data loss or duplication in certain timing conditions

 Fix

The line was corrected to explicitly clear tready:

s_axis_tready_reg <= 0;
