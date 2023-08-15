# Installation Guide

This guide provides step-by-step instructions for setting up the environment and installing the required dependencies to run the DPDK-Based Network Scanner.

## Prerequisites

Before you begin, ensure that you have the following prerequisites installed:

- Ubuntu 20.04 LTS (or compatible Linux distribution)
- Mellanox SmartNIC with DPDK-supported network card
- DPDK library (v20.11 or later)
- GCC compiler

## Step 1: System Preparation

1. Update the package repositories:

   ```bash
   sudo apt update

2. Install essential packages:
   ```bash
   sudo apt install build-essential
   
3. Install the GCC compiler:
   ```bash
   sudo apt install gcc
   
## Step 2: DPDK Installation

1. Download the latest DPDK version from the official website:
   ```bash
   wget https://fast.dpdk.org/rel/dpdk-21.08.tar.xz
   
2. Extract the DPDK archive:
   ```bash
   tar xf dpdk-21.08.tar.xz
   cd dpdk-21.08
   
3. Set the environment variables:
   ```bash
   export RTE_SDK=$(pwd)
   export RTE_TARGET=x86_64-native-linuxapp-gcc

4. Build DPDK:
   ```bash
   make install T=$RTE_TARGET -j
   
## Step 3: Mellanox Drivers and Firmware
1. Download the Mellanox OFED package:
   ```bash
   wget https://www.mellanox.com/downloads/ofed/MLNX_OFED-5.4-1.0.4.0/MLNX_OFED_LINUX-5.4-1.0.4.0-ubuntu20.04-x86_64.tgz

2. Extract the Mellanox OFED package:

   ```bash
   tar xf MLNX_OFED_LINUX-5.4-1.0.4.0-ubuntu20.04-x86_64.tgz
   cd MLNX_OFED_LINUX-5.4-1.0.4.0-ubuntu20.04-x86_64

3. Install Mellanox OFED:

   ```bash
   sudo ./mlnxofedinstall

## Step 4: Building the Scanner

1. Clone the DPDK-Based Network Scanner repository:

    ```bash
   git clone https://github.com/your-username/dpdk-network-scanner.git
   cd dpdk-network-scanner

2. Build the scanner application:
   ```bash
   make

## Step 5: Configuration

Configure the Smart NIC and DPDK settings in the config.ini file.


## Step 6: Running the Scanner
Run the scanner application:
   ```bash
   sudo ./dpdk-scanner
Congratulations! You have successfully set up and installed the DPDK-Based Network Scanner.

