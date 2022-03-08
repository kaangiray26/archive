# shortcut
> _Serverless URL Redirection_

Ah the good old spam, everyone hates that for sure. Personally, the amount of spam e-mails I get for my personal e-mail address is crazy high. Almost all websites I visit daily have implemented some ways to deal with spamming, and the common way to deal with it is to add domains to blacklists, so whenever someone shares an URL directly derived from that domain, it gets filtered and hopefully removed from the website. Reddit also does some heavy spam filtering and sometimes their filters can be a bit strict. For instance, if you try to send a link to a subreddit from the `duckdns.org` domain, it will be detected as spam and will be removed most of the time.

Although I dislike spam, I also find it threatening that they force these measurements against users. After having a bad time with not being able to post some links on Reddit, I've found out that spoofing the domains is just enough to bypass domain filters. Therefore, I needed a small website to create redirecting links to banned domains but I needed it to be quick and possibly serverless, so I created a simple html file and put some javascript code in it.

Here's how it works: The idea is to use Github Pages to host a small webpage that can take an URL as an input and encode it into hex. However, the encoding part is just encrypting the URL with AES and then encoding it to Base64 and then to Hex. This is not surprising but the AES encryption does not provide any security because the private key can be read directly from the source code and making it encrypted and irreversible is not our intention here, so I can just say that the key is `e1`. After that, the encoded part is then added to to my Github Pages subdomain with the `id` parameter. Whenever the user enters the webpage, a script in the headers checks if the URL has any querystring part. If that's the case, it decodes the `hex` string and redirects the webpage to the desired webpage before the webpage loads up.

This may sound like a silly solution to a bigger problem and yes it is. Well, this could probably lead to my Github Pages subdomain getting banned but I don't believe that the `github.io` domain would be added to the domain filter. So, one can just fork my repo and then create another website to create redirection links. Let's hope Reddit doesn't prevent redirection at all.

You can check the website yourself and as always, you can find the source code down below.

* [Website](https://kgbzen.github.io/shortcut/)
* [Source Code](https://github.com/kgbzen/shortcut)

---
Feel free to [email me](mailto:kaangiray26@protonmail.com) your comments!
