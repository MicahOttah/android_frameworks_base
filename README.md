# android_frameworks_base

Fork of `LineageOS/android_frameworks_base` with the changes of the **LG G
Pad X 8.0 (V521)** port to **LineageOS 15.1** (Android 8.1).

| Branch | What it is |
| --- | --- |
| `lineage-15.1` | the upstream LineageOS 15.1 branch, unchanged |
| `lineage-15.1-v521` | the branch the V521 port builds from |

## What is different on `lineage-15.1-v521`

| Commit | Subject |
| --- | --- |
| `11e63f07` | telephony: add 7.0-era compat APIs for the stock CNE blobs |

The connectivity stack of this device is the stock Qualcomm CNE (the
`libcne.so` blob), which is a **7.0-era** implementation that was dropped
from the platform in Android 8.0.  Two of its `@hide` APIs were changed
between 7.0 and 8.1 - `PhoneStateListener(int, Looper)` became
`PhoneStateListener(Integer, Looper)` and
`SubscriptionManager.getSlotId(int)` was renamed to
`SubscriptionManager.getSlotIndex(int)` - and DEX resolves methods by exact
signature, so the blobs cannot link against the 8.1 framework.  The two
APIs are added back as `@hide` shims that forward to the modern
implementations.

## The port

The full description of the port is in the device tree:
<https://github.com/MicahOttah/android_device_lge_v521>
