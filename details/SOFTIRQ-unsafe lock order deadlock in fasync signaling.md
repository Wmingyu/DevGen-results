# 🐛 SOFTIRQ-unsafe lock order deadlock in fasync signaling

## 📌 Overview
* **Location:** `fs/fcntl.c`
* **Current Status:** ✅ **Merged** **(vfs-7.2.misc branch)**
* **Notes:** A SOFTIRQ-safe to SOFTIRQ-unsafe lock order deadlock in `send_sigio()` and `send_sigurg()`. When FASYNC is configured for a process group, taking `read_lock(&tasklist_lock)` in softirq context (e.g., during TCP URG packet reception) can deadlock against process-context writers due to rwlock fairness. Fixed by replacing the `tasklist_lock` with `rcu_read_lock()`, which also mitigates a potential remote DoS vector.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] fs/fcntl: fix SOFTIRQ-unsafe lock order in send_sigio() | <u>[lore.kernel.org](https://lore.kernel.org/all/20260523080255.585201-1-w15303746062@163.com/)</u> |
| Re: [PATCH] fs/fcntl: fix SOFTIRQ-unsafe lock order in send_sigio() | <u>[lore.kernel.org](https://lore.kernel.org/all/d15a25fe784b5d4449c7ce4e56f1428d7ff28885.camel@kernel.org/)</u> |
| [PATCH v2] fs/fcntl: fix SOFTIRQ-unsafe lock order in fasync signaling | <u>[lore.kernel.org](https://lore.kernel.org/all/20260523135210.590928-1-w15303746062@163.com/)</u> |
| Applied to the vfs-7.2.misc branch of the vfs/vfs.git tree   | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/Re%20%5BPATCH%20v2%5D%20fsfcntl%20fix%20SOFTIRQ-unsafe%20lock%20order%20in%20fasync%20signaling.txt)</u> |

