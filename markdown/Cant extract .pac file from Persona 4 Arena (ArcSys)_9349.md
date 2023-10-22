## Post #1
- Username: diorjets
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2012 8:55 am
- Post datetime: 2012-07-25T19:25:10+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

are two examples of the files i cant extract, using ([http://aluigi.altervista.org/papers/bms/arcsys.bms](http://aluigi.altervista.org/papers/bms/arcsys.bms)) this script.
can anyone help with this?
## Post #2
- Username: snakemeat
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-25T20:07:10+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

decompress the 360 files first using the 360 sdk.
xbdecompress is the exe you need.
it is not legal to share this file.
## Post #3
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2012-07-26T21:14:11+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

I apologise for not seeing the other thread, however... This decompression method didn't do anything. Well unless deleting the source file meant something.

Which leaves the answer, maybe this wasn't compressed this way?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-26T23:29:56+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

this does work i am not sure what you are doing.
you need to use the command prompt.

c:\xbdecompress.exe c:\file.pac c:\file.pac.ext
then run the bms file on the decompressed file.
## Post #5
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2012-07-27T09:42:56+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

Me and a few others have already tried this and as I said above it's not compressed with that.

Any other way of finding out the compression on it?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-27T11:39:31+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

then you are doing something wrong I have already tested this and it works fine.
## Post #7
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2012-07-27T11:45:07+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

> Reply from chrrox
>
> then you are doing something wrong I have already tested this and it works fine.

Could you upload the decrypted files for me then please? Because I am having great trouble. Thankyou.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-27T11:46:14+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

no please read the rules.
what could you possibly do with the files if you can not use the command line?
post a screenshot of the error you get and I can tell you what you did wrong.
## Post #9
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2012-07-27T11:55:08+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

> Reply from chrrox
>
> no please read the rules.
what could you possibly do with the files if you can not use the command line?
post a screenshot of the error you get and I can tell you what you did wrong.
[http://i.imgur.com/QmEsK.png](http://i.imgur.com/QmEsK.png)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-27T11:59:12+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

yeah you are doing it wrong.
you must type
xbdecompress.exe "SPACE" original pac file name "SPACE" new filename for the extracted pac.
the best way to do that is this
open the command prompt
drag xbdecompress into it.
then hit space
now drag the pac file you want to decompress.
now hit space
now drag the same file again
now type .ext
then hit enter it will extract the file.
then use this bms on the pac files it spits out
once the file is decompressed you must run this bms.
[http://hcs64.com/files/fpac01.bms](http://hcs64.com/files/fpac01.bms)
## Post #11
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2012-07-27T12:02:56+00:00
- Post Title: Cant extract .pac file from Persona 4 Arena (ArcSys)

Thank you so much! Now I am left with XWB files, I presume this is easily convertable.

Used an XWB extractor and got a WAV, the wav file won't work with anything.. Interesting.

Apparently there is a method for encoding the unlistenable WAV to a listenable one.
