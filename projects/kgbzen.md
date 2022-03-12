# KGBZEN
> _My personal website_

kgbzen.github.io, the page you're now viewing, is a handmade blog project written from scratch. You may have seen my other project `nephila` here, it shares the same goal but was bloated with lots of extra steps such as running a python script every time etc. This particular approach is much better in terms of ease of usability.

The website is divided into two parts, one is the website viewer and the second is the content management. Let's start with the second part.

Actually, no content is hosted on the website itself, instead I use a [public github repo](https://github.com/kgbzen/archive) where I keep the images, json files and markdown files of my posts.

There are two types of posts here; project and blog posts. Each post is actually a markdown file stored in the repo and there is a json file where it keeps track of the post title, description, datetime and the url of the markdown file. This way, the website gets the json file and loads up the content and creates the clickable list elements you see on the webpage dynamically.

Whenever you click on a list element on the webpage, the browser gets the specified markdown file and converts it to html using the javascript library [Showdown](https://github.com/showdownjs/showdown). After that, the style gets applied to the converted html and displayed on the website.

So, to add a new post, I just have to commit the markdown file to the repo and update the json file and the rest is instant, because there is no deployment happening to the github pages, it's static!

Ok, I feel like I have to explain some little details about the website as well. You must have seen those little colored blocks in the left side of list items. Those are actually generated on the run by a little server I've created and hosted by Heroku. If you inspect the html, you'll see that those blocks are just images with their sources pointed to the same address. With each request, the server generates a random 5x5 square block using [Python Imaging Library](https://pillow.readthedocs.io/en/stable/). In the blog section, it does the same thing but this time there is also a hex value passed to the server to create custom colored blocks. If you think about it, it's a little bit silly to do it this way, because on each reload the server would be flooded with requests demanding new block images. I don't know why I haven't just tried to let the browser handle that :)

The same server also sends back some random phrases I've uploaded and if you reload the homepage, you will sometimes get random phrases under the main title of the website.

There is also a `manifest.json` and a pseudo-serviceworker on the webpage that lets you `install` the website to your homescreen on your mobile device and use as a progressive web app (PWA). That's all!

You can check the website yourself and as always, you can find the source code down below.

* [Website](https://kgbzen.github.io/)
* [Source Code](https://github.com/kgbzen/kgbzen.github.io)

---
Feel free to [email me](mailto:kaangiray26@protonmail.com) your comments!
