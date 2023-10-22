## Post #1
- Username: RyGaR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 29, 2006 9:11 am
- Post datetime: 2006-01-29T06:01:09+00:00
- Post Title: Unreal Championship 2 Xbox .U

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: RyGaR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 29, 2006 9:11 am
- Post datetime: 2006-02-03T07:57:25+00:00
- Post Title: Unreal Championship 2 Xbox .U

umm has anyone had a chance to look at the files? I really would appreciate a response at least   . 22 views and 0 replies
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-02-12T04:38:38+00:00
- Post Title: Unreal Championship 2 Xbox .U

Hi mate,

Yeah I will take a look at the files for you over the next few days. I, like you, get really frustrated over the fact that there are heaps of different *.u* file versions and so forth. Unfortunately I don't know much about the specifics of the Unreal files, apart from the archives, so if you could point me to some inform about one of the file types then I might be able to adjust my Game Extractor plugin to export them properly. In other words, you say the skeletons or meshes or whatever don't export usably, so is there some information somewhere about these formats - I know there are usually some small headers before the actual file content so if I know how the files are structured then I might be able to remove the headings.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: RyGaR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 29, 2006 9:11 am
- Post datetime: 2006-02-15T20:08:27+00:00
- Post Title: Unreal Championship 2 Xbox .U

Hi mr watto thanks for taking a look at the files i appreciate it.   

is this the kind of file format info you were looking for?

[http://wiki.beyondunreal.com/wiki/Package_File_Format](http://wiki.beyondunreal.com/wiki/Package_File_Format)

[http://wiki.beyondunreal.com/wiki/File_Format](http://wiki.beyondunreal.com/wiki/File_Format)

it seems as tho when I attempt to open some of the files with UTPT very little of the coding can be made out. We contected " acordero" of UTPT and he said that he is no longer updating the program but has stated that the programs source code is now availible

> Reply from Acordero
>
> You can get the UTPackages library from SourceForge, but I have attached the
files in this message. These are the current files in my hard disk, probably
a little bit more updated than the SourceForge ones.

The language used is Delphi. I hope you can use the sources to make your own
reader (or use and update my code if you are able to).
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-02-23T10:15:05+00:00
- Post Title: Unreal Championship 2 Xbox .U

OK well I have fixed the plugin up to the point where it will open the archives - hopefully this help alittle.

To use the plugin...
1. Unzip the attachment to your computer (it will be *.class files)
2. Open the GameExtractor.jar file in a zip program like WinZip
3. Copy the *.class files into WinZip
4. Save the archive (as GameExtractor.jar, NOT GameExtractor.zip)
5. Restart Game Extractor.

Or, you can always wait until the next Game Extractor update is released, which will contain this plugin.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_U.zip](https://xentaxbackup.github.io/file/624_Plugin_U.zip)
## Post #6
- Username: RyGaR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 29, 2006 9:11 am
- Post datetime: 2006-02-27T01:21:43+00:00
- Post Title: Unreal Championship 2 Xbox .U

Thank you MrWatto for your help. One question do I need the full version for  this plugin to work?
## Post #7
- Username: OlympusMons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 22, 2006 1:21 am
- Post datetime: 2006-03-21T17:40:36+00:00
- Post Title: Unreal Championship 2 Xbox .U

Thank you so much!

Im a member of this mod team with rygar and Ive done alot of the coding so far, you dont know how much this will help out. Im so please and impressed this is great, Im really at a loss for words. Thanks again!
## Post #8
- Username: OlympusMons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 22, 2006 1:21 am
- Post datetime: 2006-03-21T22:03:00+00:00
- Post Title: Unreal Championship 2 Xbox .U

Ok sorry about the double post but Ive been looking around trying to find more info for you to make things easier. I came up with this link, dunno if you came across it because it is linked from the unreal wiki.

[http://www.acordero.org/download/UT_Pac ... at_pdf.zip](http://www.acordero.org/download/UT_Package_File_Format_pdf.zip)

This is for versions of the unreal engine up to dues ex by the look of it, alot more indepth than the above information. Ive been trying to find out the version and License Mode numbers for as many of the unreal engine games as I can. I'll post a file or something once Ive looked over them all, its seems as though some games might have more than 2 for this so when you skip 6 its not doing enough.

Yes I have been taking a look at the source, seems like I could be of some help. Havent done much java but I can understand whats going on. Like I said I'll take a look around and see how much I can help you out with this because having the UC2 source or even part of it would be really helpful. I have done alot myself but theres just somethings that would be easier if I could see how epic did it.
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-03-27T09:10:04+00:00
- Post Title: Unreal Championship 2 Xbox .U

RyGaR: No, you don't need the full version, it will work with the Basic Version too.

OlympusMons: Thanks mate for the complements  . I have seen that document before, I think, and it was very good starting point when I was trying to build an archive reader for *.u* files . However, as you mentioned, it is for one of the earlier game formats, so it isn't perfectly correct if trying to work with newer formats. 

I have tried to keep the source code (the plugins at least) relatively easy to read - although the Plugin_U.java file is one of the ugliest I have ever written. I have only 1 complaint about the Unreal archives, which is that there are so many "slightly different" versions out there, and archives with the same version number are differently structured depending on the game that uses them.

On a side note, I have a java program I wrote that will scan *.u* files and report the version numbers that are used - very simple and it doesn't do anything terribly impressive, but I use it to find the different archives that I need to analyse in a game. If you want it, just send me an email and I will happily send it to you.

In regards to my *.u* plugin, I really want to do a lot of work on it, such as splitting it up into separate plugins for each version, adding better support for *.u* games, etc but unfortunately I really am pressed for time now that I have started working - I don't even get to check these forums much (maybe once a week)  - however if you want to suggest something, or if you can help with the formats in any way, I will be happy to improve the plugin whenever I am available.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: OlympusMons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 22, 2006 1:21 am
- Post datetime: 2006-03-29T05:58:51+00:00
- Post Title: Unreal Championship 2 Xbox .U

Ok so Im still gathering up version no's etc, I have a pretty large collection of unreal engine games so I'll get as many as I can as it should help isolate certain versions.

Now Ive been thinking about the UC2 *.u's there seems to be some stuff missing, the files are really small compared to there pc counter parts and Im wondering if maybe the scripts.lin file might contain a key or something. Im pretty sure it contains a bulk of the script information but I could be wrong so maybe this is worth taking a look at as this would make this version of the *.u's pretty unique compare to the others.
