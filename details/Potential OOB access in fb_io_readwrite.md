# 🐛 Potential OOB access in fb_io_read/write

## 📌 Overview

* **Location:** `drivers/video/fbdev/core/fb_io_fops.c`
* **Current Status:** 🆕 **Bug Reported** 🛠️ **Patch Sent**
* **Notes:** Legacy fbdev drivers incorrectly setting info->screen_size larger than the actual mapped framebuffer size (info->fix.smem_len) during mode switches can allow out-of-bounds memory accesses in fb_io_read() and fb_io_write().

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] fbdev: core: Clamp total_size to smem_len in fb_io_read/write | <u>[lore.kernel.org](https://lore.kernel.org/all/20260720135534.103599-1-25181214217@stu.xidian.edu.cn/)</u> |
| AI-Result                                                    | <u>[lore.kernel.org](https://sashiko.dev/#/patchset/20260720135534.103599-1-25181214217%40stu.xidian.edu.cn)</u> |
| Re: [PATCH] fbdev: core: Clamp total_size to smem_len in fb_io_read/write | <u>[lore.kernel.org](https://lore.kernel.org/all/20260720141559.0912D1F00A3A@smtp.kernel.org/)</u> |

