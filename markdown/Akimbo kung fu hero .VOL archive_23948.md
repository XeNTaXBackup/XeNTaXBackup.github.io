## Post #1
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-26T00:23:15+00:00
- Post Title: Akimbo kung fu hero .VOL archive

Hi
I'm looking someone who could make simple Tool to have ability to extract and replace files.
Magic numbers 56 46 - VF.
I uploaded smaller archive which contains menu files: background etc because archive with game assets is 356MB.
Thanks for any help.

Link:
[https://www.mediafire.com/file/7k2zv4p2 ... ge.7z/file](https://www.mediafire.com/file/7k2zv4p2v3qavwe/Language.7z/file)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-26T06:16:33+00:00
- Post Title: Akimbo kung fu hero .VOL archive

Game extractor can be used to extract files.
If you want to replace them, you can also use offzip [https://aluigi.altervista.org/mytoolz.htm#offzip](https://aluigi.altervista.org/mytoolz.htm#offzip)


There is also specification for this file format on the wiki
[http://wiki.xentax.com/index.php/Excessive_Speed_VOL](http://wiki.xentax.com/index.php/Excessive_Speed_VOL)
## Post #3
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-26T13:06:01+00:00
- Post Title: Akimbo kung fu hero .VOL archive

Thanks for reply.
I know that Game Extractor can extract files, but they are "Unnamed File XXX". I know that file names are in .VOL.

How can I replace file in offzip? Example?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-26T13:15:57+00:00
- Post Title: Akimbo kung fu hero .VOL archive

> How can I replace file in offzip? Example?

You have some examples in the tool usage information. You should use "-r" option for that.

```
  scan zlib        offzip -S input.dat
  scan offset      offzip -S input.dat 0 0x12345678
  cool scan zlib   offzip -S -x -Q input.dat
  extract zlib     offzip -a input.dat c:\output
  extract deflate  offzip -a -z -15 -Q input.dat c:\output
  reimport zlib    offzip -a -r file.dat c:\input
```


> I know that file names are in .VOL.
According to the file format specification there are no filenames.
## Post #5
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-05-27T19:10:51+00:00
- Post Title: Akimbo kung fu hero .VOL archive

I have this Tool which was made by alcexhim (thanks for that) but only extract option is supported.

[https://imgur.com/iCO4zEY](https://imgur.com/iCO4zEY)

In archive there are: tool and txt file which contains old source of VOL and probably newer source of VOL format (under - symbols). Btw if someone will be able to compile for windows new app (I mean full app from github from txt file), could post here. I tried in visual studio and I had 100+ errors. ;/ I don't have skills to write own app.

Thanks
[chaosworks.zip](https://xentaxbackup.github.io/file/20218_chaosworks.zip)
