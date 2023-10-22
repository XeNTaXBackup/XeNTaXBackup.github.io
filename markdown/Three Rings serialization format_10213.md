## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-09T21:07:06+00:00
- Post Title: Three Rings serialization format?

I received some samples for an online game called Spiral Knights.
It's developed by threerings and it's probably using one of their frameworks

[https://www.threerings.net/code/](https://www.threerings.net/code/)

The format is not hard; it's just that it come with a LOT of other data like package imports and other things.
Anyone know if the format is documented anywhere?

Samples: [http://www.mediafire.com/download.php?24vieipjqbr8i1o](http://www.mediafire.com/download.php?24vieipjqbr8i1o)

The files are zip compressed you can offzip them.
I could always hardcode case-checks but it's kind of annoying.
[3ring.JPG](https://xentaxbackup.github.io/file/6254_3ring.JPG)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-09T22:24:06+00:00
- Post Title: Three Rings serialization format?

i guess this is the closest thing to docs
the model classes
[http://clyde.googlecode.com/svn/trunk/s ... ngl/model/](http://clyde.googlecode.com/svn/trunk/src/main/java/com/threerings/opengl/model/)

and

[http://www.threerings.net/code/clyde/docs/api/](http://www.threerings.net/code/clyde/docs/api/)

mesh exporter made in max script.

[https://github.com/threerings/clyde/tre ... rc/main/ms](https://github.com/threerings/clyde/tree/master/src/main/ms)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-10T01:09:31+00:00
- Post Title: Three Rings serialization format?

The serialization is kind of boring there's probably a specific way to read each node or something.
