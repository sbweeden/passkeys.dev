---
title: "macOS"
description: "Resources for passkeys in Apple macOS"
date: 2022-09-03T16:09:38.358Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 1004
toc: true
---

{{% ds-full %}}

## Overview

The platform authenticator in macOS Ventura (13) has the following capabilities:

- creating and using passkeys that are backed up to iCloud Keychain
- creating and using passkeys on/from another device, such as:
  - an iPhone or iPad signed in to a different iCloud account
  - an Android device
  - a FIDO2 security key<sup>1</sup>

<p class="fs-6 text-muted"><sup>1</sup> On macOS, user verification methods (device PIN, biometric, etc) must already be configured on the security key prior to credential creation</p>

## Platform Notes

### Legacy Credentials

WebAuthn credentials created using the platform authenticator in macOS Monterey (12) and earlier ***will not*** be converted to passkeys but will remain available for the lifetime of the device.

<!-- TODO: cross link to generic content about "upgrading to a passkey" -->
To replace a legacy platform credential with a passkey, start a credential registration ceremony and pass **the same user handle** (user.id) in the request. macOS will overwrite the legacy credential with a new passkey that will be backed up to iCloud Keychain.

### Browser Behavior

**Safari**: credentials created in Safari are passkeys, are backed up to iCloud Keychain, and are available in other apps and services.

**Chrome**: credentials created by Chrome are currently [***single-device*** passkeys](/docs/reference/terms/#single-device-passkey), are not backed up to iCloud Keychain, and are ***not available outside of Chrome***.

**Edge**: credentials created by Edge are currently [***single-device*** passkeys](/docs/reference/terms/#single-device-passkey), are not backed up to iCloud Keychain, and are ***not available outside of Edge***.

**Firefox**: passkeys are not currently supported in Firefox on macOS. [***Single-device*** passkeys](/docs/reference/terms/#single-device-passkey) on a FIDO2 security key are supported. [User verification]({{< ref "terms/#user-verification-uv" >}}) is not supported, though, which makes it impossible to implement WebAuthn-based passwordless authentication at this time.

## Resources

- [Apple landing page for passkeys](https://developer.apple.com/passkeys/)
- [About the security of passkeys](https://support.apple.com/en-us/HT213305)
- [Supporting passkeys](https://developer.apple.com/documentation/authenticationservices/public-private_key_authentication/supporting_passkeys)
- [Supporting single-device passkeys on security keys](https://developer.apple.com/documentation/authenticationservices/public-private_key_authentication/supporting_security_key_authentication_using_physical_keys)
- [Sample Code](https://developer.apple.com/documentation/authenticationservices/connecting_to_a_service_with_passkeys)
