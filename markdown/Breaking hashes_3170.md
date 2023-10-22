## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-09-29T22:15:04+00:00
- Post Title: Breaking hashes?

[out]
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-29T22:26:01+00:00
- Post Title: Breaking hashes?

The keyword is bruteforce.
As you might already guess, it takes centuries to break long keys.
As the author describes in this site, there are several things that ease name breaking for MPQ. (Otherwise it was nearly impossible to break all of the files)
If you want to get the key for an MD5, LM, NTLM or in future also SHA hash, you can use rainbow tables, e.g. from [http://freerainbowtables.com/](http://freerainbowtables.com/)
support the project
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-09-29T22:58:28+00:00
- Post Title: Breaking hashes?

[out]
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-09-29T23:23:39+00:00
- Post Title: Breaking hashes?

[out]
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-30T10:52:10+00:00
- Post Title: Breaking hashes?

> Name breaking optimizations (Good news)
>
> 
>
> There are some optimizations, which ease and speed-up the name breaking
>
> It is good to sort the names in the archive by their ordinal numbers in the archive. Because the archives are most often built from locally stored files in one batch, archived files from the same directory and the same file types mostly follow in a line.
>
> Some file names differ only by their index (flame1.cel, flame2.cel, ...). This can be used for quick guess of file names ("try to win")
>
> File size can tell something too. It is possible to get the size without decrypting the file.
>
> MPQ encryption contains a weakness, which can be used for quick detection of decryption key of compressed files. Most of archived files are compressed, except for the files that are compressed from nature, like SMKs or MP3s. So it is possible to extract the file and explore its structure. This allows us to quess the file type and thus, the extension.
>
> Like disk folders, MPQ directories often collect files of the same type. For example if all known files within a directory are WAVes, the unknowns will be most probably WAVes too.
>
> When checking names, it is possible to pre-calculate hash values for a given directory and then finish the calculation with plain name only. This greatly speeds up the computing of hash values and thus speeds up the complete name breaking process
>
> If a certain group of files seem to have the same prefix (e.g. 2 characters), it is possible to include this prefix into the searched directory and search only the remaining 6 characters of the name. This will shorten the necessary time for testing all names to minutes.
## Post #6
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-03T14:59:45+00:00
- Post Title: Breaking hashes?

let me guess, you are trying to use this for Warhammer online? there's no point, if you have the hash algorithim, then look at the files extracted with no name, find ones that reference other files, and figure out the filenames, that's how all the peole who can extract files with filenames for WAR do it
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-04T10:40:12+00:00
- Post Title: Breaking hashes?

[out]
## Post #8
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-06T16:00:30+00:00
- Post Title: Breaking hashes?

for example, the .mod files in the archive reference .xml and .lua files, if you can correctly figure out the base path, you can create filenames from base path+ referenced file, and from that, you can build a hashlist
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-07T05:43:10+00:00
- Post Title: Breaking hashes?

[out]
## Post #10
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-07T23:32:20+00:00
- Post Title: Breaking hashes?

[http://code.google.com/p/easymyp/](http://code.google.com/p/easymyp/)

can extract with filenames. what are you planning on doing with the model data? making a model viewer? i can go ahead and tell you the models are in .nif(gamebryo engine) and a proprietary format, that is pretty easy to figure out, textures are stored both as dds and as a proprietary modification of it, that i haven't been able to crack
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-08T05:18:13+00:00
- Post Title: Breaking hashes?

[out]
## Post #12
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-08T16:31:39+00:00
- Post Title: Breaking hashes?

models are in art.myp and art2.myp, they have the .nif and .geom extension
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-08T21:38:09+00:00
- Post Title: Breaking hashes?

[out]
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-09T16:24:04+00:00
- Post Title: Breaking hashes?

[out]
## Post #15
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-09T22:52:03+00:00
- Post Title: Breaking hashes?

texture references are stored elsewhere, in the assetdb/figleaf.db file, it combines toegther all the meshes and textures
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-10T01:20:56+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #17
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-10T14:04:51+00:00
- Post Title: Re: Breaking hashes?

if you ever make any progress on the .diffuse textures used for mobs/chars lemme know, they are gving me a hard time atm
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-10T19:49:06+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-10T23:34:57+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-11T01:12:40+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #21
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-11T17:00:59+00:00
- Post Title: Re: Breaking hashes?

i'm pretty sure the bone hierarchy is stored in .xac files, and yah I've gotten that far on the .diffuse files, but the problem is the dword after mipmap_height/width isn't always zero, it appears to be two separate words, and I've found that most of the time, when those are 0, everything is just simple dxt1, but if the other words are there, regular dxt1 doesnt work
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-11T21:49:15+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #23
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2008-10-11T22:58:16+00:00
- Post Title: Re: Breaking hashes?

> Reply from Wobble
>
> So:
4 + 0 = 0
12 + 4 = 16
44 + 20 = 64
168 + 88 = 256
332 + 180 = 512

I guess someone didn't do to well in math
## Post #24
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-11T23:26:33+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #25
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-10-12T01:22:33+00:00
- Post Title: Re: Breaking hashes?

have you been able to get any of those textures to render correctly(with the extra words i mean), and .xac are in art.myp i'm pretty sure
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-10-12T02:12:29+00:00
- Post Title: Re: Breaking hashes?

[out]
## Post #27
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-10-18T02:56:52+00:00
- Post Title: Re: Breaking hashes?

Hmm interesting topic. Well heres my 2 cents.

Hashes like MD5 and SH1 can be broken in a couple minutes. That is if you know the length of the string it hashes. If it hashes part of a file and it is somewhat small, it can also be broken within a reasonable time frame. It all depends on what you know, and how you can use it to get what you don't know.

Other checksums such as simple binary functions can be broken very easily. It all depends on how you code your breaking app and what info you have at the start.
## Post #28
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-07-01T13:11:01+00:00
- Post Title: Re: Breaking hashes?

Warhammer Online hash v1.6 released June 28 for the Warhammer 1.30 update at [http://code.google.com/p/easymyp/downloads/list](http://code.google.com/p/easymyp/downloads/list) 

With this new hash file you can extract about 400mb of new models/texures from the Land of the Dead update.

Has anyone made any progress on the .geom files?
