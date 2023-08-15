# DPDK-Based Network Scanner

## Overview

Welcome to the DPDK-Based Network Scanner repository! This project aims to enhance network visibility and security using Data Plane Development Kit (DPDK) and Smart Network Interface Cards (Smart NICs). The scanner utilizes advanced techniques, including protocol-specific probes and in-network processing, to improve scanning speed, accuracy, and efficiency.

## Features

- DPDK-based packet processing for improved performance.
- Smart NIC offload engines for efficient packet analysis.
- Protocol-specific probes for enhanced network visibility.
- In-network processing optimization to reduce CPU load and latency.
- Detailed experimental evaluation showcasing performance improvements.

## Getting Started

To set up and run the DPDK-Based Network Scanner, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/dpdk-network-scanner.git
   cd dpdk-network-scanner

Install the required dependencies (DPDK, Mellanox drivers, etc.) as described in the INSTALLATION.md file.

Build the scanner application:

make

Configure the Smart NIC and DPDK settings in the config.ini file.

Run the scanner application:

sudo ./dpdk-scanner
##Code Snippets
Here are some code snippets showcasing the key components of the DPDK-Based Network Scanner:

<details>
<summary>DPDK Initialization</summary>

#include <rte_eal.h>
#include <rte_ethdev.h>

int main(int argc, char *argv[]) {
    rte_eal_init(argc, argv);
    rte_eth_dev_configure(0, nb_rx_queues, nb_tx_queues, &port_conf);
    // ...
    return 0;
}
</details>
<details>
<summary>Smart NIC Configuration</summary>

#include <rte_ethdev.h>
#include <rte_eth_ctrl.h>

void configure_smart_nic(uint16_t port_id) {
    struct rte_eth_dev_info dev_info;
    rte_eth_dev_info_get(port_id, &dev_info);
    rte_eth_dev_configure(port_id, dev_info.nb_rx_queues, dev_info.nb_tx_queues, &port_conf);
    // ...
}
</details>
##Experiment Reproducibility
For a detailed understanding of the implementation and to reproduce the experiment, refer to the full source code in this repository.

##Contributions
Contributions to this project are welcome! Feel free to submit pull requests for bug fixes, enhancements, or new features.

##License
This project is licensed under the MIT License.
