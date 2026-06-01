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
* ❌ **WontFix/Dup**: The behavior is considered expected by design, or the bug is a known/duplicate issue.

## 📜 Bug List

| ID | Subsystem | Bug Title | Status | Mailing List Threads | Details |
| :--- | :--- | :--- | :--- | :--- | :--- |
| #001 | `net/ipv4` | [NULL pointer dereference in tcp_v4_rcv](#) | ✅ **Merged** | [📄 Report](https://lore.kernel.org/) · [🛠️ Patch v2](https://lore.kernel.org/) · [🔗 Commit](https://git.kernel.org/) | [📂 Details](./bugs/001-tcp-null-deref/) |
| #002 | `mm/slub` | [Use-After-Free in kmem_cache_alloc](#) | 💬 **Needs Reply** | [📄 Report](https://lore.kernel.org/) · [💬 Discussion](https://lore.kernel.org/) | [📂 Details](./bugs/002-slub-uaf/) |
| #003 | `fs/ext4` | [Memory leak in ext4_fill_super](#) | 🛠️ **Patch Sent** | [📄 Report](https://lore.kernel.org/) · [🛠️ Patch v1](https://lore.kernel.org/) | [📂 Details](./bugs/003-ext4-leak/) |
| #004 | `drivers/usb` | [Race condition in usb_submit_urb](#) | 👀 **Confirmed** | [📄 Report](https://lore.kernel.org/) · [👀 Acked](https://lore.kernel.org/) | [📂 Details](./bugs/004-usb-race/) |
| #005 | `bpf` | [Out-of-bounds read in bpf_prog_test](#) | 🆕 **Reported** | [📄 Report](https://lore.kernel.org/) | *Drafting...* |

> **Note:** Clicking the short links under the **"Mailing List Threads"** column will redirect you to the corresponding email archives on `lore.kernel.org`. Clicking **"📂 Details"** will lead you to the reproducer code, full crash logs, and deeper technical analysis.

## 📁 Repository Structure

This repository not only tracks the status but also archives all relevant technical details for reproducibility. The directory structure is organized as follows:

```text
.
├── README.md                 # This overview dashboard
└── bugs/                     # Detailed archives for all bugs
    ├── 001-tcp-null-deref/   # Named by "ID-Short_Description"
    │   ├── README.md         # Crash context, Root Cause Analysis (RCA)
    │   ├── repro.c           # C language reproducer code
    │   ├── crash.log         # Full crash logs (e.g., from KASAN/Syzbot)
    │   └── fix.patch         # The final fix patch file
    └── 002-slub-uaf/
        └── ...
