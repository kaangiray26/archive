# KGBAPI
> _A little API_

You may be wondering about the random bitmap icons on the projects and blog page of this website. They are not images that are saved somewhere in a storage. Actually, those images are created upon a request to my little API server. The API server is just a simple Flask server deployed on Heroku, which uses the [Pillow](https://python-pillow.org/) library to do some image operations. Those splash texts on the landing page of my website is also returned from the API server. Well, there is not much to it actually. However, you can check the code, make some changes to it and directly deploy it on Heroku yourself.

There are just 3 endpoints right now:
* `/splash`
* `/square`
* `/square/<hex>`

The first one just returns a random splash text from a local file.

The second one creates a random 5x5 bitmap icon with a pre-defined color.

With the third one you can create the same 5x5 bitmap icon but here you can also set the option for the color of the blocks.

You can check the website yourself and as always, you can find the source code down below.

* [Website](https://kgbapi.herokuapp.com/)
* [Source Code](https://github.com/kgbzen/kgbapi)

---
Feel free to [email me](mailto:kaangiray26@protonmail.com) your comments!