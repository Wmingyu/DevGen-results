# 🐛 Unvalidated negative handle in drm_gem_change_handle_ioctl

## 📌 Overview

* **Location:** `drivers/gpu/drm/drm_gem.c`
* **Current Status:**  👀**Confirmed**  🛠️ **Patch Sent**
* **Notes:** A missing check for negative user handles bypasses upper-bound validation, triggering a `WARN_ON_ONCE` inside `idr_alloc()`.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/20260422114247.486581-1-25181214217@stu.xidian.edu.cn/)</u> |
| Ping:[PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/388db131.142.19e95bef999.Coremail.25181214217@stu.xidian.edu.cn/)</u> |
| Re: [PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/bfdf1fbe-d61c-4bf7-b6f0-d5c676224af4@suse.de/)</u> |
| Re: Re: [PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/3f69ad35.77a.19e9801ac64.Coremail.25181214217@stu.xidian.edu.cn/)</u> |
| Re: Re: Re: [PATCH] drm/gem: fix warning in idr_alloc due to unvalidated user handle | <u>[lore.kernel.org](https://lore.kernel.org/all/51f7582e.7b9.19e98233793.Coremail.25181214217@stu.xidian.edu.cn/)</u> |
| [PATCH v2] drm/gem: fix signed integer overflow in idr_alloc end parameter | <u>[lore.kernel.org](https://lore.kernel.org/all/20260605142644.1205922-1-w15303746062@163.com/)</u> |
| sashiko-bot:Re: [PATCH v2] drm/gem: fix signed integer overflow in idr_alloc end parameter | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/Re%20sashiko-bot%20%5BPATCH%20v2%5D%20drmgem%20fix%20signed%20integer%20overflow%20in%20idr_alloc%20end%20parameter.txt)</u> |
| sashiko-bot:Re:Re: [PATCH v2] drm/gem: fix signed integer overflow in idr_alloc end parameter | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/ReRe%20sashiko-bot%20%5BPATCH%20v2%5D%20drmgem%20fix%20signed%20integer%20overflow%20in%20idr_alloc%20end%20parameter.txt)</u> |
|                                                              | <u>[lore.kernel.org]()</u>                                   |
|                                                              | <u>[lore.kernel.org]()</u>                                   |

