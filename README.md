# NNPI‑Host Project (Community Fork)

**Overview**  
This repository provides the host-side user-mode library and test applications for Intel® Nervana™ Neural Network Processor for Inference (NNP‑I, Spring Hill). The library exposes a low-level API for managing NNPI device resources, such as host memory allocation for DMA and scheduling inference commands. It also includes a test application, **dummy_inference**, that simulates an entire inference workflow (resource allocation, command scheduling, and DMA transfers) without performing real neural network computations.

**Features**
- Low-level API for interfacing with the NNPI device.
- Management of host memory resources for DMA.
- Command channel interface for scheduling and processing inference operations.
- A test harness (**dummy_inference**) to validate the full inference flow.
- Open source and community maintained, Intel discontinued official support.

**Runtime Dependencies (Ubuntu 24.04.2)**
- libc++-dev
- build-essential
- libtool
- autoconf

**Building**

1. **Prepare the Build System**  
   Run autoreconf to generate the build system:
   ```bash
   autoreconf -i
   ```

2. **Configure**  
   Configure the project:
   ```bash
   ./configure
   ```

3. **Compile**  
   Build the project:
   ```bash
   make
   ```

4. **Install (Optional)**  
   Install the library and test application (requires sudo):
   ```bash
   sudo make install
   ```
   The user-mode library will be installed as `/usr/local/lib/libnnpi_drv.so.0` and the dummy_inference test program as `/usr/local/bin/dummy_inference`.

**Testing**

- **dummy_inference**  
  This test program simulates a full inference application workflow. It allocates resources, schedules inference commands, and performs DMA transfers between the host and the NNPI device (using the device’s ULT feature to simulate inference without actual neural network computation).  
  Run:
  ```bash
  dummy_inference -h
  ```
  to view usage instructions and options.

**Community-Driven Development**  
Intel has discontinued development and maintenance of the original NNPI‑Host project. This repository is now maintained by the community. Contributions, bug fixes, and feature enhancements are welcome, please feel free to fork and submit pull requests.

**License**  
This project is released under the GNU General Public License (GPL). See [LICENSE.txt](LICENSE.txt) for details.

**Acknowledgements**  
- **Intel® Nervana™ NNPI‑I:** The original hardware and host software were developed by Intel.  
- **Linux Kernel Mailing List:** Initial design and driver details were discussed on LKML.  
- **The Community:** Thanks to all contributors and users who keep this project alive.
