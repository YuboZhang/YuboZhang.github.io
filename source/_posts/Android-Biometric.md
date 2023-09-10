---
title: Android Biometric
date: 2022-08-07 20:31:30
updated: 2023-09-10 22:33:01
categories:
	- [Android]
tags:
	- Biometric
	- Authentication
---


## Android Biometric Cryptography

### Authentication

Android生物识别身份[认证](https://source.android.com/security/authentication?hl=zh-cn)流程
![身份验证流程](/images/authentication-flow.png "身份验证流程")

Data Flow For Fingerprint Authentication
![Data Flow For Fingerprint Authentication](/images/DataFlowForFingerprintAuthentication.png "Data Flow For Fingerprint Authentication")

### Keymaster
Keymaster implements the Android key store in TEE to guard cryptographic key storage and use in the case of a run-time kernel compromise [Keystore](https://source.android.com/docs/security/keystore?hl=zh-cn). That is, even with a fully compromised kernel, an attacker cannot read key material stored in Keymaster16. Apps can explicitly request keys to be stored in Keymaster, i.e. to be hardware-bound, to be only accessible after user authentication (which is tied to Gatekeeper/Weaver), and/or request attestation certificates to verify these key properties [android.security.keystore.KeyGenParameterSpec](https://developer.android.com/reference/android/security/keystore/KeyGenParameterSpec), allowing verification of compatibility in terms of rule ○3 (compatibility).
![访问 Keymaster](/images/access-to-keymaster.png)

### StrongBox
Strongbox, specified starting with Android 9.0, implements the Android [keystore](https://developer.android.com/training/articles/keystore.html?hl=zh-cn) in separate tamper resistant hardware (TRH) for even better isolation. This mitigates [T.P2] and [T.P3] against strong adversaries, e.g. against cold boot memory  attacks [83] or hardware bugs such as Spectre/Meltdown [95, 104], Rowhammer [57, 136], or Clkscrew [129] that allow  privilege escalation even from kernel to TEE. From a hardware perspective, the main application processor (AP) will always have a significantly larger attack surface than dedicated secure co-processor. Adding a separate TRH affords another  sandboxing layer of defense in depth. The Google Pixel 3 was the first device to support Strongbox with a dedicated TRH (Titan M [146]), and other OEM devices have since started to implement it (often using standard secure elements that have been available on Android devices for NFC payment and other use cases). (All the citations are from the article [The Android Platform Security Model](https://arxiv.org/pdf/1904.05572.pdf))
> **_NOTE:_**
Note that only storing and using keys in TEE or TRH does not completely solve the problem of making them unusable under the assumption of a kernel compromise: if an attacker gains access to the low-level interfaces for communicating directly with Keymaster or Strongbox, they can use it as an oracle for cryptographic operations that require the private key. This is the reason why keys can be authentication bound and/or require user presence verification, e.g. by pushing a hardware button that is detectable by the TRH to assure that keys are not used in the background without user consent.

### Gatekeeper
[Gatekeeper](https://source.android.com/security/authentication/gatekeeper?hl=zh-cn) implements verification of user lock screen factors (PIN/password/pattern) in TEE and, upon successful authentication, communicates this to Keymaster for releasing access to authentication bound keys. **Weaver** implements the same functionality in TRH and communicates with Strongbox.

More info:

- [在Android中使用生物识别](https://segmentfault.com/a/1190000040140033)

- [实战 | 将 Android 生物识别身份验证整合至应用中](https://segmentfault.com/a/1190000040175152)

- [Example on Github](https://github.com/isaidamier/blogs.biometrics.cryptoBlog)

- [The Android Platform Security Model](https://arxiv.org/pdf/1904.05572.pdf)
