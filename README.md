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

| ID | Location | Title | Status | Details | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| #001 | `drivers/char/agp/amd64-agp.c` | [NULL ptr deref in amd64_fetch_size()](#) | ✅&nbsp;**Merged** | [📂 Link](./bugs/001-amd64-agp-null/) | Backported to v6.1+ |
| #002 | `arch/x86/mm/numa.c` | [WARN_ON in set_cpu_sibling_map()](#) | 💬&nbsp;**Needs&nbsp;Reply** | [📂 Link](./bugs/002-numa-fake-panic/) | |
| #003 | `fs/ext4/super.c` | [Memory leak in ext4_fill_super](#) | 🛠️&nbsp;**Patch&nbsp;Sent** | [📂 Link](./bugs/003-ext4-leak/) | CVE-2026-XXXX |
| #004 | `drivers/usb/core/urb.c` | [Race condition in usb_submit_urb](#) | 👀&nbsp;**Confirmed** | [📂 Link](./bugs/004-usb-race/) | |
| #005 | `kernel/bpf/core.c` | [Out-of-bounds read in bpf_prog_test](#) | 🆕&nbsp;**Reported** | *Drafting...* | Found via automated modeling |

> **Note:** Clicking **"📂 Link"** in the `Details` column will navigate to a dedicated page for each bug. These individual pages centralize the complete timeline, discussion history, patch submissions, and all relevant mailing list links (lore.kernel.org) for that specific vulnerability.


