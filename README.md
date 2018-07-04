# Keyro

A multilingual virtual keyboard layout based on QWERTY.

## About

Keyro brings together the QWERTY layout and the Colemak multilingual layout.

### US International (dead keys)

The [US International](https://en.wikipedia.org/wiki/QWERTY#US-International) layout enables a multilingual layout that can be accessed holding `AltGr` but it also enables dead keys.  
When a character is not present in the `AltGr` layer, dead keys must be used instead.

In order to insert `è` you have to tap `` ` `` and than press down `e`;  
In order to insert `'` you have to tap `'` and than press down the space bar.

> Dead keys can be annoying since they don't register immediately the key.

### Colemak (AltGr dead keys)

The [Colemak](https://en.wikipedia.org/wiki/Colemak) layout enables ergonomic dead keys only when `AltGr` is held down.

In order to insert `è` you have to hold down `AltGr`, tap `r` (grave accent), release `AltGr` and then press down `e`;  
In order to insert `'` you can just press down `'`.

> `AltGr` dead keys leave the default layer unchanged.

### Keyro (AltGr dead keys)

The Keyro layout uses the Colemak multilingual layout but arranged in a QWERTY layout.  

> You can learn it in one hour.

## Layout

The most common dead keys (e.g. diaeresis, grave, acute, circumflex, tilde) are on the left side of the keyboard therefore easily accessible while holding the `AltGr` key.

![layout](https://github.com/i5ar/keyro/blob/master/layout/keyboard-layout.jpg "Layout")

`AltGr` dead keys:

- **D**iaeresis (`AltGr` + `d`);
- g**R**ave (`AltGr` + `r`);
- acu**T**e (`AltGr` + `t`);
- circumfle**X** (`AltGr` + `x`);
- etc.

See [Colemak multilingual layout](https://colemak.com/Multilingual) for the complete list or use your imagination.


## Installations

### Windows setup

Download the archive from the releases page, extract and run the setup as administrator.  
Restart the system and enjoy.

### Mac OS X

See [Mac OS X layout](#mac-os-x-layout)

### X.Org Server 7.0 or later

Copy the keymap file into the `symbols` directory (e.g. `/usr/share/X11/xkb/symbols/`):

```
cd keyro
sudo cp xorg/keyro /usr/share/X11/xkb/symbols/keyro  # or different directory

```

Use the `setxkbmap` command to switch layout:

```
setxkbmap -layout keyro -v && xset r 66

# test it
setxkbmap -print -verbose 10

# switch back to QWERTY
setxkbmap us; xset -r 66

```

Check the configuration file `/etc/locale.conf`.

In order to use the [`localectl`](https://docs.fedoraproject.org/f26/system-administrators-guide/basic-system-configuration/System_Locale_and_Keyboard_Configuration.html) command you must configure the Linux console as well (e.g. `/usr/lib/kbd/keymaps`):

```
localectl --no-convert set-x11-keymap keyro

# test it
localectl status

```

### Linux console

Copy the keymap file into the `keymaps` directory (e.g `/usr/lib/kbd/keymaps`) and gunzip it.  
Restart the system so your layout will be listed by the `localectl list-keymaps` command.  
Check the configuration file `/etc/vconsole.conf`.

See [`loadkeys`](https://wiki.archlinux.org/index.php/Keyboard_configuration_in_console) for more info.


## Contributions

Feedback and pull requests are welcome.

Unicode characters can be easily found in [Graphemica](http://graphemica.com).

### Windows layout

Use [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339).

### Mac OS X layout

Use [Ukelele](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele).

## TODO

- Add FreeBSD keyboard layout;
- Add Mac OS X keyboard layout;
- Add missing characters to the Windows layout.
