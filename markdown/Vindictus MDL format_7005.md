## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-18T15:51:37+00:00
- Post Title: Vindictus MDL format

Homepage: [http://vindictus.nexon.net/](http://vindictus.nexon.net/)



I've been looking at vindictus for some time and have been using mdldecompiler to export the mdl's to smd format, but then they have their security system which constantly prevents me from loading up the decompiler.

So I figured it'd be easier to just write a parser for the MDL format since [it's well-documented anyways](http://developer.valvesoftware.com/wiki/MDL)

I've gotten the basic geometry, but the materials are still ???
Has anyone written a parser for the MDL format?

I can't seem to figure out how materials are assigned lol

Some simple models (ie: just items and stuff)
[vindictus.rar](https://xentaxbackup.github.io/file/4504_vindictus.rar)
## Post #2
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-07-18T18:46:20+00:00
- Post Title: Vindictus MDL format

What's wrong? MDLDecompiler successfully make SMD from yours MDL-files. Example: 
[](http://xmages.net/show.php/2973961_barbecue-set-jpg.html)
## Post #3
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-07-18T23:24:43+00:00
- Post Title: Vindictus MDL format

You just need to strip the comp extension from the files
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-18T23:38:12+00:00
- Post Title: Vindictus MDL format

> Reply from Nazaroff
>
> What's wrong? MDLDecompiler successfully make SMD from yours MDL-files. Example:

There's nothing wrong. MDL Decompiler works fine, but having to do it one at a time is too bothersome.
