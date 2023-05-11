# My build of Surf v2.1
![](https://i.postimg.cc/8PCDNyVn/screenshot-20210423-017.png)

This repository hosts the source code of my build of Surf made by [Suckless software](https://surf.suckless.org/). It is based on Surf v2.1 and is mostly unpatched with the exception of two patches: one to have built-in download support and the second one for Surf to use the system clipboard. The list of applied patches can be found in the *patches* folder. It features:

* Ultra minimalist Web browser/display: no tabs, no statusbar, no plugins
* Search queries using *surfraw* (*dmenu* and *surfraw* must be installed for this work)
* Support for videos built-in if the following packages are installed: *gst-libav* & *gst-plugins-good*
* Links hinting (the file *script.js* must be placed in the folder *$HOME/.config/surf/script.js*
* Caching has been totally disabled
* Other disabled features: automatic media play, geolocation, spell checking, scroll bars, DNS prefetch
* User-Agent has been set to mimic mainstream Web browser
* Site specific custom style sheets (requires configuration in *config.def.h* and a CSS file in *$HOME/.config/surf/styles*)
* Support for the *XDG_BASE_DIRECTORY* standard: files for scripting or stylesheets will be located at *$XDG_CONFIG_HOME/surf*
* Support for dark mode if the Website has a dark mode configured

# Dependencies
The following packages are necessary in order to run this build of Surf properly:

* webkit2gtk (v4.0 or greater - necessary for compiling)
* dmenu (for text search, Web queries and URI browsing)
* surfraw (for quick Web queries)

If you want a nice DMenu to be integrated, you can install [my custom build](https://github.com/astsu777/dmenu). You can also check out [my build of ST](https://github.com/astsu777/st) for a nice terminal emulator.

# Installation
Download this repository, compile the sources and install the binaries. Type the following commands to do so:

```
git clone --depth 1 https://github.com/astsu777/surf.git
cd surf
sudo make clean install
```

<u>**Note**</u>: this Surf installation is automated when installing an X environment with my [bootstrap script](https://github.com/astsu777/bootstrap).

# Usage
The Surf Web browser is not really meant to browse the modern Web properly: it lacks so many features that any multimedia Web sites would break. However, this program is very light on system resources and is well suited to read text/documentation for example.

To use it, execute *surf* followed by an URL. For example, to open DuckDuckGo with Surf, type:

If you use a login manager (such as *lightdm*), make sure to create a *dwm.desktop* file in */usr/share/xsessions/*. The file should contain the following:

```
surf https://duckduckgo.com
```

<u>Note</u>: the *http(s)://* part is optional

# Key Bindings
I configured the key bindings that I like. They are all configured in the *config.def.h* file. Here is the full list and what they actually do:

* **MODKEY** has been configured to be the Control key

| Key binding | Action |
| :--- | :--- |
| `MODKEY + o` | open provided URL in current window |
| `MODKEY + /` | search text on the page |
| `MODKEY + n` | go to the next search match (downwards) |
| `MODKEY + s` | search query using *surfraw* |
| `MODKEY + f` | enable link hinting and open link in current window |
| `MODKEY + SHIFT + f` | enable link hinting and open link in a new window |
| `MODKEY + c` | cancel link hinting |
| `MODKEY + SHIFT + n` | go to the previous search match (upwards) |
| `Escape (or MODKEY + c` | stop loading the Web page |
| `MODKEY + r` | reload the page |
| `MODKEY + SHIFT + r` | reload the page and bypass the cache |
| `MODKEY + SHIFT + l` | browse forward to the next page |
| `MODKEY + SHIFT + h` | browse backwards to the previous page |
| `MODKEY + h` | scroll left on the page |
| `MODKEY + j` | scroll down on the page |
| `MODKEY + k` | scroll up on the page |
| `MODKEY + l` | scroll right on the page |
| `MODKEY + b` | step up on the page |
| `MODKEY + space` | step down on the page |
| `MODKEY + SHIFT + j` | zoom out |
| `MODKEY + SHIFT + k` | zoom in |
| `MODKEY + SHIFT + q` | zoom reset (100%) |
| `MODKEY + y` | copy URL to the clipboard |
| `MODKEY + p` | browsed to the copied URL in the clipboard |
| `MODKEY + SHIFT + p` | print the current page |
| `F11` | toggles full screen |
| `MODKEY + SHIFT + o` | toggles the Web inspector |
| `MODKEY + SHIFT + a` | toggles the cookie policy |
| `MODKEY + SHIFT + c` | toggles caret browsing |
| `MODKEY + SHIFT + f` | toggles frame flattening |
| `MODKEY + SHIFT + s` | toggles JavaScript |
| `MODKEY + SHIFT + i` | toggles the load of images |
| `MODKEY + SHIFT + v` | toggles plugins |
| `MODKEY + SHIFT + b` | toggles scroll bars |
| `MODKEY + SHIFT + m` | toggles custom stylesheets |
| `MODKEY + SHIFT + d` | toggles dark mode support |

# Contact
You can always reach out to me:

* [Twitter](https://twitter.com/astsu777)
* [Email](mailto:gaetan@ictpourtous.com)
