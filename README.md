# i3lock-fancy-multimonitor
The idea for this project was shamelessly copied from [meskarune](https://github.com/meskarune)'s [i3lock-fancy](https://github.com/meskarune/i3lock-fancy).

It uses [scrot](http://freecode.com/projects/scrot) to take a screenshot of the desktop, then [ImageMagick](http://www.imagemagick.org/) blurs the image and adds a lock icon and text.

By using information from [xrandr](http://www.x.org/wiki/Projects/XRandR/) and basic math, this script supports multiple monitor setups, displaying the icon and text centered on all screens.

The lock icon is different from the original project, with a transparent black circle around it. The text is also an image, making it easier to customize (and to put it at the correct position). Finally, it uses vanilla [i3lock](https://github.com/i3/i3lock) instead of [i3lock-color](https://github.com/eBrnd/i3lock-color). The author of i3lock-color [is not maintaining it anymore](https://github.com/eBrnd/i3lock-color/issues/6). If you want to customize the colors of i3lock, the recommended version of i3lock-color is [this one](https://github.com/Arcaena/i3lock-color), maintained by [Chris Guillott](https://github.com/Arcaena).

## Installation
Make sure you have all the dependencies:

```
sudo apt-get install scrot imagemagick i3lock
```

Copy the `lock` script along with the images to some place on your system (e.g.: the i3 folder) and give it execution permission:

```
git clone https://github.com/guimeira/i3lock-fancy-multimonitor.git
cp -r i3lock-fancy-multimonitor ~/.i3
chmod +x ~/.i3/i3lock-fancy-multimonitor/lock
```

Create a key binding on your i3 config file (in this example I'm using $mod+p):

```
echo "bindsym \$mod+p exec /home/<your username>/.i3/i3lock-fancy-multimonitor/lock" >> ~/.i3/config
```

Now reload the i3 configuration file. By default, the key binding is `$mod+Shift+c`.
