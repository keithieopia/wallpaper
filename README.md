# ~/bin/wallpaper

> The calmer and more well-ordered my desktop is, the more I can convince myself I'm on top of things.
>
> -- Steven Hall

Various scripts that set dynamically changing desktop wallpapers.

- [change-wallpaper](#change-wallpaper)
- [color-wallpaper](#color-wallpaper)
- [fortune-wallpaper](#fortune-wallpaper)
- [natgeo-wallpaper](#natgeo-wallpaper)
- [rand-wallpaper](#rand-wallpaper)
- [sunlight-wallpaper](#sunlight-wallpaper)
- [weather-wallpaper](#weather-wallpaper)
- *[Installing / Running on Login](#installing)*

### change-wallpaper
<a name="change-wallpaper"></a>
Detects the running Desktop Environment and runs the appropriate command to change the wallpaper to a given file. Most of the wallpaper scripts call this script if it's available and fallback to built-in GNOME support.

Currently supports KDE/Plasma and most GNOME/GTK+ based DEs that support the [GSettings](https://developer.gnome.org/gio/stable/GSettings.html) tool. Example of GSettings DEs are: [Budgie](https://solus-project.com/budgie/), [Cinnamon](http://developer.linuxmint.com/projects.html), [GNOME](https://www.gnome.org/), [MATE](https://mate-desktop.org/), [Unity](http://unity.ubuntu.com/), and [Yunit](https://yunit.io/).

It would probably be easy to port this script to use something like `feh` or `xsetbg` for window managers like i3, bspwm, openbox, etc.

### color-wallpaper
<a name="color-wallpaper"></a>
Sets the desktop to a random color. Amusingly, the simplest way I found to do this is by using `openssl`. Not many wallpaper setters can boast they generate colors securely! Please report vulnerabilities to the [Snake](http://www.philzimmermann.com/EN/essays/SnakeOil.html) [Oil](https://www.schneier.com/crypto-gram/archives/1999/0215.html#snakeoil) [Security](http://www.interhack.net/people/cmcurtin/snake-oil-faq.html) tracker.  

*Public Domain (This overrides the repo-wide MIT License)*

#### Screenshots
|  #1  |  #2  |  #3  |  #4  |
| ---- | ---- | ---- | ---- |
| [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color1-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color1.jpg) | [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color2-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color2.jpg) | [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color3-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color3.jpg) | [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color4-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-color4.jpg) |

---

## fortune-wallpaper
<a name="fortune-wallpaper"></a>
Sets the wallpaper to a random quote generated by the ubiquitous `fortune-mod`. Only short quotes are use for space reasons.

*MIT License*

#### Screenshots
|  #1  |  #2  |
| ---- | ---- |
| [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-fortune1-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-fortune1.jpg) | [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-fortune2-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-fortune2.jpg) |

---

### natgeo-wallpaper
<a name="natgeo-wallpaper"></a>
Downloads and sets the wallpaper to National Geographic's [Photo of the Day](http://www.nationalgeographic.com/photography/photo-of-the-day/). The aspect ratio for the photos is unsuitable for HD monitors, so the script stretches and blurs a copy in the background to prevent ugly system colored bars typical with scaled wallpapers.  

#### Screenshots
|  #1  |  #2  |
| ---- | ---- |
| [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-natgeo1-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-natgeo1.jpg) | [ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-natgeo2-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-natgeo2.jpg) |

**NOTE:** *Photos used in the screenshot are copyrighted by National Geographic. They are used for demonstrative purposes only and I make no claims to them*

---

### rand-wallpaper
<a name="rand-wallpaper"></a>
Downloads and sets a random wallpaper from [Desktoppr](https://www.desktoppr.co/) using its API. Obviously, the results of running this are random: you have been warned. Wallpapers are submitted by users, but only high resolution wallpapers are allowed.

---

### sunlight-wallpaper
<a name="sunlight-wallpaper"></a>
A overlay that shows which parts of the world currently lit by sunlight and the daily clouds as seen from various satellites in orbit. I do none of the hard work and this is all thanks to die.net's [World Sunlight Map](https://www.die.net/earth/) and Xplanet's [Real Time Cloud Map](http://xplanet.sourceforge.net/clouds.php).

*Public Domain (This overrides the repo-wide MIT License)*  

#### Screenshot
[ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-sunlight-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-sunlight.jpg)

---

### weather-wallpaper
<a name="weather-wallpaper"></a>
Current doppler weather radar for the contiguous U.S. The screenshot is deceptive as the wallpaper is actually animated; in a way you would expect from a weather radar. There is a brief pause between frames of the animation so that the animation isn't too distracting.

#### Screenshot
[ ![](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-weather-thumb.jpg) ](https://raw.githubusercontent.com/keithieopia/wallpaper/master/.readme-assets/wallpaper-weather.jpg)


## Installing / Running on Login
<a name="installing"></a>
Create a [Desktop Entry](https://specifications.freedesktop.org/desktop-entry-spec/desktop-entry-spec-latest.html) file in *~/.config/autostart/* (you may need to create the folder) or */etc/xdg/autostart* if you want it to start for all users.

`~/.config/autostart/wallpaper.desktop`

```desktop
[Desktop Entry]
Name=Wallpaper
Comment=Sets the desktop wallpaper
Exec=bash -c '$HOME/bin/wallpaper/natgeo-wallpaper'
Terminal=false
Type=Application
X-GNOME-Autostart-enabled=true
```

**NOTE**: Change the *Exec=* to the path of the wallpaper script you want to use

## Feedback
I would love your feedback! If you found any of these wallpaper scripts
useful, please send me [an email](mailto:timothykeith@gmail.com). For
the privacy conscious, feel free to encrypt any messages using my
[PGP key](https://gist.githubusercontent.com/keithieopia/434f3575ec1f020d6589a4c01dc0847e/raw/2e0749f2966ff501ee28797a926229c081f7e652/timothykeith.pub.asc):

> 46E6 9F69 90C1 DE8C 9791 88EE 94A4 E2D4 *6B32 AA11*

To import it into your keyring:
```console
$ curl https://gist.githubusercontent.com/keithieopia/434f3575ec1f020d6589a4c01dc0847e/raw/2e0749f2966ff501ee28797a926229c081f7e652/timothykeith.pub.asc | gpg --import -
```

**NOTE:** SKS Public Key Servers (such as pgp.mit.edu) don't support
Curve25519 keys yet. In the meantime, consider using
[Keybase.io](https://keybase.io/); my username is [timothykeith](https://keybase.io/timothykeith).


### Bug Reports
Submit bug reports via GitHub's [Issue Tracker](https://github.com/keithieopia/wallpaper/issues)


## Author
Copyright &copy; 2016 - 2019 Timothy Keith, except where otherwise noted.

Licensed under the [MIT license](https://github.com/keithieopia/wallpaper/blob/master/LICENSE).

*This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.*
