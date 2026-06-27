# 🐛 Page fault via undersized PCI BAR 0 in ibmasm

## 📌 Overview

* **Location:** `drivers/misc/ibmasm/module.c`
* **Current Status:** 🆕 **Bug Confirmed** 
* **Notes:** The `ibmasm` driver maps PCI BAR 0 without verifying if the resource length is sufficient to cover the statically accessed `INTR_CONTROL_REGISTER` (offset 0x13A4). A malformed or undersized BAR 0 allows the `readl()` operation to cross the page boundary into unmapped memory, triggering a page fault during module probe. Since this occurs while holding the module loading lock, it cascades into a global system soft lockup. Fixed by validating that the BAR size is at least `INTR_CONTROL_REGISTER + 4` before invoking `pci_ioremap_bar()`.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| misc: ibmasm: Fix out-of-bounds MMIO access during module load | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623070909.362260-1-w15303746062@163.com/)</u> |
| Re: [PATCH] misc: ibmasm: Fix out-of-bounds MMIO access during module load | <u>[lore.kernel.org](https://lore.kernel.org/all/2026062354-crawfish-t-shirt-d45d@gregkh/)</u> |
| [PATCH v2] misc: ibmasm: Fix static and dynamic out-of-bounds MMIO accesses | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623114046.368089-1-w15303746062@163.com/)</u> |
| Re: [PATCH v2] misc: ibmasm: Fix static and dynamic out-of-bounds MMIO accesses | <u>[lore.kernel.org](https://lore.kernel.org/all/2026062354-quote-lullaby-85e3@gregkh/)</u> |
| [PATCH v3 0/2] misc: ibmasm: Fix out-of-bounds MMIO accesses | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623124304.371163-1-w15303746062@163.com/)</u> |
| [PATCH v3 1/2] misc: ibmasm: Fix static out-of-bounds MMIO access during probe | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623124304.371163-2-w15303746062@163.com/)</u> |
| [PATCH v3 2/2] misc: ibmasm: Fix dynamic out-of-bounds MMIO access | <u>[lore.kernel.org](https://lore.kernel.org/all/20260623124304.371163-3-w15303746062@163.com/)</u> |
| sashiko: [PATCH v3 0/2] misc: ibmasm: Fix out-of-bounds MMIO accesses | <u>[lore.kernel.org](https://sashiko.dev/#/patchset/20260623124304.371163-1-w15303746062%40163.com)</u> |
| [PATCH v4 0/2] misc: ibmasm: Fix out-of-bounds MMIO accesses | <u>[lore.kernel.org](https://lore.kernel.org/all/20260624032425.384325-1-w15303746062@163.com/)</u> |
| [PATCH v4 1/2] misc: ibmasm: Fix static out-of-bounds MMIO access during probe | <u>[lore.kernel.org](https://lore.kernel.org/all/20260624032425.384325-2-w15303746062@163.com/)</u> |
| [PATCH v4 2/2] misc: ibmasm: Fix dynamic out-of-bounds MMIO access via malicious MFA | <u>[lore.kernel.org](https://lore.kernel.org/all/20260624032425.384325-3-w15303746062@163.com/)</u> |
| Re:[PATCH v4 2/2] misc: ibmasm: Fix dynamic out-of-bounds MMIO access via malicious MFA | <u>[lore.kernel.org](https://lore.kernel.org/all/20246781.61e.19f06b66729.Coremail.w15303746062@163.com/)</u> |

