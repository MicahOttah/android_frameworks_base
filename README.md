# android_frameworks_base

Fork of `LineageOS/android_frameworks_base` for the **LG G Pad X 8.0 (V521)**
LineageOS 15.1 port.  The port builds from `lineage-15.1-v521`; the other
branches are upstream.

Changes:

* Two `@hide` telephony APIs from Android 7.0
  (`PhoneStateListener(int, Looper)`, `SubscriptionManager.getSlotId(int)`)
  are back as shims, so the stock Qualcomm CNE blobs can link.

Port and device tree: <https://github.com/MicahOttah/android_device_lge_v521>
