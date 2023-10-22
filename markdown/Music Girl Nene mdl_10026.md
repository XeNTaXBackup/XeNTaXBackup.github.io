## Post #1
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2013-01-09T07:43:17+00:00
- Post Title: Music Girl Nene mdl

website : [http://www.mg-nene.com/](http://www.mg-nene.com/)
it's a free ipod game,

they use a same format with mg miku [viewtopic.php?f=16&t=9541](http://forum.xentax.com/viewtopic.php?f=16&t=9541)
but there is problem with the body and face (the body rip perfectly but the hands are perfectly broken)
and another mdl files (like stage and the face) the finale00 noesis script didn't work for that

maybe some cool senior here can edited it a little bit ?

here is the sample 

[http://www.mediafire.com/?9q8awn716hm6onh](http://www.mediafire.com/?9q8awn716hm6onh)

and someone in da already ripped it [http://xdonotenterx.deviantart.com/art/ ... popular%20](http://xdonotenterx.deviantart.com/art/Music-Girl-Nene-340724288?q=boost%3Apopular%20)((nene)%20AND%20(by%3Axdonotenterx))&qo=2
[http://xdonotenterx.deviantart.com/art/ ... popular%20](http://xdonotenterx.deviantart.com/art/For-the-Love-of-nene-341224327?q=boost%3Apopular%20)((nene)%20AND%20(by%3Axdonotenterx))&qo=1

and he didn't distribute the script..


thank you
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-09T20:49:28+00:00
- Post Title: Music Girl Nene mdl

no offense, but did you try searching this site?

there's a topic about half a page down about the MusicGirl games.
## Post #3
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2013-01-10T07:27:01+00:00
- Post Title: Music Girl Nene mdl

yeap i did,but only music girl miku
they almost got a same format,

here what have i got when i trying to rip from musicgirl nene with music girl miku noesis plugin

(can someone edit the script somehow ?)

*and thank you for interested in my problem
[nene.png](https://xentaxbackup.github.io/file/6124_nene.png)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-10T11:29:00+00:00
- Post Title: Music Girl Nene mdl

that is the model. the extra things you see are morph targets. you just have to export it as obj and delete what you don't want.
## Post #5
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2013-01-10T11:38:42+00:00
- Post Title: Music Girl Nene mdl

yeah for the hands ,they are so many (so i can maybe delete them)
but for the face,leg..they are missing,so is there any way to solve this beside remodeling it ?
## Post #6
- Username: LuchiaL
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-10T11:47:13+00:00
- Post Title: Music Girl Nene mdl

Did you look for the face mabee its out of position in the center of the mesh or something.
best bet is to export and look in a 3d program.
You could try the maya script I released to import the models also.
## Post #7
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2013-01-10T11:50:04+00:00
- Post Title: Music Girl Nene mdl

thanks for the help chrox,i will try your maya script
and report the result soon..  

#thanks chrox,the script work perfectly,all the hands are in different layers c;
 and for the texture i export it from noesis..

thanks for interested in my problem
[nenek.png](https://xentaxbackup.github.io/file/6125_nenek.png)
## Post #8
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-08-10T15:56:02+00:00
- Post Title: Music Girl Nene mdl

Dokidoki! Precure Touch and Talk uses the same format as this but I am having a problem with the bone structure when using Chroxx's script.
## Post #9
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2013-11-04T19:42:50+00:00
- Post Title: Music Girl Nene mdl

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-28T02:10:14+00:00
- Post Title: Music Girl Nene mdl

You can fix the script with one line edit
They just moved the quat to a different position
just change the line to be these numbers

```
 boneOritation = om.MQuaternion(boneMat[8], boneMat[9], boneMat[10], boneMat[11])
```
