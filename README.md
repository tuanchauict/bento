# Bento

A macOS menu bar app that saves groups of windows as **workspaces** and brings a whole workspace forward in one
step: each window goes back to its position and size, and only those windows are raised, even when an app has many
others open. Its **quick switcher** (⌥Tab, as in AltTab) lists the workspaces and every open window, and a
**window switcher** (⌃⌥Space) jumps to any window on any desktop.
Up to 0.2.0 it was called Oh my windows. Updating keeps your workspaces, settings and permissions.

![The quick switcher: workspaces on top, then every open window](screenshots/quick-switcher.png)

This repository holds the releases only.

## Install

```sh
brew install --cask tuanchauict/tap/bento
```

Or download [**Bento.dmg**](../../releases/latest/download/Bento.dmg), open it and drag Bento onto Applications.
Needs macOS 14 or later, on Apple silicon or Intel.

## Permissions

- **Accessibility** (System Settings > Privacy & Security > Accessibility) is required: it is how windows are found,
  moved and raised.
- **Screen Recording** (Screen & System Audio Recording) is optional. It gives the switchers a preview of each
  window; without it they show app icons. macOS may ask you to reopen the app after you allow it.

## Using it

1. Arrange the windows you want: positions, sizes, which is on top.
2. Menu bar icon > **New Workspace from Current Windows…**, tick the windows, **Save**.
3. Switch with the menu, the quick switcher (**⌥Tab**) or, with Pro, a shortcut of the workspace's own. Typing
   in the quick switcher filters workspaces by name and windows by app or title.

Hold ⌃⌥ and press Space for the window switcher, Space again to move on, and let go to jump to the highlighted
window. It lists the windows of every desktop, most recently used first, and marks the ones on another desktop,
minimized or hidden.

Click **Letters** on either switcher and every card gets a letter: type it to switch. The quick switcher then opens
on the letters, with / to search. By default each workspace and window keeps its letter; the General settings can
instead give each row of cards a row of the keyboard (1 2 3…, Q W E…). The gear on the switchers opens their settings.

![The window switcher](screenshots/window-switcher.png)

Settings are under menu bar icon > **Manage Workspaces…**: each workspace's layout, shortcut and windows. Finding
windows on other desktops, and jumping to them, uses the **Enhanced** raise method (the default), which relies on
private macOS calls as AltTab and yabai do.

![A workspace in the settings](screenshots/workspace-settings.png)

## Bento Pro

Bento is free with up to 2 workspaces, and needs no account. **Bento Pro** adds unlimited workspaces, a shortcut for
each workspace, and every Pro feature to come: **$12 once, for up to 3 Macs**, no subscription.
[Buy Bento Pro](https://buy.polar.sh/polar_cl_mI1jP2w2t5yHUCYIXt7tSmGk4wg3FaSEcIzZ94g0nyx). Needs Bento 1.0 or later.

- Checkout is by [Polar](https://polar.sh), which handles the tax and emails your license key. Paste it in menu bar
  icon > **Get Bento Pro…** and press **Activate**.
- Activating sends the key and this Mac's name to Polar once. The key is never checked again, so Pro keeps working
  offline. [Privacy](#privacy) lists every request Bento makes.
- Nothing is deleted without Pro. The first two workspaces in your list work; any past them, and shortcuts set
  with Pro, stay listed but paused, and work again when you enter the key. Adding a third workspace or setting a
  shortcut asks for Pro; clearing a shortcut never does.
- Questions about a purchase, bugs or ideas: [open an issue](https://github.com/tuanchauict/bento/issues) or email
  [bento@iamtuna.org](mailto:bento@iamtuna.org).
- To move Pro to another Mac, remove it on the old one under **Manage Workspaces…** > **Bento Pro**, or free a Mac
  in the [customer portal](https://polar.sh/tuanchau/portal), where you can also find your key again.

## Privacy

Bento has no account, no analytics and no crash reports. Workspaces, window pictures and settings stay on your Mac,
in `~/Library/Application Support/WindowPair` (the app's first name), `~/Library/Caches/org.iamtuna.WindowPair` and
Bento's preferences. These are all the requests it makes:

| When | To | What it sends |
|---|---|---|
| Once a day, unless you turn it off, and when you choose **Check for Updates…** | GitHub (`api.github.com`) | A request for this repository's latest release, nothing else |
| When you press **Activate** | Polar | The key, Bento's id at Polar and this Mac's name |
| When you press **Remove from This Mac** | Polar | The key, Bento's id at Polar and the activation's id |

Each request names the app only as `Bento`, keeps no cookies and adds no id of its own; as with any connection, the
server sees your internet address. To stop the daily check, turn it off in **Manage Workspaces… > General > Updates**;
Bento then checks only when you ask. A new version shows in the menu; installing it is up to you. Of GitHub's answer,
Bento uses the version number only.

Accessibility is used to find, move and raise windows, from their titles and positions. Bento does not read what you
type into other apps or what is inside your windows. Window pictures (Screen Recording) are taken only while a
switcher, or the Capture Windows sheet, is open, and never leave your Mac.

Checkout is on Polar's site: Polar handles the payment, and the seller sees what an order needs (your name, email
address and country, and the names of the Macs your key is on), used only to deliver Pro, answer you and refund.

## Update and uninstall

Menu bar icon > **Check for Updates…** says whether a newer Bento is out. With Homebrew:

```sh
brew upgrade --cask bento
brew uninstall --cask bento    # add --zap to also remove saved workspaces, caches and preferences
```
