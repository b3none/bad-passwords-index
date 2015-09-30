## What this is

This is a compiled index of common passwords. It's intended for service providers that want to improve their users' passwords without relying on frustrating password requirements like, "6 to 16 characters, capital letter, lowercase letter, number, and symbol..."

The index contains roughly 161,000 unique passwords accounting for almost 45% of a database dump of 10 million passwords. For more background information, including a description of the approach used to generate the index, see [the writeup on my personal site](http://www.robsheldon.com/index-of-bad-passwords/). The index file is only 1MB and the most common passwords are sorted near the top of the file, so searching against it should be fast in most cases and not require much system memory.

The index file is generated by a program that packs many different common passwords into a small amount of disk space using substring matching and concatenation.


## How to use the bad password index

Convert your user's password to lowercase and do a simple string search against the index. No regular expressions are necessary. If there's a match, the user's password is too common. If there isn't a match, your user's password might still be common, but at least it won't be among the most common 161,000 passwords, so if you're storing your users' passwords with a strong hashing scheme (like you should be) then they should be a little better protected against attempts to brute force their password.

There are no fancypants libraries, frameworks, or nonsense required. Use your favorite language with the index, I don't care what it is. ...unless you like XML. If you like XML, I'm judging you.


## Sources

For the first version of this file, the only source is [a security researcher's dump of 10 million usernames and passwords](http://techcrunch.com/2015/02/10/a-security-researcher-just-dumped-10-million-real-passwords/). However, I plan to add more sources to the index, which I may or may not already have depending on the legal liabilities I am subject to.


## Updates

I will infrequently update this index with passwords from new sources and as I improve the packing algorithm. I think I'm pretty close to having an optimal packing algorithm though; I can probably only get another percentage point or two of unique passwords stuffed into a 1MB file.


## License

I am [Unlicensing](http://unlicense.org/) this file. You may use it or modify it for any purpose. I disclaim all copyrights for it. I do not require attribution or credit. Have fun, write code. See the UNLICENSE file for the nitty-gritty legalese.