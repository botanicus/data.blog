tags:
- iPad Pro
date: 2020-03-01 01:00:03.882546052 +00:00

---

# Programming on iPad Pro

_My iPad Pro has been my main and only machine for nearly 2 years now._

## Programming

While there are some tries to make a locally running shell for iOS[ˆ1], none of the solutions I've seen is anywhere close to being ready for real-world development.

That's no problem at all as I like to develop on a VPS anyway. It has many advantages:

- You can switch between (client) machines. Anything with an SSH client will do, regardless of the operation system.
- Putting iPad to sleep or even restarting it have no effects on code in the VPS – it just keeps running. If you have a large test suit, I'm sure you know what this means.
- You have your private staging. Just share an IP and port with your coworker and ask them whether the feature they asked you to make works as they wanted it.

![](blink-with-tmux.png)

## Mosh

Before you say _"yeah, but SSH is a pain in the arse"_, let me introduce you to Mosh. Mosh is a wrapper around SSH and it automatically reconnects if the connection drops or even if you change network.

It doesn't send over all the data, preventing flooding the connection, but only the data that are visible on the screen right now.

That means it's got no scroll buffer, but don't worry, just use tmux, `Ctrl+v [` 

## Testing web apps

![](windows-in-remotix.png)
![](inspect)

## Downloading files from the cloud

![](download-from-dropbox.jpg)

## Work-related communication

Spark
![](slack.png)

[ˆ1]: Such as [iSH](https://ish.app).