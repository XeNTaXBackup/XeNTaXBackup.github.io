## Post #1
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-07-09T15:22:47+00:00
- Post Title: Mortal Kombat Komplete Edition (PC) .XXX AUDIO Files

Hello! I hope everyone enjoyed MKKE as much as I did. Especially those squishy X-RAY sounds

As far as I know, MK is using Unreal Engine. And the "Asset" folder is where I believe they keep all the goodies. It'ss full of .xxx files and I tried my best to open them, but unfortunately with no luck. I'm pretty bad at this, so that's why I'm asking for your help :>

Here is an archive full of .xxx files samples:

 http://www.mediafire.com/download/0aw29 ... amples.zip 
(link updated)

Thank you for your time and help
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-09T20:36:18+00:00
- Post Title: Mortal Kombat Komplete Edition (PC) .XXX AUDIO Files

first, [http://www.gildor.org/down/35/umodel/extract.zip](http://www.gildor.org/down/35/umodel/extract.zip) then use a fsb extractor like fsbii or just search for the string "FSB4" in a hex editor on the .fmodeventfile within those extracted, and cut everything that comes before that out.
[http://www.hcs64.com/files/fsbii07.zip](http://www.hcs64.com/files/fsbii07.zip) <- easier method, just drag a .fmodeventfile onto it. it should spit out a .fsb file.
the final step, fsb extractor, which gives you .mp3 files with this game.
[http://aezay.site11.com/aezay/fsbextractor/](http://aezay.site11.com/aezay/fsbextractor/) (if this is down, try fsb_mpeg or fsbext, [http://www.hcs64.com/files/fsb_mpeg012.zip](http://www.hcs64.com/files/fsb_mpeg012.zip) or [http://aluigi.altervista.org/papers/fsbext.zip](http://aluigi.altervista.org/papers/fsbext.zip)
files will now have proper names, the biggest task is finding the right .fmodeventfile (s)
most of the xray sounds are in each CHAR's .xxx, within a folder in the extracted contents starting SND_SFX_(charname) then in a subfolder named "projects" then finally look for the one with PS3 in the name, you'd expect pc, but this was a weird port job, they originally had a pc port planned, but scrapped it, hence why the original ps3/360 release still had the pc sound banks (which are just a placeholder in ALL versions, including the final pc port.)
## Post #3
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-07-10T06:51:54+00:00
- Post Title: Mortal Kombat Komplete Edition (PC) .XXX AUDIO Files

Thank you for such a useful and detailed guide, Pepper!
