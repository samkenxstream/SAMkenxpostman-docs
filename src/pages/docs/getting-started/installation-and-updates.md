---
title: "Installing and updating Postman"
updated: 2023-02-02
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Download and Install"
    url: "https://www.postman.com/downloads/"
  - type: section
    name: "Additional resources"
  - type: subtitle
    name: "Videos"
  - type: link
    name: "Unboxing What’s New in Postman v10 | Postman Intergalactic"
    url:  "https://youtu.be/LmEl7rHYhxU"
  - type: link
    name: "Agent for the Postman Web Client | Postman Level Up"
    url:  "https://www.youtube.com/watch?v=6xlJUx2ZMy4&list=PLM-7VG-sgbtC5tNXxd28cmePSa9BYwqeU&index=3"
  - type: subtitle
    name: "Blog posts"
  - type: link
    name: "Announcing Postman v10: The API Platform for an API-First World"
    url: "https://blog.postman.com/announcing-postman-v10/"
  - type: link
    name: "Introducing the Postman Agent: Send API Requests from Your Browser without Limits"
    url: "https://blog.postman.com/introducing-the-postman-agent-send-api-requests-from-your-browser-without-limits/"
  - type: section
    name: "Next steps"
  - type: link
    name: "Sending your first request"
    url: "/docs/getting-started/sending-the-first-request/"

---

Postman is available on the web at **[go.postman.co/home](https://go.postman.co/home)** and as a native desktop app for Mac (Intel or Apple silicon), Windows (Intel 32-bit or 64-bit), and Linux (64-bit) operating systems.

To get the latest version of the Postman desktop app, visit the [download page](https://www.postman.com/downloads/) and select **Download** for your platform.

To get an earlier version of the Postman desktop app, see [Installing earlier versions of Postman](/docs/administration/updating/#installing-earlier-versions-of-postman).

## Contents

* Installing Postman on the desktop
    * [Windows](#installing-postman-on-windows)
    * [Mac](#installing-postman-on-mac)
    * [Linux](#installing-postman-on-linux)
* [Using the Postman web app](#using-the-postman-web-app)
    * [Browser requirements](#browser-requirements)
    * [Installing the Postman Desktop Agent](#installing-the-postman-desktop-agent)
    * [Web limitations](#web-limitations)
* [Updating Postman](#updating-postman)
* [Chrome app (deprecated)](#postman-chrome-app-deprecated)
    * [Migrating to the native app](#migrating-to-the-native-app)
* [Using Postman behind a firewall](#using-postman-behind-a-firewall)
* [Troubleshooting your Postman installation](#troubleshooting-your-postman-installation)

## Installing Postman on Windows

Postman is available for Windows 7 and later.

1. [Download](https://www.postman.com/downloads/) the latest Postman version.
1. Select and run the `.exe` file to install Postman.

> Postman v9.4 is the last version of Postman that supports both 32-bit and 64-bit Windows. All versions of Postman following v9.4 will only work on 64-bit x86 Windows. You can continue to use Postman v9.4 and earlier on 32-bit Windows.

## Installing Postman on Mac

Postman is available for macOS 10.11 (El Capitan) and later.

1. [Download](https://www.postman.com/downloads/) the latest Postman version.

    > Make sure to download the **Mac Apple Chip** version if you have a Mac with an Apple silicon processor.

1. If your browser downloads the file as a zip file, find the file in the **Downloads** folder and unzip it.
1. In the **Downloads** folder, double-click the `Postman` file to install it.
1. When prompted, move the file to your __Applications__ folder. This will ensure that future updates can be installed correctly.

> You may encounter a "Library not loaded" error if you unzip and install Postman using a third-party archiving app. Use the default Archive Utility for Mac to unzip the file.

You can also install Postman using the [Homebrew](https://brew.sh/) package manager:

```sh
brew install --cask postman
```

## Installing Postman on Linux

You can install Postman on Linux by manually downloading it, using the [Snap](https://snapcraft.io/postman) store link, or with the command `snap install postman`.

To install manually, [download](https://www.postman.com/downloads/) and unzip the app, for example into the `Downloads` directory.

To start the app from a launcher icon, create a desktop file. Name the file `Postman.desktop` and save it in the following location:

```shell
~/.local/share/applications/Postman.desktop
```

Enter the following content in the file, replacing `/path/to/Downloads` with the location of the file, and save it:

```shell
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/path/to/Downloads/Postman/app/Postman %U
Icon=/path/to/Downloads/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
```

> Postman supports the following Linux distributions:
>
> * Ubuntu 14.04 and newer
> * Fedora 24
> * Debian 8 and newer
>
> The support of certain Linux distributions depends on if they're supported by Electron. Refer to [Electron's documentation](https://www.electronjs.org/docs/latest/development/build-instructions-linux).
>
> It's recommended you install [Snap](https://snapcraft.io/postman) as it includes all the libraries that the app needs and they're bundled with the app itself.
>
> Avoid starting Postman using the `sudo` command, as it will create permission issues on the files created by Postman.
>
> Make sure you have read/write permission for the `~/.config` folder where Postman stores information.
>
> If you are an Ubuntu 18 user, you will also need to install the `libgconf-2-4` package with the command `apt-get install libgconf-2-4`

## Using the Postman web app

You can use Postman in your web browser to carry out your API development and testing tasks in conjunction with the Postman Agents. To access the Postman web app, visit [go.postman.co/home](https://go.postman.co/home).

> If you are using the Postman web app, Postman recommends using the Postman Desktop Agent for the best experience. See [About the Postman Agent](/docs/getting-started/about-postman-agent/) for more information.

### Browser requirements

The Postman web app is optimized for the following browsers:

* Chrome (78 and higher)
* Firefox (76 and higher)
* Edge (79 and higher)
* Safari (13.1.1 and higher)

### Installing the Postman Desktop Agent

If you are using the Postman web app, Postman recommends downloading and installing the [Postman Desktop Agent](/docs/getting-started/about-postman-agent/#the-postman-desktop-agent), a micro-application that runs locally on your desktop. The Desktop Agent overcomes the cross-origin resource sharing (CORS) limitations of browsers and acts as your agent for making API requests from the Postman web app.

### Web limitations

The Postman web app is under active development. There are features you can only access in the Postman desktop app, not in your browser:

* **Find and replace** - The Postman desktop app supports [finding and replacing values in a workspace](/docs/getting-started/navigating-postman/#find-and-replace), but this function isn't available on the Postman web app yet.
* **Certificates and proxy** - The Postman desktop app enables you to customize [certificates](/docs/sending-requests/certificates/) and [proxy configurations](/docs/getting-started/proxy/#configuring-proxy-settings). On the Postman web app, these take the browser defined value and can't be overridden by Postman.
* **Postman Interceptor** - [Interceptor](/docs/sending-requests/capturing-request-data/interceptor/) syncs cookies from your browser to the Postman desktop app and captures network requests directly from the browser. It's not possible to use Interceptor with the Postman web app.
* **Scratch Pad** - The Postman desktop app supports working in Postman offline using the [Scratch Pad](/docs/getting-started/using-scratch-pad/).

## Updating Postman

The Postman desktop app notifies you when a major update is available. For other updates, there is a dot on the settings icon <img alt="Settings icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px">. If the indicator is red instead of orange, it indicates a failed update.

<img alt="Update Ready" src="https://assets.postman.com/postman-docs/v10/update-ready-v10.jpg" width="300px"/>

Select the update option to download or install the latest update. If you are using Postman v9.13 or later, Postman automatically downloads updates. Postman notifies you when the download is complete and prompts you to restart Postman to apply the updates.

<img alt="Check for updates" src="https://assets.postman.com/postman-docs/v10/settings-update-v10.jpg"/>

## Postman Chrome app (deprecated)

The Postman Chrome app is deprecated. If you use the Chrome app, you can keep your data when you [switch to using Postman](#migrating-to-the-native-app) either by syncing with your Postman account or by exporting from Chrome and importing into Postman.

The Postman desktop app is built on [Electron](https://www.electronjs.org/), and [overcomes a number of restrictions](https://blog.postman.com/going-native/) of the Chrome platform.

* The native apps let you work with [cookies](/docs/sending-requests/cookies/) directly.
* Unlike the Chrome app, the [Interceptor](/docs/sending-requests/capturing-request-data/interceptor/) doesn't need a separate extension.
* The native apps come with a built-in proxy that you can use to [capture network traffic](/docs/sending-requests/capturing-request-data/capturing-http-requests/).
* The native apps aren't restricted by the Chrome standards for the menu bar. You can check for updates, create Postman Windows and tabs, and edit preferences.
* The native apps let you send headers like `Origin` and `User-Agent`. These are restricted in the Chrome app.
* The "don't follow redirects" option exists in the native apps to prevent requests that return a 300-series response from being automatically redirected—doing this in the Chrome app requires the Interceptor extension.
* The native app has a built-in [console](/docs/sending-requests/troubleshooting-api-requests/), which enables you to view the network request details for API calls.

### Migrating to the native app

To switch from the Chrome app to native, [download](https://www.postman.com/downloads/) Postman and [sign in to your account](https://go.postman.co/). Start the native app, and your history and collections will be automatically synced.

Alternatively, if you don't want to sign in to your Postman account, you can bulk export your Postman data from the Chrome app, and then bulk import into the new native app at **Settings > Data**.

![Import Export Data](https://assets.postman.com/postman-docs/export-data-v86.jpg)

> Note that importing will overwrite your existing data. For more on bulk import, see [Importing Postman data](/docs/getting-started/importing-and-exporting-data/).

## Using Postman behind a firewall

Postman's infrastructure runs on Amazon's AWS platform. If you are operating behind a network firewall, you'll need to allow the following domains to make WebSocket connections for Postman:

* `\*.getpostman.com`
* `\*.postman.co`
* `\*.pstmn.io`
* `\*postman.com`

By default, WebSocket connections use the same ports as HTTP (80) and HTTPS (443). For Postman v10, allow the following domains:

Postman web app - websocket connections:

* `https://bifrost-web-v10.gw.postman.com`
* `https://bifrost-web-public-v10.gw.postman.com`
* `https://bifrost-web-v10.gw.postman.co`

Postman desktop app - websocket connections:

* `https://bifrost-v10-global.gw.postman.com`
* `https://bifrost-premium-v10-global.gw.postman.com`

Postman desktop app - HTTP connections:

* `https://bifrost-https-v10.gw.postman.com`
* `https://bifrost-premium-https-v10.gw.postman.com`

Postman doesn't have a fixed IP range that can be provided. If necessary, refer to the [current AWS IP ranges](https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html) and allow the broad range provided.

## Troubleshooting your Postman installation

If you encounter any issues installing and running Postman, check out the following tips. If these don't help, refer to the installation posts on the [community forum](https://community.postman.com/tags/installation) and create a new post if your issue isn't already covered. You can also contact [Postman support](https://www.postman.com/support).

### Update failed error

If you get an __Update Failed__ notification in Postman, you can use the DevTools to investigate.

![update-error-dialog](https://assets.postman.com/postman-docs/v10/update-error-dialog.jpg)

Open the DevTools using **View > Developer > Show DevTools (Current View)**.

Some known errors are as follows:

* **Error message** - `Cannot update while running on a read-only volume`
    * This error means that the app user doesn't have write permission in the directory where Postman is installed. To resolve the problem, move Postman to a directory where the user has write permissions, for example the `/Application` directory for Mac, and to the `home` directory for Linux.

* **Error message** - `Code signature at URL file:///... did not pass validation: code object is not signed at all`
    * This error means that there are multiple updates running at the same time. This can happen when the app is opened before the earlier update could finish. To resolve the problem, quit and reopen the app.

* **Error message** - `EACCES: permission denied, open '/opt/Postman/Postman-1620288011421.tar.gz`
    * This error means that the app user doesn't have write permission in the directory where Postman is installed. To resolve the problem, move Postman to a directory where the user has write permissions, for example the `home` directory for Linux.

### Update not available

If you are using Postman for Linux, and installed the app with the Ubuntu Software Center or Snap Store, you may not have the __Check for updates__ option. This is because the updates are handled by the store, which automatically updates Postman on a regular cadence.
