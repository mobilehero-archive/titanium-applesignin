# @titanium/applesignin

[![@titanium/applesignin](https://img.shields.io/npm/v/@titanium/applesignin.png)](https://www.npmjs.com/package/@titanium/applesignin)


> Native modules that allows you to use the iOS 13+ Apple Sign In API with Axway Titanium native mobile apps.

* [📝 Description](#-description)
* [🚀 Getting Started](#-getting-started)
	* [Install `@titanium/applesignin` in root of project](#install-titaniumapplesignin-in-root-of-project)
	* [Add entitlement to `tiapp.xml`](#add-entitlement-to-tiappxml)
	* [Add to Apple Developer Account](#add-to-apple-developer-account)
* [✨Features](#features)
* [Requirements](#requirements)
* [Example](#example)
* [APIs](#apis)
	* [Methods](#methods)
		* [`createLoginButton()`](#createloginbutton)
		* [`authorize({ scopes })`](#authorize-scopes-)
		* [`getCredentialState(userId, callback)`](#getcredentialstateuserid-callback)
	* [Events](#events)
		* [`login`](#login)
* [License](#license)
* [Author](#author)
* [📚Learn More](#learn-more)
* [📣 Feedback](#-feedback)
* [©️ Legal](#️-legal)


## 📝 Description

This is a repackaging of the compiled iOS module for [ti.applesignin](https://github.com/hansemannn/titanium-apple-sign-in) to allow for installation via npm.

## 🚀 Getting Started

### Install `@titanium/applesignin` in root of project

```bash
npm install @titanium/applesignin
```

### Add entitlement to `tiapp.xml`

```xml
     <entitlements>
        <dict>
          <key>com.apple.developer.applesignin</key>
          <array>
              <string>Default</string>
          </array>
        </dict>
      </entitlements>
```

### Add to Apple Developer Account

1. Go to your App Identifiers - https://developer.apple.com/account/resources/identifiers/list
2. Create new identifier (or edit an existing one)
3. Add capability by checking the box for `Sign In with Apple`

![Sign In with Apple](https://cdn.secure-api.org/images/sign-in-with-apple-capability.png)

4. Create a provisioning profile for that app id - https://developer.apple.com/account/resources/profiles/list
5. Download and install that provisioning profile
6. Make sure id of Titanium app matches App ID created: `<id>YOUR.APP.ID</id>`


## ✨Features

* [x] Includes Titanium native iOS module: `ti.applesignin 1.1.0`

## Requirements

The following project- and OS-requirements are necessary:

- [x] Xcode 11+
- [x] iOS 13+
- [x] Titanium SDK 8.0.0+

## Example

This module was designed to follow a similar scheme like Ti.Facebook and Ti.GoogleSignIn.

```js
var AppleSignIn = require('@titanium/applesignin');

AppleSignIn.addEventListener('login', function (event) {
  console.warn(`event: ${JSON.stringify(event, null, 2)}`);
  if (!event.success) {
    alert(event.error);
    return;
  }
});

var win = Ti.UI.createWindow({
  backgroundColor: '#fff'
});

var btn = AppleSignIn.createLoginButton({ width: 280, height: 38 });

btn.addEventListener('click', function () {
  AppleSignIn.authorize();
});

win.add(btn);
win.open();
```

## APIs

### Methods

#### `createLoginButton()`

Creates a new localized login button.

#### `authorize({ scopes })`

Starts an authorization flow with an optional array of scoped. Defaults to all scopes ( `fullName` and `email` ).

#### `getCredentialState(userId, callback)`

Fetches the current credential state with a given user-id (received from the `event.profile.userId`  key of the `login` event).
The result is returned to the `state` parameter of the `callback` and can be authorized, revoked, transferred or unknown.

### Events

#### `login`

The login event with the user's `profile`.


## License

MIT

## Author

Hans Knöchel



## 📚Learn More

- [ti.applesignin GitHub Repo](https://github.com/hansemannn/titanium-apple-sign-in) - Repo for original ti.applesignin module


## 📣 Feedback

Have an idea or a comment?  [Join in the conversation here](https://github.com/brentonhouse/titanium-applesignin/issues)! 

## ©️ Legal

Modules are licensed under Apache 2.0 from https://github.com/appcelerator-modules/titanium-applesignin

Alloy is developed by Appcelerator and the community and is Copyright © 2012-Present by Appcelerator, Inc. All Rights Reserved.

Alloy is made available under the Apache Public License, version 2. See their license file for more information.

Appcelerator is a registered trademark of Appcelerator, Inc. Titanium is a registered trademark of Appcelerator, Inc. Please see the LEGAL information about using trademarks, privacy policy, terms of usage and other legal information at http://www.appcelerator.com/legal.