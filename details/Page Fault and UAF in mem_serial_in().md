# 🐛 Page Fault and UAF in mem_serial_in()

## 📌 Overview

* **Location:** `drivers/tty/serial/8250/8250_port.c`
* **Current Status:** 🆕 **Bug Reported** 🛠️ **Patch Sent**
* **Notes:** Allowing arbitrary iomem_base injection via the TIOCSSERIAL ioctl causes a bogus memory mapping, triggering a fatal Page Fault in mem_serial_in(). This crash orphans the tty_lock, ultimately leading to a slab-use-after-free in mutex_spin_on_owner().

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] serial: 8250: validate iomem_base in serial8250_verify_port() | <u>[lore.kernel.org](https://lore.kernel.org/all/20260720053733.102186-1-25181214217@stu.xidian.edu.cn/)</u> |
| AI-Result                                                    | <u>[lore.kernel.org](https://sashiko.dev/#/patchset/20260720053733.102186-1-25181214217%40stu.xidian.edu.cn)</u> |

