## Post #1
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2021-02-03T10:13:46+00:00
- Post Title: Robotech Battlecry Vicious Engine .Pak Files Extraction?

Currently looking to get the .Pak files from Robotech: Battlecry extracted, so I can look into them. Models, textures, anything that is possible to extract from these .pak files will be greatly appreciated! I've read some other previous posts on here for games on the same engine, and most people seem to say this is a REALLY Easy, uncompressed format. Which, I'd love to see for myself, although I can Not for the life of me, get into them. And I have used some of the scripts that people have made, but they never seem to work, unfortunately, usually citing this error: 

"Error: incomplete input file 0: vf1a.pak
       Can't read 64 bytes from offset 737a1000. (<- I assume this is because the file is a particular hex that the script does not account for?)
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0     1%   32979      1666060    . offset 737a1000

Last script line before the error or that produced the error:
  10  log NAME OFFSET SIZE"

I left a few sample assets, if that helps. Thank you! Anything would be greatly appreciated!!
(It's safe to assume that "skin_stealth" is the skin for the model, and "vf1s" is the choosable head option. I included some other ones I wasn't sure about, cause I would presume Those would be the Body models?)
[https://www.mediafire.com/file/3s8vnjzv ... k.rar/file](https://www.mediafire.com/file/3s8vnjzvbzwrpom/RobotechBattlecryPak.rar/file)
## Post #2
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2021-12-15T18:52:49+00:00
- Post Title: Robotech Battlecry Vicious Engine .Pak Files Extraction?

Bump, sorry. I'm really looking into getting these extracted. Any help is appreciated
## Post #3
- Username: Fortniteman11
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2022 9:43 am
- Post datetime: 2022-08-22T13:31:44+00:00
- Post Title: Robotech Battlecry Vicious Engine .Pak Files Extraction?

did you figure it out
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-10-23T04:17:21+00:00
- Post Title: Robotech Battlecry Vicious Engine .Pak Files Extraction?

Those models are made with a lot of submeshes, I analyzed one submesh and I found vertices and faces but my result looks like a mess.. It seems like those files are from Gamecube version so I tried with Xbox version and the result looks better:





It is better if you use Xbox files but you need to extract each submesh manually because I don't know the whole format of .pak files. For what I can see, these .pak files include skeleton, meshes, animations and textures.
