# 🎓 1-Year Mastery Syllabus for Cortex-A (BeagleBone Black Edition)

This comprehensive 12-month syllabus guides you through mastering ARM Cortex-A systems using **BeagleBone Black** — tailored for embedded Linux, bare-metal programming, and real-world BSP/kernel development roles.

---

## 📦 MODULE 1 (Month 1–2): ARM Architecture & Bare-Metal Boot

### Month 1: ARMv7-A Architecture & SoC Internals

#### Week 1:

* Learn Cortex-A (ARMv7-A) pipeline and privilege levels (USR/SVC/IRQ/FIQ/SYS)
* Understand MMU, page tables, TLBs, and virtual memory basics
* Read key parts of the ARM ARM (v7-A/R)

#### Week 2:

* Study AM335x TRM (SoC on BBB): MMIO, memory map, clock system
* Explore exception levels and interrupt vector table layout
* Learn to write and link ARM assembly + C startup files

#### Week 3:

* Set up toolchain: `arm-none-eabi-gcc`, GDB, OpenOCD
* Practice building and running small ARM assembly snippets on QEMU/BBB

#### Week 4:

* Study U-Boot boot flow: SPL → U-Boot proper
* Learn boot media options (eMMC, SD, UART boot)

### Month 2: Bare-Metal Projects (No OS)

#### Week 5:

* Write MMIO LED blinker at EL3 (or Supervisor Mode)
* Use linker script to place memory regions manually

#### Week 6:

* Implement UART driver (polling)
* Set up printf-style debugging over UART

#### Week 7:

* Add interrupt vector table
* Implement IRQ and FIQ handlers with GIC support

#### Week 8:

* Enable MMU: write basic identity page tables
* Use virtual memory translation for code and stack

---

## ⚙️ MODULE 2 (Month 3–4): U-Boot, TF-A, and Bootloaders

### Month 3: Dive into U-Boot

#### Week 9:

* Compile and boot BeagleBone Black’s U-Boot from source
* Enable serial output, edit environment variables

#### Week 10:

* Modify U-Boot: Change banner text, add new CLI command
* Add a GPIO-based LED test in U-Boot CLI

#### Week 11:

* Explore Flattened Device Tree (FDT) structure
* Understand how U-Boot passes DTB to Linux

#### Week 12:

* Rebuild and test U-Boot with custom DT
* Use U-Boot scripts to automate booting and kernel testing

### Month 4: Trusted Firmware-A (optional) + TF-A Concepts

#### Week 13:

* Learn Secure/Non-secure world (TrustZone overview)
* Study ARM Trusted Firmware (TF-A) layers: BL1, BL2, BL31

#### Week 14:

* Build TF-A for ARMv8-A in QEMU or other board for simulation
* Learn how EL3 code initializes Secure Monitor

#### Week 15:

* Integrate TF-A with U-Boot for systems needing EL3 initialization

#### Week 16:

* Bonus: Modify TF-A to add UART debug log or boot profiling

---

## 🐧 MODULE 3 (Month 5–6): Embedded Linux Kernel + Device Drivers

### Month 5: Kernel Internals

#### Week 17:

* Compile mainline Linux for BeagleBone Black (armv7)
* Configure using `make menuconfig`, build zImage and DTB

#### Week 18:

* Learn Linux boot process (zImage + DTB → init → rootfs)
* Use BusyBox init or systemd minimal setup

#### Week 19:

* Explore `/proc`, `/sys`, `/dev`, `udev` internals
* Test GPIO access via sysfs and new libgpiod interface

#### Week 20:

* Create your own `platform_driver` for LED or button
* Handle `probe()`, `remove()`, `of_match_table`

### Month 6: Writing Real Drivers

#### Week 21:

* Write a **character device driver**
* Implement open, read, write, ioctl

#### Week 22:

* Write an I2C device driver for an external sensor (e.g. BME280)
* Use DT overlay to describe sensor node

#### Week 23:

* Add interrupt handling to character driver
* Use `request_irq()` and work queues

#### Week 24:

* Create a user-space app to interact with your driver
* Package as systemd service to run on boot

---

## 🧰 MODULE 4 (Month 7–8): Yocto & Linux RootFS Customization

### Month 7: Deep Dive into Yocto

#### Week 25:

* Set up Yocto project with BeagleBone Black BSP layer (meta-ti)
* Build core-image-minimal for BBB

#### Week 26:

* Create custom layer: `meta-yourname`
* Add packages (htop, nano, ssh, your driver)

#### Week 27:

* Modify init system (SysVinit or systemd)
* Add systemd service to auto-launch your app

#### Week 28:

* Build and use `populate_sdk` to generate SDK for app dev
* Install SDK on host and build a CLI app for BBB

### Month 8: Advanced Yocto

#### Week 29:

* Learn OTA strategies (A/B partitions, RAUC)
* Setup basic OTA testbed using SD card partitions

#### Week 30:

* Build multi-image setup: base + recovery rootfs
* Add checksum verification before applying OTA

#### Week 31:

* Add Wi-Fi (USB dongle or cape) and test wpa\_supplicant integration
* Add dropbear or OpenSSH for remote debugging

#### Week 32:

* Package entire Yocto distro + app for SD card or eMMC flashing

---

## 🔬 MODULE 5 (Month 9–10): Optimization, Real-Time, Power Management

### Month 9: Real-Time Linux & Profiling

#### Week 33:

* Patch Linux with PREEMPT\_RT
* Build real-time kernel for BeagleBone

#### Week 34:

* Measure latency using cyclictest
* Compare PREEMPT vs PREEMPT\_RT behavior

#### Week 35:

* Profile your driver using `ftrace`, `perf`, and tracepoints

#### Week 36:

* Use kernel probes (kprobes) to hook into kernel routines

### Month 10: Power Management + Optimization

#### Week 37:

* Study power domains, DVFS, CPU frequency scaling

#### Week 38:

* Enable suspend-to-RAM or suspend-to-disk

#### Week 39:

* Use device tree and kernel config to manage unused peripherals

#### Week 40:

* Benchmark boot time and optimize U-Boot + Kernel timings

---

## 🔐 MODULE 6 (Month 11–12): Secure Boot, OP-TEE, and Final Projects

### Month 11: Security + Trusted Execution

#### Week 41:

* Study Secure Boot principles: hash chain, signature

#### Week 42:

* Learn how U-Boot secure boot works (e.g., FIT images + RSA signature)

#### Week 43:

* Explore OP-TEE + TF-A integration (QEMU or real board w/ secure world)

#### Week 44:

* Bonus: Add a secure boot path and measure boot integrity

### Month 12: Capstone Projects

#### Week 45:

* Choose one:

  * Custom BeagleBone image (Yocto + Kernel + App)
  * Write a full-featured device driver
  * OTA + Secure Boot demo system

#### Week 46:

* Document project, create system diagram, write README

#### Week 47:

* Package into GitHub repo + create flashing instructions

#### Week 48:

* Final polish, optional blog/video demo, portfolio ready!

---

## 🧠 Extra Topics (Optional/Advanced)

* Hypervisors (Xen on ARM, KVM)
* Kernel module signing
* eBPF intro for tracing/security
* OpenAMP for AMP (e.g., M4 + A8 multicore SoC)

---

## ✅ Tools to Master

| Tool                 | Purpose                              |
| -------------------- | ------------------------------------ |
| OpenOCD + GDB        | Bare-metal debugging                 |
| Device Tree Compiler | Validate and compile DTS/DTB         |
| perf, ftrace         | Kernel profiling                     |
| Yocto                | Image generation and BSPs            |
| Git + Buildroot      | Compare with Yocto, fast prototyping |

---

## 📚 Recommended Resources

* [Bootlin Training Series](https://bootlin.com/doc/training/)
* [TI AM335x TRM Manual](https://www.ti.com/lit/pdf/spruh73)
* [Linux Kernel Newbies](https://kernelnewbies.org/)
* [Elixir Cross Referencer](https://elixir.bootlin.com/linux/latest/source)
* [OP-TEE Docs](https://optee.readthedocs.io/en/latest/)
* [Yocto Project Mega Manual](https://docs.yoctoproject.org/)

