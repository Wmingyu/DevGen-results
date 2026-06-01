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

| ID   | Location                                         | Title                                                        | Status              | Details                                                      | Notes |
| :--- | :----------------------------------------------- | :----------------------------------------------------------- | :------------------ | :----------------------------------------------------------- | :---- |
| #001 | `drivers/char/agp/amd64-agp.c`                   | NULL ptr deref in amd64_fetch_size()                         | 👀**Confirmed**      | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Divide%20by%20zero%20in%20hamachi_init_one.md)</u> |       |
| #002 | `drivers/net/ethernet/packetengines/hamachi.c`   | net: packetengines: remove obsolete hamachi driver           | ✅ **Merged**        | <u>[📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=4cf42f9c3e3624fedf4f6c38c3d81d80c8b3cbd6)</u> |       |
| #003 | `drivers/net/ethernet/packetengines/yellowfin.c` | net: packetengines: remove obsolete yellowfin driver and vendor dir | ✅ **Merged**        | <u>[📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=aec3202247b4ab41c5bf3b9f704a2d9a323a051b)</u> |       |
| #004 | `net/ipv6/udp.c`                                 | Memory leak in udpv6_sendmsg()                               | 🔄 **Already Fixed** | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
| #005 |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
| #006 |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
| #007 |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
| #008 |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
| #009 |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
|      |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |
|      |                                                  |                                                              |                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |       |

> **Note:** Clicking **"📂 Link"** in the `Details` column will navigate to a dedicated page for each bug. These individual pages centralize the complete timeline, discussion history, patch submissions, and all relevant mailing list links (lore.kernel.org) for that specific vulnerability.
