# 🐛 Kernel Bug Tracker

Welcome to my Kernel Bug Tracker repository! This repository serves as an open record of the kernel vulnerabilities discovered, analyzed, and reported to the upstream Linux Kernel community. 

> 📄 **Academic Artifact:** This repository provides supplementary data, complete timelines, and patch histories for the academic paper: **[DevGen]**.

## 📊 Status Legend

| Symbol | Status               | Description                                                  |
| :----: | :------------------- | :----------------------------------------------------------- |
|   🆕    | **Reported**         | Initial bug report sent to the mailing list, awaiting first response. |
|   👀    | **Confirmed**        | Developers have acknowledged the bug or are actively debugging it. |
|   💬    | **Needs Reply**      | Ongoing discussion requiring follow-up or maintainers have asked questions. |
|   🛠️    | **Patch Sent**       | A fix patch has been submitted and is pending review.        |
|   ✅    | **Accepted**         | The fix patch has received maintainer approval (e.g., `Reviewed-by`) and is either merged or queued for merging. |
|   ❌    | **WontFix**          | The bug cannot be fixed (e.g., due to design choices or hardware limits). |
|   🔄    | **Indirectly Fixed** | The bug was indirectly resolved by upstream code refactoring or patches for other issues. |

---

## 📜 Vulnerability List

*Click on any vulnerability title to view the dedicated page with patch history and mailing list threads (lore.kernel.org).*

| ID   | Location                                         | Vulnerability & Details                                      | Status & Notes                                         |
| :--- | :----------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------- |
| #001 | `net/ethernet/packetengines/hamachi.c`           | [Divide by zero in hamachi_init_one](https://github.com/Wmingyu/DevGen-results/blob/main/details/Divide%20by%20zero%20in%20hamachi_init_one.md) | 👀 **Confirmed**                                        |
| #002 | `net/ethernet/packetengines/hamachi.c`           | [net: packetengines: remove obsolete hamachi driver](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=4cf42f9c3e3624fedf4f6c38c3d81d80c8b3cbd6) | ✅ **Accepted**                                         |
| #003 | `net/ethernet/packetengines/yellowfin.c`         | [net: packetengines: remove obsolete yellowfin driver](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=aec3202247b4ab41c5bf3b9f704a2d9a323a051b) | ✅ **Accepted**                                         |
| #004 | `net/ipv6/udp.c`                                 | [Memory leak in udpv6_sendmsg()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20udpv6_sendmsg().md) | 👀**Confirmed**<br/>🔄 **Indirectly Fixed**              |
| #005 | `gpu/drm/drm_gem.c`                              | [Unvalidated negative handle in drm_gem_change_handle_ioctl](https://github.com/Wmingyu/DevGen-results/blob/main/details/Unvalidated%20negative%20handle%20in%20drm_gem_change_handle_ioctl.md) | 👀**Confirmed**<br>🛠️ **Patch Sent**                     |
| #006 | `fs/hugetlbfs/inode.c`<br>`mm/vma.c`             | [resv_map memory leak in __mmap_region()](https://github.com/Wmingyu/DevGen-results/blob/main/details/resv_map%20memory%20leak%20in%20__mmap_region().md) | ✅ **Accepted**                                         |
| #007 | `i2c/i2c-dev.c`                                  | [Integer overflow in I2C_TIMEOUT ioctl](https://github.com/Wmingyu/DevGen-results/blob/main/details/Integer%20overflow%20in%20I2C_TIMEOUT%20ioctl.md) | ✅ **Accepted**<br><sub>Backported to v5.15-v7.0</sub>  |
| #008 | `char/agp/amd64-agp.c`                           | [NULL ptr deref in amd64_fetch_size()](https://github.com/Wmingyu/DevGen-results/blob/main/details/NULL%20ptr%20deref%20in%20amd64_fetch_size().md) | ✅ **Accepted**                                         |
| #009 | `x86/kernel/smpboot.c`                           | [WARN_ON in set_cpu_sibling_map via numa=fake](https://github.com/Wmingyu/DevGen-results/blob/main/details/WARN_ON%20in%20set_cpu_sibling_map%20via%20numa%3Dfake.md) | 👀 **Confirmed**                                        |
| #010 | `crypto/intel/qat/qat_common/adf_dev_mgr.c`      | [Use-After-Free in adf_devmgr_get_dev_by_id()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Use-After-Free%20in%20adf_devmgr_get_dev_by_id().md) | ✅ **Accepted**                                         |
| #011 | `crypto/intel/qat/qat_common/adf_ctl_drv.c`      | [Local DoS via printk storm in QAT ioctls](https://github.com/Wmingyu/DevGen-results/blob/main/details/Local%20DoS%20via%20printk%20storm%20in%20QAT%20ioctls.md) | ✅ **Accepted**                                         |
| #012 | `i2c/busses/i2c-i801.c`                          | [Hardware state machine corruption in i801_access()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hardware%20state%20machine%20corruption%20in%20i801_access().md) | 👀 **Confirmed**<br>🛠️**Patch Sent**                     |
| #013 | `watchdog/wdt_pci.c`                             | [Shared IRQ storm in wdtpci_interrupt()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Shared%20IRQ%20storm%20in%20wdtpci_interrupt().md) | 👀 **Confirmed**<br>❌ **WontFix**                       |
| #014 | `gpu/drm/ast/ast_2500.c`                         | [Soft lockup in ast_2500_patch_ahb()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Soft%20lockup%20in%20ast_2500_patch_ahb().md) | 👀 **Confirmed**<br>🛠️ **Patch Sent**                    |
| #015 | `bluetooth/hci_ldisc.c`                          | [UAFs and race conditions in hci_uart lifecycle](https://github.com/Wmingyu/DevGen-results/blob/main/details/UAFs%20and%20race%20conditions%20in%20hci_uart%20lifecycle.md) | ✅ **Accepted**<br><sub>Backported to v5.10-v7.0</sub>  |
| #016 | `gpu/drm/vkms/vkms_crtc.c`                       | [ABBA deadlock in vkms vblank timer](https://github.com/Wmingyu/DevGen-results/blob/main/details/ABBA%20deadlock%20in%20vkms%20vblank%20timer.md) | ✅ **Accepted**                                         |
| #017 | `gpu/drm/vmwgfx/vmwgfx_vkms.c`                   | [Hrtimer interrupt storm in vmw_vkms_enable_vblank()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hrtimer%20interrupt%20storm%20in%20vmw_vkms_enable_vblank().md) | 👀 **Confirmed**<br>🛠️ **Patch Sent**                    |
| #018 | `fs/fcntl.c`                                     | [SOFTIRQ-unsafe lock order deadlock in fasync signaling](https://github.com/Wmingyu/DevGen-results/blob/main/details/SOFTIRQ-unsafe%20lock%20order%20deadlock%20in%20fasync%20signaling.md) | ✅ **Accepted**                                         |
| #019 | `video/fbdev/core/fbcon.c`                       | [Memory leak in fbcon_do_set_font()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Memory%20leak%20in%20fbcon_do_set_font().md) | 🆕 **Reported**<br>🛠️ **Patch Sent**                     |
| #020 | `gpu/drm/vkms/vkms_crtc.c`                       | [Hrtimer livelock via unvalidated display mode](https://github.com/Wmingyu/DevGen-results/blob/main/details/Hrtimer%20livelock%20via%20unvalidated%20display%20mode.md) | 🔄 **Indirectly Fixed**                                 |
| #021 | `gpu/drm/drm_prime.c`                            | [rb_tree corruption in drm_prime_remove_buf_handle()](https://github.com/Wmingyu/DevGen-results/blob/main/details/rb_tree%20corruption%20in%20drm_prime_remove_buf_handle().md) | 👀 **Confirmed**<br>❌ **WontFix**<br><sub>On Hold</sub> |
| #022 | `net/qrtr/af_qrtr.c`                             | [Refcount saturation and UAF in qrtr_port_remove()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Refcount%20saturation%20and%20UAF%20in%20qrtr_port_remove().md) | 👀**Confirmed**<br>🛠️ **Patch Sent**                     |
| #023 | `drivers/gpu/drm/drm_gem.c`                      | [Refcount saturation and UAF in qrtr_port_remove()](https://github.com/Wmingyu/DevGen-results/blob/main/details/WARNING%20in%20idr_alloc%20via%20drm_gem_change_handle_ioctl.md) | 👀 **Confirmed**                                        |
| #024 | `drivers/crypto/intel/qat/qat_common/adf_init.c` | [Use-After-Free in adf_dev_up()](https://github.com/Wmingyu/DevGen-results/blob/main/details/Use-After-Free%20in%20adf_dev_up().md) | 👀 **Confirmed**                                        |
| #025 |                                                  |                                                              |                                                        |
| #026 |                                                  |                                                              |                                                        |



