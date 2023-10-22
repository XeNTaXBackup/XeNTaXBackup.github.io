## Post #1
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-09-28T13:19:52+00:00
- Post Title: Help with this compressed one.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-09-29T20:36:52+00:00
- Post Title: Help with this compressed one.

Just from a quick glance:

```
// for each file (until archive ends)
  byte {1}     - name length
  char {x}     - name
  uint32 {4}   - file size
  byte {x}     - file data

```

I don't see any archive-level compression. I'm sure somebody can write you a Mexscript for this ...
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-09-30T15:09:50+00:00
- Post Title: Help with this compressed one.

well...i tried with jaedernaub ripper and it didnt found any real png gfx,so i tought about compressed?!

greets.
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-09-30T15:15:08+00:00
- Post Title: Help with this compressed one.

I haven't tried to apply Jaeder Naub, but at I could at least extract the first file manually and open it with my graphics software without any problems.
## Post #5
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-10-04T16:33:06+00:00
- Post Title: Help with this compressed one.

well..i tried to cut the file with png header and cant open it.

well,no offense to your knowledge,i've reading many posts from you and you're much more than me in reverse,i do something wrong?!

well,of your replies,it's not compressed and therefor nothing custom.

thanks to look at.
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-10-05T13:53:19+00:00
- Post Title: Help with this compressed one.

Oh, no offense taken. You have every right to doubt me.

As I don't know which image viewer you use, I can't guess where the problem might be. The PNG files can definitively be opened with XnView as well as Corel Photo-Paint 10 (see attachment). I've whipped up a crude [extractor](http://www.xentax.com/uploads/author/denizoezmen/_LIBExt.zip); you can compare your results with those produced by this program.

Intersting side note: The first byte indeed seems to a file counter. However, there are still bytes left in the sample .lib file after extracting its content. I've got no idea what these are used for ...
[mainmenu.jpg](https://xentaxbackup.github.io/file/1348_mainmenu.jpg)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-10-08T15:28:51+00:00
- Post Title: Help with this compressed one.

work like a charm despite i'm never been able to open the big file into a viewer..well my main problem was to extract all png and you do another great toy for me!

greets!

like said someone,if I could do it, I would do it!
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-10-12T13:02:21+00:00
- Post Title: Help with this compressed one.

You're welcome; have fun!
