# Eval GJS GNOME Shell Extension

The original extension is great, i just wanted my to use my username on shell scripts, bit selfish, I know.

As of GNOME 41, the dbus method `Eval()` is now restricted with `MetaContext:unsafe-mode` property (see this [commit](https://gitlab.gnome.org/GNOME/gnome-shell/-/merge_requests/1970/diffs?commit_id=f42df5995e08a89495e2f59a9ed89b5c03369bf8)). This extension provides unrestricted `Eval()` dbus method for running arbitrary code in the compositor.

## Features

* Run arbitrary GJS code like you would with GNOME `Eval()` dbus method.
* `Main`, `Gio`, `GLib` and `Meta` available by default.

## Installation

```sh
git clone git://github.com/cantudo/eval-gjs.git
cd eval-gjs
make install
```

## Example Usage

```sh
gdbus call \
  --session \
  --dest org.gnome.Shell \
  --object-path /dev/cantudo/EvalGjs \
  --method dev.cantudo.EvalGjs.Eval "Main.overview.show();"
```
