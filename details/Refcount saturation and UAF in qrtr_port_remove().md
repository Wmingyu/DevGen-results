# 🐛 Refcount saturation and UAF in qrtr_port_remove()

## 📌 Overview

* **Location:** `net/qrtr/af_qrtr.c`
* **Current Status:**  ✅ **Patch Accepted**  **Backported to v5.10-v7.0**
* **Notes:** A race condition in `qrtr_port_remove()` occurs because the socket reference count is decremented before the port is removed from the XArray and before the RCU grace period elapses. This allows a concurrent RCU reader to obtain the socket and attempt to increment a zeroed refcount, leading to saturation and a potential Use-After-Free. Fixed by deferring `sock_put()` until after `xa_erase()` and `synchronize_rcu()` complete.

## 🔗 Mailing List Threads & Timeline

This section tracks the complete email correspondence and patch history for this vulnerability.

| Description                                                  | Link                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [PATCH] net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove | <u>[lore.kernel.org](https://lore.kernel.org/all/20260530082243.1123402-1-w15303746062@163.com/)</u> |
| Re: [PATCH] net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/Re%20%5BPATCH%5D%20net%20qrtr%20fix%20refcount%20saturation%20and%20potential%20UAF%20in%20qrtr_port_remove.txt)</u> |
| [PATCH] net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove | <u>[lore.kernel.org](https://sashiko.dev/#/patchset/20260530082243.1123402-1-w15303746062%40163.com)</u> |
| [PATCH v2] net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove | <u>[lore.kernel.org](https://lore.kernel.org/all/20260604064801.1180388-1-w15303746062@163.com/)</u> |
| AI Reviews:sashiko                                           | <u>[lore.kernel.org](https://sashiko.dev/#/patchset/20260604064801.1180388-1-w15303746062%40163.com)</u> |
| Re: [PATCH v2] net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove | <u>[lore.kernel.org](https://lore.kernel.org/all/20260608131549.GI3920875@horms.kernel.org/)</u> |
| applied to netdev/net.git                                    | <u>[lore.kernel.org](https://lore.kernel.org/all/178097040939.1753037.3386694182969051861.git-patchwork-notify@kernel.org/)</u> |
| Patch "net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove" has been added to the 5.10-stable tree | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/Patch%20net%20qrtr%20fix%20refcount%20saturation%20and%20potential%20UAF%20in%20qrtr_port_remove%20has%20been%20added%20to%20the%205.10-stable%20tree.txt)</u> |
| Patch "net: qrtr: fix refcount saturation and potential UAF in qrtr_port_remove" has been added to the 7.0-stable tree | <u>[lore.kernel.org](https://github.com/Wmingyu/DevGen-results/blob/main/email-list/Patch%20net%20qrtr%20fix%20refcount%20saturation%20and%20potential%20UAF%20in%20qrtr_port_remove%20has%20been%20added%20to%20the%207.0-stable%20tree.txt)</u> |

