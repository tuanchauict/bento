# Oh my windows

A macOS menu bar app that saves groups of windows as **workspaces** and brings a whole workspace forward in one
step: each window goes back to its position and size, and only those windows are raised, even when an app has many
others open. It also has an AltTab-style **window switcher** (⌥Tab) for jumping to any window on any desktop.

This repository holds the releases only.

## Install

```sh
brew install --cask tuanchauict/tap/oh-my-windows
```

Or download the zip from [Releases](../../releases), unzip it and move **Oh my windows.app** to Applications.
Needs macOS 14 or later. Builds are signed and notarized, and run on Apple silicon and Intel.

## Permissions

- **Accessibility** (System Settings > Privacy & Security > Accessibility) is required: it is how windows are found,
  moved and raised.
- **Screen Recording** (Screen & System Audio Recording) is optional. It gives the switchers a preview of each
  window; without it they show app icons. macOS may ask you to reopen the app after you allow it.

## Using it

1. Arrange the windows you want: positions, sizes, which is on top.
2. Menu bar icon > **New Workspace from Current Windows…**, tick the windows, **Save**.
3. Switch with the menu, a per-workspace shortcut, or the quick switcher (**⌃⌥Space**). Typing in the quick
   switcher filters workspaces by name and windows by app or title.

Settings are under menu bar icon > **Manage Workspaces…**. Finding windows on other desktops, and jumping to them,
uses the **Enhanced** raise method (the default), which relies on private macOS calls as AltTab and yabai do.

## Update and uninstall

```sh
brew upgrade --cask oh-my-windows
brew uninstall --cask oh-my-windows          # add --zap to also remove saved workspaces and caches
```
