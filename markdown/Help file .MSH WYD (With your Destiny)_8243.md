## Post #1
- Username: maloko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 10, 2012 10:42 am
- Post datetime: 2012-02-10T03:13:02+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T05:47:25+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

Four things:

1: if it doesn't load, open the debug log and look at what the vertSize is. I think I captured most of them.
2: I didn't add multiple model loading. Well, that's not very useful until you get the materials loaded anyways.
3: Some of the faces are supposed to be drawn backwards. I don't know how it is determined. There are only 4 unknowns in the format at this moment.
4: if someone tells me the format for the textures I'll add it

The textures are the .wys files.
They are just DDS file except they changed the part that's supposed to tell you which DXT format it uses as well as the idstring from "DDS" to their "WS10". So far it looks like "2z73" is DXT1, "7x0s" is DXT3.

I didn't want to spend more than 15 minutes on the models for tonight so here's what I wrote (noesis plugin):

[http://db.tt/iWZEC4zY](http://db.tt/iWZEC4zY)

Oh, and it doesn't have any idstrings.
I guess I *could* do something like read 8 integers and verify that they are integers and also smaller than a certain value...check that the fourth integer is one of [32, 36, 40, 44, 48], check that the first integer is 0... That might make it more unique.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T07:17:22+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

So as I mentioned, the textures are just DDS files except they decided to change the idstring and mess around with the "DXT1/3/5" part.

Though, I think I made it overcomplicated.

[http://db.tt/Sc4li3Fd](http://db.tt/Sc4li3Fd)

Anyways ok, so I also find it amusing that the guy's head loads far away from his body. Weird.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-02-15T17:27:19+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

> I guess I *could* do something like read 8 integers and verify that they are integers and also smaller than a certain value...check that the fourth integer is one of [32, 36, 40, 44, 48], check that the first integer is 0... That might make it more unique.

See the attached file. It is the unique file, because the first bytes are $FFFFFFFF. 
[bn010401.zip](https://xentaxbackup.github.io/file/5070_bn010401.zip)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T17:59:13+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

Some of them have 0 as the first integer. I think it's a flag or something.
## Post #6
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2014-08-23T08:38:49+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

But , how can i edit this textures in photoshop for example, and save back in .wys format?
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-08-23T13:37:42+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

> Reply from RonaldinhoR9
>
> But , how can i edit this textures in photoshop for example, and save back in .wys format?
I'm pretty sure you can paste in the raw dds data if you know which DXT the texture you want to replace uses
## Post #8
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2014-08-25T12:28:18+00:00
- Post Title: Help file .MSH WYD (With your Destiny)

How to use that plugins in NOESIS? Just copy/paste them inside plugins folder? Casue the files inside that plugin folder at [http://www.himeworks.com/noesis-plugins/](http://www.himeworks.com/noesis-plugins/)  aren't in .dll format.
