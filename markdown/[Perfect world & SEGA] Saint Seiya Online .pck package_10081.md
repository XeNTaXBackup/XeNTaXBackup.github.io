## Post #1
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-01-25T16:18:25+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

hello, this is my first time posting here ...

I would like some help in extracting files from an archive of the game Saint Seiya Online produced by SEGA and the Perfect World. I already test several PCK extractors but it seems that none works in this new game
I already tried to learn how to create extractors in QuickBMS but not had much success, but at least I could understand something of the files that I tested. When I opened the Saint seiya files in hex ​​editor  my mind exploded. I could not understand anything.
if someone can help me or give me some light here is a sample file:
[http://www.4shared.com/file/cuptruEt/configs.html](http://www.4shared.com/file/cuptruEt/configs.html)
My real intention is to extract the models to make a costume using papercraft.
I do not know if using this file will be possible to create a decent extractor to the Models.pck file
if necessary use the models.pck file, the official link to download the game is this:
[http://download102.wanmei.com/sds/clien ... 130115.zip](http://download102.wanmei.com/sds/client/sds_20130115.zip)
The 3d models are beautiful, I realy need this:


if no one can help thanks for your time ^^
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-27T16:06:42+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

You can try ninja ripper if what you want is the models.
## Post #3
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-01-27T20:39:24+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

the problem is that the game is in closed Beta in china, I cant access the game

thanks for your help, if there is any way to bypass the restriction I will surely test
## Post #4
- Username: renato
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-28T03:41:16+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

Saint Seiya Online pck Extractor
this is a quickbms script.
you can try fatducks importer as it uses the .ski format for models.

```
#by chrrox
#quickbms from aluigi http://aluigi.altervista.org/quickbms.htm
get magic1 long #0x4dCa23EF
get arcsize long
get magic2 long #0x56A089B7
goto -8
get files long
goto -272
filexor "0xe1 0xf9 0xa4 0x62"
get tbloff long
filexor ""
for i = 0 < files
goto tbloff
filexor "0xe1 0xf9 0xa4 0x62"
get tzsize long
filexor "0xd5 0xC3 0x20 0x35"
get tzsize2 long
filexor ""
savepos tbloff
clog MEMORY_FILE tbloff tzsize 276
getdstring name 0x104 MEMORY_FILE
get offset long MEMORY_FILE
get size long MEMORY_FILE
get zsize long MEMORY_FILE
if size == zsize
log name offset size
else
clog name offset zsize size
endif
math tbloff + tzsize
next i


```
## Post #5
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-28T04:16:38+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

Downloading the CBT
## Post #6
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-01-28T08:15:49+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

MAN MAN MAN MAN MAN MAN, i'm crying right now, I can not find words to thank you

you are the best OMFG

I'm looking for a way to extract it from when the game was released for download, I was already going crazy

Thank you, thank you so much
## Post #7
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-01-28T12:23:44+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

it worked perfectly, now the problem are the files of the models, I could not find a converter that works, I tried the Fat importer and some Blender addons.

the hex editor shows a  intelligible code, I can see the object groups, the textures names, but I could not find a guide to help me create a converter to obj, my knowledge of programming borders on nothing

I have attached a sample in the post
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-28T12:27:35+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

you should ask fatduck to update his importer in his thread.
## Post #9
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2013-01-28T12:45:17+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

ok, thanks so much for your help ^^
## Post #10
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2013-06-28T08:18:33+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

> Reply from chrrox
>
> you should ask fatduck to update his importer in his thread.
SKI How to extract
[ski.zip](https://xentaxbackup.github.io/file/6487_ski.zip)
## Post #11
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2013-08-04T08:13:26+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

Has anyone found a solution there for ski convert?
## Post #12
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2014-05-14T22:26:37+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

Hi, the QuickBMS script doesn´t work for me, it gives me this error:

"Incomplete input file number 0, can´t read 4 bytes"

and doesn´t decompress anything, please help me ! !
## Post #13
- Username: kangaroo78
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Sep 29, 2015 6:24 pm
- Post datetime: 2016-02-02T11:16:14+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

IS there any updates guys, I have been trying to unpack model.pck, have done the  tempmodel.pck but then cant do anything after that. IS there anyone that can give a bit of help please?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-13T06:47:22+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

Is it a problem of a format change or is it a problem of using the unpacker?
What exactly did you do?

In case it's a format change try to get an old version sample, unpack it.
Then use the script on the new format and report exactly what happens.

> Reply from kangaroo78
>
> have done the  tempmodel.pckDoes mean what? Does this .pck result from the model.pck extraction? (Guess 'no'.)
## Post #15
- Username: kangaroo78
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Sep 29, 2015 6:24 pm
- Post datetime: 2016-03-04T02:49:41+00:00
- Post Title: [Perfect world & SEGA] Saint Seiya Online .pck package

> Reply from shakotay2
>
> Is it a problem of a format change or is it a problem of using the unpacker?
What exactly did you do?

In case it's a format change try to get an old version sample, unpack it.
Then use the script on the new format and report exactly what happens.
kangaroo78 wrote:have done the  tempmodel.pckDoes mean what? Does this .pck result from the model.pck extraction? (Guess 'no'.)

I cant unpack the "model.pck". ( I used the script for the other .pck and it worked with no problem but no the model.pck) I followed a tutorial from another site that says that combining  model.pck + model.pcx = tempmodel.pck and then it should be easier to unpack and be able to get all models there, but script didnt work. (dnt know if the script has to be modified for that tempmodel.pck, if so I dnt know how)
## Post #16
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-03-12T10:24:25+00:00
- Post Title: Re: [Perfect world & SEGA] Saint Seiya Online .pck package

Someone would be what kind of file handles animations and if we can import them into 3dsmax
## Post #17
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-03-15T14:01:47+00:00
- Post Title: Re: [Perfect world & SEGA] Saint Seiya Online .pck package

I can not find the icons in the package someone would be or are they?
