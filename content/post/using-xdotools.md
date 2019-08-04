---
title: "Using xdotool to automate text input"
date: 2019-07-13T22:31:02+05:30
categories: ["linux"]
---
Ever since I've started using Ubuntu as my daily driver at work I'm always amazed by the kind of customizations and tiny tweaks you can do to be a bit more productive and make your life easier. Here is one such think I had configured a few days back.

At work almost all the machines within the internal network can be accessed by using their fully qualified domain name (FQDN). The problem is that the domain name is quite long. Along with the dots it's 18 characters that is to be typed if you want to SSH in or connect to a web server running on that machine.

I was looking for a way in which if I press a specific key combo the text should be typed into whatever window that is in focus.

After searching around for a bit I came across a package called xdotool. This is the description of the package in the apt repository - 

>simulate (generate) X11 keyboard/mouse input events xdotool lets you programmatically (or manually) simulate keyboard input and mouse activity, move and resize windows, etc. It does this using X11's XTEST extension and other Xlib functions.

Sounds exactly like what we need and this is how I set it up.

1. Install it using the command `sudo apt install xdotool`
2. Try running the command `xdotool sleep 0.3 type <the text that you want to type>`. This should output the text that you entered.
3. Configure this command in your system shortcuts. In Gnome this can be done by navigating to _Settings_ -> _Keyboard_ -> _Keyboard Shortcuts_.

Once this is done the next time you press the key combo that you have configured the text gets typed to your active window be it a terminal or a web browser.

##### Note
The sleep argument is provided so that there is a sufficent delay between pressing the shortcut and invoking the type command. If this was not set some of the starting characters in your string will get gobbled up.
