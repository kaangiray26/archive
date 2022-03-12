# Easy Click
> _Use Your Keyboard To Simulate Mouse Clicks_

Have you ever been frustrated about not being able to draw properly using your laptop's touchpad? Touchpads are usually small and hard to use for anything else other than just navigation. Imagine you're trying to draw something with your favourite open-source painting program. You have to press down on your touchpad all the time to actually keep drawing. Now, this creates a problem because whenever you're pressing really hard it's much harder to move your finger because of the friction.

To fix this problem (temporarily), I've created a small python script to simulate mouse clicks using your hardware keyboard. The script uses the `pynput` module to create an event listener that waits for the execution of certain keys. To simulate events, it uses `xdotool`, which is a X11 automation tool, available in many distrubitions. Now, you can use your touchpad for drawing without actually using any force to press on the pad.

Here is a comparison:

| Without Easy-Click | With Easy-Click |
| ------------------ | --------------- |
| ![Without Easy-Click](https://raw.githubusercontent.com/kgbzen/easy-click/master/images/no-easy-click.png) | ![With Easy-Click](https://raw.githubusercontent.com/kgbzen/easy-click/master/images/easy-click.png) |

> _Notice how it looks more curly and natural with Easy-Click. And no, I didn't make the first one bad intentionally._

To use it, just start `easy-click` by running the command easy-click. This will shrink the terminal window and put it in the bottom right corner of your screen. If it says `Mode:On`, then the event listener should be running. The window will move itself out of the way if you need to click something underneath the terminal window.

Here's the default layout:

| Layout |
| ------ |
| ![Layout](https://raw.githubusercontent.com/kgbzen/easy-click/master/images/layout.png) |

You can check the latest release yourself and as always, you can find the source code down below.

* [Website](https://github.com/kgbzen/easy-click/releases)
* [Source Code](https://github.com/kgbzen/easy-click)

---
Feel free to [email me](mailto:kaangiray26@protonmail.com) your comments!
