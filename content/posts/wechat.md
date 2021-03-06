---
title: "Installing Wechat Desktop Client"
date: 2022-03-06T15:44:00+11:00
tags: ["wechat", "linux"]
categories: ["Linux"]
draft: false
---

## Introduction {#introduction}

WeChat is a popular micro-messaging cross-platform app supporting text, image/videos, group chats with over 900 million active monthly users, mostly in China. Along with the basic messaging facilities, it also provides payment services in China to pay bills, order goods and services, transfer money and much more.

Currently there is no official Linux version of WeChat. This article will introduce how to install WeChat.


## Using WeChat on Linux desktop {#using-wechat-on-linux-desktop}

Just as you saw for WhatsApp on Linux, WeChat can also be used via a web browser by scanning the QR code. That of course doesn’t provide a native desktop experience.

You have two ways to use WeChat on Linux:

-   Use a dedicated unofficial WeChat client
-   Use a generic messaging service aggregator like Franz or Rambox

The unofficial WeChat client known as electronic-chat is discontinued unfortunately. It is no longer developed but you could still use it in snap format. However, I recommend not using it.


## Method 1: Wine {#method-1-wine}

The compatibility layer [Wine](https://wiki.archlinux.org/title/Wine) can be used to run WeChat within Linux.

If the WeChat shadow window is displayed on top of other windows during use, you can try to use **wine-for-wechat** in the [archlinuxcn](https://wiki.archlinux.org/title/Archlinuxcn) repository. This version of Wine uses a [patch](https://github.com/archlinuxcn/repo/blob/master/archlinuxcn/wine-for-wechat/wine-wechat.patch) for WeChat shadow windows.

In addition, it is also provided by [deepin-wine-wechat](https://aur.archlinux.org/packages/deepin-wine-wechat/) AUR (without patch), which is a Wine container configured for Arch. The WeChat version is the latest official version. You can also install wine-wechat from the archlinuxcn repository.

Details: [Linux/Arch Linux Unofficial user repositories/Use others repositorie/Arch Linux Chinese Community Repository]({{< relref "archLinuxUserRepository#arch-linux-chinese-community-repository" >}})


## Method 2: Installing WeChat on Linux via Rambox Pro {#method-2-installing-wechat-on-linux-via-rambox-pro}

Rambox Pro is another method that you can use to run WeChat on Linux. It is a workspace browser that allows you to run and manage as many applications as you want.

With this one, you cannot only run WeChat. But you can also run other applications like Discord, Airtable, Aol, Buffer, WhatsApp on Linux.

You can download and install Rambox Pro free of cost. Also, it comes with premium plans for advanced users. However, as long as you are running WeChat, the free plan is enough.

To get started with Rambox Pro, follow these steps:

At first, you have to install Rambox Pro. You can install it from the Desktop Software center, or you can run the below command:

```bash

boyang:~$ sudo snap install ramboxpro
[sudo] password for yanboyang713:
ramboxpro 1.4.1 from Rambox (ramboxapp✓) installed
```

Once installed, run the application from the menu, and it will ask you to sign up.
![](https://i1.wp.com/itsfoss.com/wp-content/uploads/2020/06/rambox-pro-signup.png?w=800&ssl=1)

After signing up, hit the Home icon, and now you have to select WeChat.
![](https://i2.wp.com/itsfoss.com/wp-content/uploads/2020/06/add-a-new-app.png?w=800&ssl=1)

Then click on the Add button.
![](https://i0.wp.com/itsfoss.com/wp-content/uploads/2020/06/add-wechat-2.png?w=800&ssl=1)

Once done, you will get to see a QR code on your screen.
![](https://i0.wp.com/itsfoss.com/wp-content/uploads/2020/06/scan-QR-code.png?w=800&ssl=1)

Scan the QR code from your smartphone’s WeChat app to log in to WeChat on your Linux machine.


## Method 2: Installing WeChat on Linux via Snap [Deprecated] {#method-2-installing-wechat-on-linux-via-snap-deprecated}

electronic-chat is a third party open source client for WeChat hosted on github. As you can see, the repository is archived and the project is no longer active.
Though the article has mentioned the steps, please avoid using this method.

You can use snap in your Linux distribution to install it:

```bash
sudo snap install electronic-wechat
```

This will install WeChat client. Once done, launch it from the menu by searching for WeChat.
![](https://i2.wp.com/itsfoss.com/wp-content/uploads/2020/06/wechat.jpg?w=800&ssl=1)

When you launch it for the first time, it will ask you to scan QR code.
![](https://i1.wp.com/itsfoss.com/wp-content/uploads/2020/06/scan-qr-code.jpg?w=800&ssl=1)

Select the option to Scan QR code from the app and you can use it from your Ubuntu system.

If at any moment, you are not satisfied and would rather prefer your phone to keep using WeChat, you can uninstall it using below command:

```bash
sudo snap remove electronic-wechat
```

That’s it. Enjoy WeChat on Linux desktop.
