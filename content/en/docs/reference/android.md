---
title: "Android"
description: "Resources for passkeys in Android"
date: 2022-09-03T16:09:38.358Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 1001
toc: true
---

{{% ds-pa %}}

## Overview

The platform authenticator in Android 9+ has the following capabilities:

- creating and using passkeys that are backed up to Google Password Manager
- using a passkey from the local Android device to sign into services on another device (such as a laptop or desktop), using FIDO [Cross-Device Authentication](../terms#cross-device-authentication-cda)

## Platform Notes

- **Credential Manager** is a new Android Jetpack API that supports multiple sign-in methods, including passkeys, in a single API, thus simplifying the integration for developers.<br><br><a href="https://developer.android.com/training/sign-in/passkeys" target="_blank"><button type="button" class="btn btn-light">Credential Manager API <i class="bi bi-box-arrow-up-right ms-2"></i></button></a>

- The [Device Public Key (DPK)](../terms#device-public-key-dpk) extension is supported in beta, but is currently gated behind a flag in Chrome. Developers can enable `chrome://flags/#enable-experimental-web-platform-features` to experiment with DPK on Android, or on desktop Chrome when using [Cross-Device Authentication](../terms#cross-device-authentication-cda) with an Android device.

## Resources

- [Credential Manager API](https://developer.android.com/training/sign-in/passkeys)
- [Security of Passkeys in the Google Password Manager](https://security.googleblog.com/2022/10/SecurityofPasskeysintheGooglePasswordManager.html)
- [Sample app](https://github.com/android/identity-samples/tree/main/Fido2)
