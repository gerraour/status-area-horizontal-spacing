This is a GNOME shell extension that reduces the horizontal spacing between status area icons (top-right of the panel: volume indicator, etc). (Tested in GNOME 3.2, 3.4, 3.6, 3.8).

Status area before (default 12px hpadding):

![original (12px padding)](status_area_original.png)

Status area after (6px hpadding):

![after with 6px padding](status_area_6px.png)

## Installation
One-click install from extensions.gnome.org: [link here](https://extensions.gnome.org/extension/355/status-area-horizontal-spacing/).

Manual install: download the files (go to 'Downloads' and select the zip file).
Start `gnome-tweak-tool` and select 'Shell Extensions > Install Shell Extension > (zip file you just downloaded)'. 

## Configuring

### GNOME 3.10+
You can configure it via the extensions.gnome.org website, or using the `gnome-shell-extension-prefs` command.
The "horizontal spacing" setting is the padding between items in the top-right area of the panel.
There is a new "status icon spacing" setting which is the spacing between the status icons in the new aggregate menu button (the single button that has all the wifi/battery etc icons).

### GNOME 3.4+
You can configure it via the extensions.gnome.org website, or using the `gnome-shell-extension-prefs` command.

### GNOME 3.2
Edit `extension.js` and change the line:

    const HPADDING = 6;

to whatever spacing you want. The original GNOME-shell value is 12px, and the default for this plugin is 6px.
At least 6px is recommended.

## Alternatives
If you do not want to use the extension, you can modify `/usr/share/gnome-shell/theme/gnome-shell.css`: change the `-natural-hpadding` property of `.panel-button`, i.e.:

    .panel-button {
        -natural-hpadding: 12px;

could become

    .panel-button {
        -natural-hpadding: 6px;

to change the padding to 6 pixels. If you change this below 6 pixels, you will also have to modify the `-minimum-hpadding` value to accommodate it.

However this will be lost every time you change themes, upgrade gnome-shell, etc.

## Developers

Branches are as follows:

* 'default' branch is for development.
* 'gnome3.2' branch is for GNOME 3.2. Configure it by editing `extension.js`.
* 'gnome3.4' branch is for GNOME 3.4+ (3.6-3.12) Configure using `gnome-shell-extension-prefs`.
* 'gnome3.10+' branch is for GNOME 3.10+ (3.10-3.12) Configure using `gnome-shell-extension-prefs`. On top of the gnome3.4 branch it also lets you set the horizontal padding of the "aggregate menu" button.
* 'stable' branch: **obsolete** (renamed to 'gnome3.2').

