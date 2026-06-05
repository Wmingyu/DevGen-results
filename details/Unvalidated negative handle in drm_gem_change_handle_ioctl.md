# 🐛 Unvalidated negative handle in drm_gem_change_handle_ioctl

## 📌 Overview

* **Location:** `drivers/gpu/drm/drm_gem.c`
* **Current Status:** 🆕 **Reported** 🛠️ **Patch Sent**
* **Notes:** A missing check for negative user handles bypasses upper-bound validation, triggering a `WARN_ON_ONCE` inside `idr_alloc()`.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/20260422114247.486581-1-25181214217@stu.xidian.edu.cn/)</u> |
| Ping:[PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/388db131.142.19e95bef999.Coremail.25181214217@stu.xidian.edu.cn/)</u> |

