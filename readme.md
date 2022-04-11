[//]: # (header-start)

<h1 align="center">
	<a href="https://blog.axway.com/mobile-apps/changes-to-application-development-services">
		Preparing for end of Axway
	</a>	
</h1>
<h2 align="center">
	👇 &nbsp; support for Amplify Cloud and Mobile   &nbsp; 👇
</h2>	

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		<img src="https://cdn.secure-api.org/images/RIP-Axway-Amplify-Titanium.png" alt="RIP Axway Amplify Titanium (2010 - 2022)" width="80%" />
	</p>
</a>	
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/changes-to-application-development-services">
			🪦 &nbsp; RIP Axway Amplify Titanium (2010 - 2022)
	</a>
</p>
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">
			🪦 &nbsp; RIP Axway Amplify Cloud Services (2012 - 2022)
	</a>
</p>
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">
			🪦 &nbsp; RIP Axway Amplify Crash Analytics (2015 - 2022)
	</a>
</p>

<hr>
<h4 align="center">
🛑 &nbsp;&nbsp; <a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">Axway support for Amplify products has ended</a> for most products related to mobile and cloud. 
</h4>

<h4 align="center">
A few of the open-source versions of Axway Amplify products will live on after <a href="">Axway Amplify End-of-Life</a> (EOL) announcements.  However, all closed-source projects and most open-source projects are now dead.  
	</h4>

<p>&nbsp;</p>

> 👉 &nbsp;&nbsp; A group of Axway employees, ex-Axway employees, and some developers from Titanium community have created a legal org and now officially decide all matters related to future of these products.  

<p>&nbsp;</p>
<hr>


## API FAQ:

* [API Best Practices](https://brenton.house)
* [What is API Security?](https://brenton.house/what-is-api-security-5ca8117d4911)
* [OWASP Top 10 List for API Security](https://www.youtube.com/watch?v=GLVHDj0Cpg4)
* [What is API Security?](https://brenton.house/what-is-api-security-5ca8117d4911)
* [Top API Trends for 2022](https://brenton.house/top-10-api-integration-trends-for-2022-49b05f2ef299)
* [What is a Frankenstein API?](https://brenton.house/what-is-a-frankenstein-api-4d6e59fca6)
* [What is a Zombie API?](https://brenton.house/what-is-a-zombie-api-6e5427c39b6a)
* [API Developer Experience](https://brenton.house/keys-to-winning-with-an-awesome-api-developer-experience-62dd2fa668f4)
* [API Cybersecurity 101](https://brenton.house/what-is-api-security-5ca8117d4911)
* [YouTube API Videos](https://youtube.com/brentonhouse)
* [YouTube API Shorts Videos](https://youtube.com/apishorts)

&nbsp;

[![Click to watch on Youtube](https://img.youtube.com/vi/GLVHDj0Cpg4/0.jpg)](https://www.youtube.com/watch?v=GLVHDj0Cpg4&list=PLsy9MwYlG1pew6sktCAIFD5tbrXy9HUQ7  "Click to watch on YouTube")


> &nbsp; [↑ Watch video on YouTube ↑](https://www.youtube.com/watch?v=GLVHDj0Cpg4&list=PLsy9MwYlG1pew6sktCAIFD5tbrXy9HUQ7)

&nbsp;



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