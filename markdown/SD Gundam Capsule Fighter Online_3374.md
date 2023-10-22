## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-03-01T07:43:20+00:00
- Post Title: SD Gundam Capsule Fighter Online

I really like this game and it use some kinds of modified zlib for the package!
Full client can be download at: 
[http://count1.9you.com/download.php?id=434](http://count1.9you.com/download.php?id=434)

And since the resources are packed into one big file (800M) so I can't upload it ATM!

I can cut some out if anyone wanted!

Here is a screenshot:
[SDGO.jpg](https://xentaxbackup.github.io/file/1899_SDGO.jpg)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-03-02T11:18:25+00:00
- Post Title: SD Gundam Capsule Fighter Online

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-02T14:27:14+00:00
- Post Title: SD Gundam Capsule Fighter Online

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-03-02T20:08:42+00:00
- Post Title: SD Gundam Capsule Fighter Online

uhmmm I have taken a look to cut.zpk and I have written a tool for extracting those files.
in short that archive is just a sequence of gzip files divided in chucks of 512 bytes but the problem is that their content is not much comprehensible so my tool is mainly an excercise and probably it's not so useful in practice.

*edit* new version: [http://aluigi.org/papers/sdgundamext.zip](http://aluigi.org/papers/sdgundamext.zip)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-02T23:16:58+00:00
- Post Title: SD Gundam Capsule Fighter Online

the image format is tga just delete the first 16 bytes of the texture files.
some of the texture files are also bmp they are the same though just delete the first 16 bytes
[](http://xs.to/xs.php?h=xs537&d=09101&f=000057c2.zoa624.jpg)

I have attached a model file from this game here it says it should be a simple plain so it should be a good way to find the model format.
[000032af.rar](https://xentaxbackup.github.io/file/1907_000032af.rar)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-03-03T16:57:44+00:00
- Post Title: SD Gundam Capsule Fighter Online

I have downloaded the game and I have also rewritten my tool since I have figured the fields of the zdx file, so now all the extracted files have their full names.
anyway I have seen that exist some files (a very low number) which seem corrupted because happen some errors during the decompression, an example is "anrs\10040.ani" which is just truncated (so it's for sure not an error of the extractor) while the others are more strange.
anyway the new version is available here:

[http://aluigi.org/papers/sdgundamext.zip](http://aluigi.org/papers/sdgundamext.zip)
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-03-03T22:22:19+00:00
- Post Title: SD Gundam Capsule Fighter Online

Thank you bugtest!

Just come back to see what its up to and you already updated your tools!

It seems to work fine, have to check the files and get back to you ASAP!

Thank you.
## Post #8
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-21T02:55:54+00:00
- Post Title: SD Gundam Capsule Fighter Online

I had read this post.It is very useful to me.And I want to ask some questions.I down the sdgundamext.zip and unzip it,then open the sdgundamext.exe,but it can't work.When it open,then it close automatically.Is some thing worng of my operation?
Thank you.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-21T06:31:45+00:00
- Post Title: SD Gundam Capsule Fighter Online

it's a command-line tool so must be launched from the console.
go on Start->Run and type cmd (or command if you are on Windows 9x)
will appear the black console window.
now extracted sdgundamext.exe in c:
create a new folder in c: called extract
type:
c:\sdgundamext PATH_OF_THE_FILE c:\extract

where PATH_OF_THE_FILE is the full path of your ZPK or ZDX or DAT file of Gundam, if you don't have much practice with the console maybe copy the file in c: and so use c:\name_of_the_file
if you have Windows XP it's enough to type c:\sdgundamext (space) then drag the file you want to extract with the mouse in the console and will appear its full path automatically :)

obviously this usage seems long because it's just a quick step-by-step for users who have never used the console because in reality using the command-line is a joke for how much it's easy.
some other info about how to use the command-line tools are available [here](http://aluigi.org/about.htm#howuse)
## Post #10
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-21T16:24:02+00:00
- Post Title: SD Gundam Capsule Fighter Online

Thanks for your help.
I want to ask one more question about how to change texture files to tga or bmp files?
Also I want to change the charcter voice.The voice file maybe in the mdrs and couldn't open in general way.
Thank you!
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-21T18:48:23+00:00
- Post Title: SD Gundam Capsule Fighter Online

I can't help with the repacking because for various reasons I do only the extraction job
## Post #12
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-21T23:28:34+00:00
- Post Title: SD Gundam Capsule Fighter Online

Hello,I want to know how to change texture files to tga or bmp files  like chrrox do. I had try to del the first 16 bytes of the txr file but counldn't open it.
## Post #13
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-26T02:38:56+00:00
- Post Title: SD Gundam Capsule Fighter Online

I want to ask how to change texture files to tga or bmp file?
I have extract all the file and del the first 16 bytes to some txr files of txrs folder,and change their name to .tga or .bmp,but still can't open it.Is something worong to my way?
Sorry for my poor English.
Thank you.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-26T03:25:02+00:00
- Post Title: SD Gundam Capsule Fighter Online

Here is a sample so you can edit the file yourself.
basically you just remove the first part of the file until you have 2 spaces before the first non zero character.
[http://www.MegaShare.com/1138017](http://www.MegaShare.com/1138017)
## Post #15
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-26T07:26:50+00:00
- Post Title: SD Gundam Capsule Fighter Online

Thanks for your help.
And I want to open directly the voice file on mdrs folder,but fail finaly.Using the Extractor can scan some wav files(not full),and the vocie have cacophony.
Here is the one file of mdrs folder.
[2641.rar](https://xentaxbackup.github.io/file/2160_2641.rar)
## Post #16
- Username: eeveekwok
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 20, 2009 4:01 pm
- Post datetime: 2009-06-27T10:03:39+00:00
- Post Title: Re: SD Gundam Capsule Fighter Online

here is more mod files of mdrs folder.
[http://www.MegaShare.com/1144968](http://www.MegaShare.com/1144968)
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-03T15:04:48+00:00
- Post Title: Re: SD Gundam Capsule Fighter Online

IMPORTANT update:
I have rewritten the tool completely (the extraction was bugged) and I have also added the possibility of rebuilding the archives because a recent patch in the hongkong version (0.9.34) no longer allows to reuse the files from the same game folder:

[http://aluigi.org/papers.htm#sdgundamext](http://aluigi.org/papers.htm#sdgundamext)

I have seen that this tool has had a huge diffusion recently so don't miss this update and in case of problems I'm here.

some usage examples:
- classical extraction of all the files:
  sdgundamext "C:\Program Files\9you\SD°ª1FOnline\GPackData.zpk" z:\output_folder

- listing of the files
  sdgundamext -l "C:\Program Files\9you\SD°ª1FOnline\GPackData.zpk" none

- extraction (or listing) of the files with the ani extension:
  sdgundamext -f "*.ani" "C:\Program Files\9you\SD°ª1FOnline\GPackData.zpk" z:\output_folder

- rebuilding of the archive:
  sdgundamext -b "C:\Program Files\9you\SD°ª1FOnline\GPackData_new.zpk" z:\input_folder
## Post #18
- Username: muvluv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 04, 2010 4:32 pm
- Post datetime: 2010-06-08T14:51:17+00:00
- Post Title: Re: SD Gundam Capsule Fighter Online

Does someone knows how to edit or modify your own faceless operator for another one?
I've been trying to figure it out...
