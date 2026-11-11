Appmant

A terminal-based Android app manager for rooted devices, built for Termux.

Appmant provides an interactive "fzf" (https://github.com/junegunn/fzf)-powered interface to browse and manage installed Android applications across users and profiles.

Switch between profiles, filter user and system apps, search packages, inspect app details, and manage enabled or frozen states—all from your terminal.

Screenshots

<p align="center">
  <img src="assets/screenshot1.jpg" width="32%" alt="Appmant main interface">
  <img src="assets/screenshot2.jpg" width="32%" alt="Appmant app management">
  <img src="assets/screenshot3.jpg" width="32%" alt="Appmant profile and package view">
</p>Features

- Dynamic Android user and profile discovery.
- User and system application filters.
- Latest-first and alphabetical sorting.
- Interactive package search.
- Application previews and package information.
- Freeze and enable applications.
- Single and multi-selection.
- Per-user application uninstall.
- Android App Info shortcut.
- Built-in keyboard help.

Requirements

- Rooted Android device.
- "Termux" (https://github.com/termux/termux-app).
- "fzf".
- Working "sudo" command with root access.
- "aapt2" (optional, for application-label extraction in previews).

Installation

Clone the repository:

git clone https://github.com/royalewhite/Appmant.git
cd Appmant

Install "fzf":

pkg install fzf

Launch Appmant:

./appmant

Global Installation

To launch Appmant from any directory:

install -m 755 appmant appmant-preview appmant-profiles "$PREFIX/bin/"

Launch it with:

appmant

Keep all three executable files together. The main script relies on the preview and profile helper scripts.

Keyboard Controls

Key| Action
"1–9" / "ALT-1–9"| Switch Android profiles
Header tabs| Switch profiles, filters, and sorting
"TAB" / "s"| Toggle User / System apps
"ALT-U"| Show User apps
"ALT-Y"| Show System apps
"o" / "ALT-O"| Toggle Latest / Name sorting
"j" / "↓"| Move down
"k" / "↑"| Move up
"g" / "G"| Jump to top / bottom
"CTRL-D" / "CTRL-U"| Half-page down / up
"SPACE"| Select / deselect an app
"u"| Clear selections
"f" / "CTRL-F"| Freeze selected apps
"e" / "CTRL-T"| Enable selected apps
"d" / "x" / "ENTER"| Uninstall selected or current app
"i"| Open Android App Info
"/" / "CTRL-R"| Open search
"ENTER" (in search)| Hide search and keep the filter
"ESC"| Clear search and close search mode
"r"| Refresh package list
"?"| Show help
"q" / "CTRL-Q"| Quit

App Operations

- Freeze: Disables an application for the selected Android user.
- Enable: Re-enables an application for the selected Android user.
- Uninstall: Removes an application for the selected user. This does not remove the underlying system APK.

Troubleshooting

Profile discovery fails

Check root access and verify that "sudo" can execute Android package-manager commands.

The interface does not start

Make sure "fzf" is installed and all three Appmant scripts are present.

Application labels are missing in previews

Install or configure "aapt2" at "$PREFIX/bin/aapt2". Package names and other available metadata can still be displayed without it.

Compatibility

Developed and tested on Samsung Galaxy M14 5G running Android 15 and One UI 7 with Termux and root access.

Other rooted Android devices may work depending on their package-manager behavior.

Contributing

Found a bug or have an idea?

- Open an "Issue" (https://github.com/royalewhite/Appmant/issues).
- Submit a "Pull Request" (https://github.com/royalewhite/Appmant/pulls).

---

Appmant — Android app management, straight from your terminal. 👾
