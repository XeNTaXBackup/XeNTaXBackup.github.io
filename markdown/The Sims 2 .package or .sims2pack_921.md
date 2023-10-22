## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-21T20:03:35+00:00
- Post Title: The Sims 2 .package or .sims2pack

I know the game just came out but I thought I might as well ask.  Any chance of supporting The Sims 2 game data files (.PACKAGE) or the installer files (.SIMS2PACK) ?
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-22T03:55:48+00:00
- Post Title: The Sims 2 .package or .sims2pack

Hey,

Check out [http://www.modthesims2.com](http://www.modthesims2.com) for a bunch of programs to do this. Mr Mouse, you will also find the specs for these files on the wiki at this site - the package format is a snack, but you won't be able to do the other formats without a specific plugin because they use XML directories.

ModTheSims2 is being run by a group of people who have had alot of experience modding games like Simcity 4, including myself, and some new tools should be coming out pretty soon. The big tool, DatGen, is already half-developed and will do all the handling of *.package files.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-30T09:57:14+00:00
- Post Title: The Sims 2 .package or .sims2pack

I'm looking at some .package files with DatGen 0.6, and all I get is a bunch of Unknown 
types.  I see some PNG graphics files, some XML text files, and some other text files
with parameters.

But what I'm interested in is the model geometry (vertices/faces) and animation data. 

Do these files contain it, or are these files just specify customization parameters?  
Because I don't care too much for customization files.  I want the raw 3D model data.
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-30T21:40:33+00:00
- Post Title: The Sims 2 .package or .sims2pack

And is it true you can't find any filenames in the .package file?

Are you sure they aren't hidden away in an unknown compressed section at the 
end of the file?  I think it would be rather stupid for the programmer to strip
away filenames.
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-10-05T14:15:14+00:00
- Post Title: The Sims 2 .package or .sims2pack

Well based on Simcity 4, which uses the same archive format, there are no filenames stored with the files. However, there are a *few*, a very minor *few*, that do have filenames stored with them.

The version of Game Extractor you can download from [http://www.modthesims2.com](http://www.modthesims2.com), or from my website, will display filenames for the files that have them.

In regards to DatGen, download the latest version (0.7) to be able to read the archives. ([http://www.datgen.info](http://www.datgen.info))

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-12T23:32:52+00:00
- Post Title: The Sims 2 .package or .sims2pack

To tell you the truth, I don't like java or winrar very much.  They are such an inconvienent to use.

If you want your programs to be used by everyone, I would distribute them as Win32 executables
and compress them using Winzip.  More people will use them.  Otherwise, I don't think they will become
very popular.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-10-17T12:41:23+00:00
- Post Title: The Sims 2 .package or .sims2pack

1. I don't use WinRar, I use WinZip
2. I use Java because I an most comfortable programming in it, it has a huge backend and support community, and it works on all computer systems. It also has a very nice and convenient plugin backbone

I do my best to make my Java programs run easily for Windows users, as most of the people using my software do use Windows. For example, I include an *.exe file and several *.bat files that will run the program for you.

Now, feel free to go ahead and write Windows programs if you want to, I certainly won't stop you, however i won't be changing to something like C++ just because one person doesn't like Java - unfortunately thats not the way things work. In the last month, I have transferred about 6GB of Game Extractor from my website, which equates to about 12000 downloads, as well as an extra 150MB of traffic every day - I don't know whether you would call this popular but I certainly do.

Sorry for the harsh tone, I just get alittle annoyed when people come along and bag your programs and such when they don't even know the first thing about programming, let alone reasons behind the choices that I have to make and the time I spend developing tools for other people so that everyone can have the same benifits that I have. Sorry re: dissapoinment or offence.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-18T02:57:34+00:00
- Post Title: The Sims 2 .package or .sims2pack

> Reply from friendsofwatto
>
> 2. I use Java because I an most comfortable programming in it, it has a huge backend and support community, and it works on all computer systems.

That isn't .... 100% true.  It runs on every system that has a JavaVM for it.  Unfortunately, there isn't a VM for ALL systems, just all of the main systems that most people use.  And since the JavaVM isn't open source, you can't compile it for a new system.
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-10-18T12:44:06+00:00
- Post Title: The Sims 2 .package or .sims2pack

True, but I assume the majority of users run either Windows, Mac, Solaris, or Unix/Linux.
