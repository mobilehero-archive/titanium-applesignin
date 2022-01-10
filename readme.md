[//]: # (header-start)

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
<h1 align="center">
	Axway Amplify End-of-Life Announcement
</h1>
<h2 align="center">
	👇 &nbsp; See notes below  &nbsp; 👇
</h2>	
</a>

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		<img src="https://cdn.secure-api.org/images/RIP-Axway-Amplify-Titanium.png" alt="RIP Axway Amplify Titanium (2010 - 2022)" width="80%" />
	</p>
</a>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		🪦 &nbsp; RIP Axway Amplify Titanium (2010 - 2022)
	</p>
</a>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		🪦 &nbsp; RIP Axway Amplify Cloud Services (2012 - 2022)
	</p>
</a>
<hr>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<h4 align="center">
🛑 &nbsp;&nbsp; All products affected by the announcements will not be supported by Axway effective their EOL dates in 2022.
</h4>

<h4 align="center">
Some Open-Source versions of Axway products will live on after End-of-Life (EOL) Axway Amplify product announcements.  However, some products are closed-source and will NOT continue after the shut down in 2022.  
	</h4>
</a>
<p>&nbsp;</p>

> 👉 &nbsp;&nbsp; Stay tuned for more info as plans are being made to save the Titanium project and move it under the control of a independent group of developers.

<p>&nbsp;</p>
<hr>
<p>&nbsp;</p>
<p>&nbsp;</p>

[//]: # (header-end)



# @titanium/applesignin

[![@titanium/applesignin](https://img.shields.io/npm/v/@titanium/applesignin.png)](https://www.npmjs.com/package/@titanium/applesignin)
[![Dependabot Status](https://api.dependabot.com/badges/status?host=github&repo=brentonhouse/titanium-applesignin)](https://dependabot.com)


> This is an experiment by [Brenton House](https://brenton.house) using open-source projects.  You are welcome to try it out but be aware of the risks_

<br/>

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

> Native modules that allows you to use the iOS 13+ Apple Sign In API with Axway Titanium native mobile apps.   
>     
> This is a repackaging of the compiled iOS module for [ti.applesignin](https://github.com/appcelerator-modules/titanium-apple-sign-in) to allow for installation via npm.

## 🚀 Getting Started

### Install `@titanium/applesignin` in root of project

```bash
npm install @titanium/applesignin
```

### Add entitlement to `tiapp.xml`

> Be sure the `<entitlements>` element goes **outside** of the `<plist>` element in your `tiapp.xml` file!

```xml
<ti:app xmlns:ti="http://ti.appcelerator.org">
	<ios>
		<plist>
		</plist>
		<entitlements>
			<dict>
				<key>com.apple.developer.applesignin</key>
				<array>
					<string>Default</string>
				</array>
			</dict>
		</entitlements>
	</ios>
</ti:app>
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

* [x] Includes Titanium native iOS module: `ti.applesignin 1.1.1`

## Requirements

The following project- and OS-requirements are necessary:

- [x] Xcode 11+
- [x] iOS 13+
- [x] Titanium SDK 8.0.0+

## Example

This module was designed to follow a similar scheme like Ti.Facebook and Ti.GoogleSignIn.

```js
const AppleSignIn = require('@titanium/applesignin');

AppleSignIn.addEventListener('login', function (event) {
  console.warn(`event: ${JSON.stringify(event, null, 2)}`);
  if (!event.success) {
    alert(event.error);
    return;
  }
});

const win = Ti.UI.createWindow({
  backgroundColor: '#fff'
});

const btn = AppleSignIn.createLoginButton({ width: 280, height: 38 });

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

⭐  [ti.applesignin GitHub Repo](https://github.com/appcelerator-modules/titanium-apple-sign-in) - Repo for original ti.applesignin module   


## 📣 Feedback

Have an idea or a comment?  [Join in the conversation here](https://github.com/brentonhouse/titanium-applesignin/issues)! 

## ©️ Legal

Modules are licensed under Apache 2.0 from https://github.com/appcelerator-modules/titanium-applesignin

Alloy is developed by Appcelerator and the community and is Copyright © 2012-Present by Appcelerator, Inc. All Rights Reserved.

Alloy is made available under the Apache Public License, version 2. See their license file for more information.

Appcelerator is a registered trademark of Appcelerator, Inc. Titanium is a registered trademark of Appcelerator, Inc. Please see the LEGAL information about using trademarks, privacy policy, terms of usage and other legal information at http://www.appcelerator.com/legal.