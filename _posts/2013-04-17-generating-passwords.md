---
title: Generating Passwords
layout: news
excerpt: Howto use passwords as hash salts to generate site-specific passwords without the need to remember them.
---

So, here is the problem:

1. Sites we use are going to get hacked and have their password databases stolen. Yes, they *should* be salted + hashed, but even that can be broken.

Thus most people recommend we use different passwords for different sites. This causes us to run straight into the next problem.

2. Passwords are hard to remember.

Even if you use some form of phrasal approach as suggested by [XKCD](http://xkcd.com/936/), that's still a lot of phrases. A solution is to write them all down, either on a simple piece of paper[^1], in a pgp encrypted file or a password manager (either an app or online)[^2].

I use (for at least some of my passwords) a different approach; built around the mathematical property of hashing algorithms that they are one-way[^3]. I use this by hashing a master password with the sitename to generate each site's password. This means I can have a single password, but each site has a different one *and* even if a site is comprimised *and* they happen to know the system I use, it is still intractable for them to figure out any of my other passwords.

An initial example:

````
#!/bin/sh
echo $1$2 | md5sum | cut -b 1-8
````
This script takes two parameters, passes them into md5sum and returns the first 8 characters of the response.
The first parameter should be your master password, the second the password identifier (e.g. yahoo).

This works (and is pretty similar to what I used to use), but can be improved upon. I will come back to this to talk about the limitations of this approach and how you can get around it.
[^1]: Not that crazy an idea, if you believe that your online and physical security are seperate problems; which they mostly will be if you are not getting targetting specifically. However, I still think it is a bad idea.
[^2]: [Lifehacker](http://lifehacker.com/5529133/five-best-password-managers) did a good round-up of some of the better ones.
[^3]: I'm not going to explain in detail, but basically calculating the hash from a value is easy. Calculating the value from the hash is difficult / impossible.
