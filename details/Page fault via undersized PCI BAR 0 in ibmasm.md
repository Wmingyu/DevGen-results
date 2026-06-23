# 🐛 Page fault via undersized PCI BAR 0 in ibmasm

## 📌 Overview
* **Location:** `drivers/misc/ibmasm/module.c`
* **Current Status:** 🆕 **Bug Reported** 🛠️ **Patch Sent**
* **Notes:** The `ibmasm` driver maps PCI BAR 0 without verifying if the resource length is sufficient to cover the statically accessed `INTR_CONTROL_REGISTER` (offset 0x13A4). A malformed or undersized BAR 0 allows the `readl()` operation to cross the page boundary into unmapped memory, triggering a page fault during module probe. Since this occurs while holding the module loading lock, it cascades into a global system soft lockup. Fixed by validating that the BAR size is at least `INTR_CONTROL_REGISTER + 4` before invoking `pci_ioremap_bar()`.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| misc: ibmasm: Fix out-of-bounds MMIO access during module load | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623070909.362260-1-w15303746062@163.com/)</u> |
|                                                              |                                                              |

