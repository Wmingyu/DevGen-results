# 🐛 Memory leak in vc_allocate() on screen buffer allocation failure

## 📌 Overview

* **Location:** `drivers/tty/vt/vt.c`
* **Current Status:** 🆕 **Bug Reported**  🛠️ **Patch Sent**
* **Notes:** When screen buffer allocation fails in vc_allocate(), the error path frees the virtual console structure without releasing its associated unicode screen map. This leaves the unicode dictionary with an elevated reference count and leaks memory when the console is subsequently deallocated

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                           | Link                                                         |
| :---------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] tty: vt: fix memory leak in vc_allocate()     | <u>[lore.kernel.org](https://lore.kernel.org/all/20260723070530.117552-1-25181214217@stu.xidian.edu.cn/)</u> |
| Re: [PATCH] tty: vt: fix memory leak in vc_allocate() | <u>[lore.kernel.org](https://lore.kernel.org/all/2026072345-copartner-shrink-9596@gregkh/)</u> |
| Re: [PATCH] tty: vt: fix memory leak in vc_allocate() | <u>[lore.kernel.org](https://lore.kernel.org/all/88f9ac58-8079-415d-902c-3b9455a9d17c@stu.xidian.edu.cn/#t)</u> |

