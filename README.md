# 🐛 My Kernel Bug Tracker

Welcome to my Kernel Bug Tracker repository! This repository serves as an open record of the kernel vulnerabilities I have discovered, analyzed, and reported to the upstream communities (e.g., Linux Kernel). It also tracks the current patch status for each vulnerability.

This repository provides supplementary data and artifacts for the academic paper: **[DevGen]**.

## 📊 Status Legend

To facilitate quick scanning, I use the following emojis to indicate the current status of each reported bug:

* 🆕 **Reported**: The initial bug report has been sent to the mailing list, waiting for the maintainers' first response.
* 👀 **Confirmed**: Developers have acknowledged the bug or are actively debugging it.
* 💬 **Needs Reply**: Maintainers have asked questions, or there is an ongoing discussion requiring my follow-up.
* 🛠️ **Patch Sent**: A fix patch has been submitted (by me or others) and is pending review.
* ✅ **Merged**: The fix patch has been officially accepted and merged into the mainline or a subsystem tree.
* ❌ **WontFix**: The bug cannot be fixed (e.g., due to design choices or hardware limitations).
* 🔄 **Already Fixed**: The bug has already been reported and patched on the master branch.

## 📜 Bug List

| ID   | Location                                         | Title                                                        | Status               | Details                                                      | Notes                        |
| :--- | :----------------------------------------------- | :----------------------------------------------------------- | :------------------- | :----------------------------------------------------------- | :--------------------------- |
| #001 | `drivers/char/agp/amd64-agp.c`                   | NULL ptr deref in amd64_fetch_size()                         | 👀**Confirmed**       | [📂 Link](./bugs/001-amd64-agp-null/)                         |                              |
| #002 | `drivers/net/ethernet/packetengines/hamachi.c`   | net: packetengines: remove obsolete hamachi driver           | ✅ **Merged**         | [📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=4cf42f9c3e3624fedf4f6c38c3d81d80c8b3cbd6) |                              |
| #003 | `drivers/net/ethernet/packetengines/yellowfin.c` | net: packetengines: remove obsolete yellowfin driver and vendor dir | ✅ **Merged**         | [📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=aec3202247b4ab41c5bf3b9f704a2d9a323a051b) |                              |
| #004 |                                                  |                                                              | 👀&nbsp;**Confirmed** | [📂 Link](./bugs/004-usb-race/)                               |                              |
| #005 |                                                  |                                                              | 🆕&nbsp;**Reported**  | 📂 Link                                                       | Found via automated modeling |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |
|      |                                                  |                                                              |                      | 📂 Link                                                       |                              |

> **Note:** Clicking **"📂 Link"** in the `Details` column will navigate to a dedicated page for each bug. These individual pages centralize the complete timeline, discussion history, patch submissions, and all relevant mailing list links (lore.kernel.org) for that specific vulnerability.

