
## 🧩 Modules Overview

### 1. `fifo_top`
- Integrates all submodules: write/read pointer handlers, memory, and synchronizers.
- Parameters: `DATA_WIDTH`, `DEPTH`, `PTR_WIDTH`.

### 2. `wptr_handler` & `rptr_handler`
- Manages binary and Gray-coded pointers.
- Detects `full` and `empty` conditions using wrap-around logic.

### 3. `fifo_mem`
- Dual-port memory with pipelined read/write operations.
- Handles data storage and retrieval.

### 4. `synchronizer`
- Two-stage synchronizer for safe pointer transfer across clock domains.

## 🧪 Testbench Features

- Clock generation for `wclk` and `rclk` with different periods.
- Reset sequencing and stimulus for write/read operations.
- Monitors `full` and `empty` flags.
- Includes assertions to catch illegal read/write attempts.
- Generates a `.vcd` file for waveform analysis.

## 🚀 Simulation Instructions

1. **Tool Required:** Any Verilog simulator (e.g., ModelSim, Vivado, Icarus Verilog).
2. **Run Simulation:**
   ```bash
   iverilog -o fifo_sim Asynchronous\ FIFO_DUT\ \(1\).txt Asynchronous\ FIFO_TB\ \(1\).txt
   vvp fifo_sim
