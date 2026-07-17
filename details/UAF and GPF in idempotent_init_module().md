# 🐛 UAF and GPF in idempotent_init_module()

## 📌 Overview
* **Location:** `kernel/module/main.c`
* **Current Status:** 🆕 **Bug Confirmed** 🛠️ **Patch Sent**
* **Notes:** A stack-allocated node linked to a global list causes a stale pointer dereference if the module-loading task is abruptly terminated. Fixed by using heap allocation to safely decouple the node's lifespan from the process stack.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] module: fix UAF and GPF in idempotent_init_module via heap allocation | <u>[lore.kernel.org](https://lore.kernel.org/all/20260717082601.81704-1-25181214217@stu.xidian.edu.cn/)</u> |
| Re: [PATCH] module: fix UAF and GPF in idempotent_init_module via heap allocation | <u>[lore.kernel.org](https://lore.kernel.org/all/20260717084017.A9CFE1F000E9@smtp.kernel.org/)</u> |
|                                                              | <u>[lore.kernel.org](#)</u>                                  |
|                                                              | <u>[lore.kernel.org](#)</u>                                  |

