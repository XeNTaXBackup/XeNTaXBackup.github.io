## Post #1
- Username: myers
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 26, 2010 12:52 am
- Post datetime: 2015-01-14T21:21:09+00:00
- Post Title: Compression?

Hi guys!
I need some help, I'm trying for day now, but without any luck... the truth is I'm totally stupid at this compression/encrypton yet.
It should contains five strings: FIRST SECOND THIRD FOURTH FIFTH



Thats all what I've found out:
Red part: how many elements
An element is 12 byte: id, offset (decompressed?), length (also decompressed?), and something at the end
Blue part: elements of 4 bytes after that. Maybe some offsets or lengths too? Some other part of the original file can be more elements (higher and higher), and always the last one is the length of the Green part.
Green part: compressed data I think 

Of course I've attached the file also (its cutted out from a bigger file, but its sure there is no anything useful for this part).
Yeah, and the game is Xenus 2/Precursors .qrc file. We have an editor for this, but its too old for Precursors, and it can't handle some important part of the file.

Thanks, I hope somebody can help me!
[five.zip](https://xentaxbackup.github.io/file/8478_five.zip)
## Post #2
- Username: myers
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 26, 2010 12:52 am
- Post datetime: 2015-07-26T11:42:34+00:00
- Post Title: Compression?

Anybody could help with this? I'm still stucked
## Post #3
- Username: heksesang
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 17, 2014 10:12 pm
- Post datetime: 2015-08-16T03:06:26+00:00
- Post Title: Compression?

Do you have more samples? I can try help you out, but it's hard to work on just this one little sample, as you can't really spot the patterns.
## Post #4
- Username: myers
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 26, 2010 12:52 am
- Post datetime: 2015-09-06T07:04:08+00:00
- Post Title: Compression?

Thanks heksesang!

I've included a resource file, it contains 5 strings (the last one with another info -comment, sound file, etc... - , you can see it on the picture how does it looks like).

[http://postimg.org/image/ar8u68nbx/](http://postimg.org/image/ar8u68nbx/)

edit: I've changed the img to an url, because it was big.
[RESOURCE.7z](https://xentaxbackup.github.io/file/9686_RESOURCE.7z)
## Post #5
- Username: heksesang
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 17, 2014 10:12 pm
- Post datetime: 2015-12-29T09:22:13+00:00
- Post Title: Compression?

> Reply from myers
>
> Thanks heksesang!

I've included a resource file, it contains 5 strings (the last one with another info -comment, sound file, etc... - , you can see it on the picture how does it looks like).

http://postimg.org/image/ar8u68nbx/

edit: I've changed the img to an url, because it was big.
Sorry for the slow response, gonna have a look at the file and see if I can figure anything out.

Seems to be 12 strings in the resource file you posted?

EDIT: Seems to be two entries for each string in the table. So 12 entries for 6 strings.
## Post #6
- Username: heksesang
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 17, 2014 10:12 pm
- Post datetime: 2015-12-29T12:45:14+00:00
- Post Title: Compression?

This is the current 010 template I have for the file:
[https://gist.github.com/heksesang/191a64e70e7effaa572b](https://gist.github.com/heksesang/191a64e70e7effaa572b)

The ZRes signature made me think it could be zlib, but so far I haven't been able to inflate the data, so I am guessing it's something else.

To figure out what parts of the file are flags and what they mean, it would be a good idea to make changes to each of the flags in that editor and make resource files for the different combinations of flags (but with otherwise the same string data). That way we could compare the files and see what parts changes.
