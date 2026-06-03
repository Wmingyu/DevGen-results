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

| ID   | Location                                            | Title                                                        | Status                             | Details                                                      | Notes                          |
| :--- | :-------------------------------------------------- | :----------------------------------------------------------- | :--------------------------------- | :----------------------------------------------------------- | :----------------------------- |
| #001 | `drivers/net/ethernet/packetengines/hamachi.c`      | Divide by zero in hamachi_init_one                           | 👀**Confirmed**                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Divide%20by%20zero%20in%20hamachi_init_one.md)</u> |                                |
| #002 | `drivers/net/ethernet/packetengines/hamachi.c`      | net: packetengines: remove obsolete hamachi driver           | ✅ **Merged**                       | <u>[📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=4cf42f9c3e3624fedf4f6c38c3d81d80c8b3cbd6)</u> |                                |
| #003 | `drivers/net/ethernet/packetengines/yellowfin.c`    | net: packetengines: remove obsolete yellowfin driver and vendor dir | ✅ **Merged**                       | <u>[📂 Link](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=aec3202247b4ab41c5bf3b9f704a2d9a323a051b)</u> |                                |
| #004 | `net/ipv6/udp.c`                                    | Memory leak in udpv6_sendmsg()                               | 🔄 **Already Fixed**                | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md)</u> |                                |
| #005 | `drivers/gpu/drm/drm_gem.c`                         | Unvalidated negative handle in drm_gem_change_handle_ioctl   | 🆕 **Reported** 🛠️ **Patch Sent**    | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Unvalidated%20negative%20handle%20in%20drm_gem_change_handle_ioctl.md)</u> |                                |
| #006 | `fs/hugetlbfs/inode.c` & `mm/vma.c`                 | resv_map memory leak in __mmap_region()                      | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/resv_map%20memory%20leak%20in%20__mmap_region().md)</u> |                                |
| #007 | `drivers/i2c/i2c-dev.c`                             | Integer overflow in I2C_TIMEOUT ioctl                        | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Integer%20overflow%20in%20I2C_TIMEOUT%20ioctl.md)</u> | **Backported to v5.15 - v7.0** |
| #008 | `drivers/char/agp/amd64-agp.c`                      | NULL ptr deref in amd64_fetch_size()                         | 👀**Confirmed** 💬 **Needs Reply**   | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/NULL%20ptr%20deref%20in%20amd64_fetch_size().md)</u> |                                |
| #009 | `arch/x86/kernel/smpboot.c`                         | WARN_ON in set_cpu_sibling_map via numa=fake                 | 👀 **Confirmed**                    | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/WARN_ON%20in%20set_cpu_sibling_map%20via%20numa%3Dfake.md)</u> |                                |
| #010 | `drivers/crypto/intel/qat/qat_common/adf_dev_mgr.c` | Use-After-Free in adf_devmgr_get_dev_by_id()                 | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Use-After-Free%20in%20adf_devmgr_get_dev_by_id().md)</u> |                                |
| #011 | `drivers/crypto/intel/qat/qat_common/adf_ctl_drv.c` | Local DoS via printk storm in QAT ioctls                     | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Local%20DoS%20via%20printk%20storm%20in%20QAT%20ioctls.md)</u> |                                |
| #012 | `drivers/i2c/busses/i2c-i801.c`                     | Hardware state machine corruption in i801_access()           | 👀**Confirmed** 💬 **Needs Reply**   | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hardware%20state%20machine%20corruption%20in%20i801_access().md)</u> |                                |
| #013 | `drivers/watchdog/wdt_pci.c`                        | Shared IRQ storm in wdtpci_interrupt()                       | 👀 **Confirmed** ❌ **WontFix**      | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Shared%20IRQ%20storm%20in%20wdtpci_interrupt().md)</u> |                                |
| #014 | `drivers/gpu/drm/ast/ast_2500.c`                    | Soft lockup in ast_2500_patch_ahb()                          | 👀 **Confirmed** 🛠️ **Patch Sent**   | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Soft%20lockup%20in%20ast_2500_patch_ahb().md)</u> |                                |
| #015 | `drivers/bluetooth/hci_ldisc.c`                     | UAFs and race conditions in hci_uart lifecycle               | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/UAFs%20and%20race%20conditions%20in%20hci_uart%20lifecycle.md)</u> | **Backported to v5.10 - v7.0** |
| #016 | `drivers/gpu/drm/vkms/vkms_crtc.c`                  | ABBA deadlock in vkms vblank timer                           | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/ABBA%20deadlock%20in%20vkms%20vblank%20timer.md)</u> |                                |
| #017 | `drivers/gpu/drm/vmwgfx/vmwgfx_vkms.c`              | Hrtimer interrupt storm in vmw_vkms_enable_vblank()          | 👀**Confirmed** 🛠️ **Patch Sent**    | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hrtimer%20interrupt%20storm%20in%20vmw_vkms_enable_vblank().md)</u> |                                |
| #018 | `fs/fcntl.c`                                        | SOFTIRQ-unsafe lock order deadlock in fasync signaling       | ✅ **Merged**                       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/SOFTIRQ-unsafe%20lock%20order%20deadlock%20in%20fasync%20signaling.md)</u> |                                |
| #019 | `drivers/video/fbdev/core/fbcon.c`                  | Memory leak in fbcon_do_set_font()                           | 🆕 **Reported**                     | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20fbcon_do_set_font().md)</u> |                                |
| #020 | `drivers/gpu/drm/vkms/vkms_crtc.c`                  | Hrtimer livelock via unvalidated display mode                | 🆕 **Reported** 🔄 **Already Fixed** | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hrtimer%20livelock%20via%20unvalidated%20display%20mode.md)</u> |                                |
| #021 | `drivers/gpu/drm/drm_prime.c`                       | rb_tree corruption in drm_prime_remove_buf_handle()          | 👀**Confirmed** ❌ **WontFix**       | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/rb_tree%20corruption%20in%20drm_prime_remove_buf_handle().md)</u> | **On Hold**                    |
| #022 |                                                     |                                                              |                                    | <u>[📂 Link](https://github.com/Wmingyu/DevGen-results/blob/main/details/Local%20DoS%20via%20printk%20storm%20in%20QAT%20ioctls.md)</u> |                                |

> **Note:** Clicking **"📂 Link"** in the `Details` column will navigate to a dedicated page for each bug. These individual pages centralize the complete timeline, discussion history, patch submissions, and all relevant mailing list links (lore.kernel.org) for that specific vulnerability.

