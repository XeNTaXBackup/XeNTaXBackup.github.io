## Post #1
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-10-11T06:29:59+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

Hi, Guys.

Do you have any idea how we could unpack/repack .pak Archive from " Ryse : Son of Rome "
The game used 4th generation of CryEngine and can't be extract by 7zip.

.pak file are protected.

here a sample : 
[http://www.mediafire.com/download/n00t4 ... meData.pak](http://www.mediafire.com/download/n00t4zv0z48wdc0/GameData.pak)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-11T11:41:48+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

The game uses LZ4 compression so an unpacker is quite possible
## Post #3
- Username: rock55
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 12, 2014 12:41 am
- Post datetime: 2014-10-11T17:52:37+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from sarzamin
>
> Hi, Guys.

Do you have any idea how we could unpack/repack .pak Archive from " Ryse : Son of Rome "
The game used 4th generation of CryEngine and can't be extract by 7zip.

.pak file are protected.

here a sample : 
http://www.mediafire.com/download/n00t4 ... meData.pak
in karha khobe anjam bedi khodet kari ro shoro koni <ama in ke kar virayesh shode kase diga ro ke faktor foroshe ro ham didi, bery virayesh koni befresti anjoman
bad polesh ro ham begiri (haram ast) dorost nist!
shayad pish biad har kari ke anjam bedi kase dige bezane va befroshe! hamishe ke anjoman bisaheb ba shoma nist!!!!
har zaman virayesh mikoni fekr in bash ke haghe kase dige ee ro khordi pas age haghet roozi khorde shod narahat nasho!!
to in site emkane ersal pm nadaram,har kas etelaat in tory be shoma dade mesle sag dorogh gofte,vase albaghi ham rodar ro shodim sohbat mikonim(ba shoma ya ba mn,sarzamin)
ama cod of 3,variant,.. 
az nazar man bayd talafi she ta donbal haghe kas dige nabashid , ta ba amsale jabar singh hamkari nakonid.
## Post #4
- Username: alterian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 12, 2014 2:47 pm
- Post datetime: 2014-10-12T07:02:21+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

Yeah, a Ryse unpacker would be pretty sweet!
## Post #5
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-10-12T12:19:50+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

The sample you posted is not a good one.

I can clearly see some zip dictionary ending headers on the bottom of it but local headers are missing. If the archives use zip format to store their contents that would make it a lot easier to make an unpacker
## Post #6
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2014-10-12T13:52:58+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

Ryse .pak files can be decrypted with the Crysis3 .pak decrypter.
[http://crysis.gamebanana.com/tools/5416](http://crysis.gamebanana.com/tools/5416)
## Post #7
- Username: extreing
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 11:05 pm
- Post datetime: 2014-10-12T15:08:45+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from joqqy
>
> Ryse .pak files can be decrypted with the Crysis3 .pak decrypter.
http://crysis.gamebanana.com/tools/5416
no is not, i cant decompress with the PakDecrypt
## Post #8
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-10-13T09:39:36+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

Maybe it's like Warface where the tool can work if it has the right "key" to the pak files?
(So someone would need to find what the decrypt key for Ryse is.)
## Post #9
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-10-13T12:46:25+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from extreing
>
> joqqy wrote:Ryse .pak files can be decrypted with the Crysis3 .pak decrypter.
http://crysis.gamebanana.com/tools/5416
no is not, i cant decompress with the PakDecrypt
Actually it worked fine for me with Sounds.pak from pc release. only problem is ryse uses a 64bit fmodex dll so lolfsb extract can't use that to decode the fsb vorbis.
## Post #10
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-13T15:14:49+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

I just get a zip file after unpacking and inside that are just OGG files that I can edit with no problem. How are you getting FSBs?
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-10-13T22:48:50+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from brendan19
>
> I just get a zip file after unpacking and inside that are just OGG files that I can edit with no problem. How are you getting FSBs?
I.. don't know? I can screenshot for you. I bought it from steam a few days ago.
## Post #12
- Username: extreing
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 11:05 pm
- Post datetime: 2014-10-14T15:26:41+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from Pepper
>
> brendan19 wrote:I just get a zip file after unpacking and inside that are just OGG files that I can edit with no problem. How are you getting FSBs?
I.. don't know? I can screenshot for you. I bought it from steam a few days ago.

The problem is with Gamedata.pak and script.pak
## Post #13
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-10-15T12:49:22+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

> Reply from extreing
>
> Pepper wrote:brendan19 wrote:I just get a zip file after unpacking and inside that are just OGG files that I can edit with no problem. How are you getting FSBs?
I.. don't know? I can screenshot for you. I bought it from steam a few days ago.




The problem is with Gamedata.pak and script.pak

He was talking about ogg files. those would be inside the sounds one, but all I get is FSBs.

though it seems you were meaning to quote this:

> Reply from Pepper
>
> extreing wrote:joqqy wrote:Ryse .pak files can be decrypted with the Crysis3 .pak decrypter.
http://crysis.gamebanana.com/tools/5416
no is not, i cant decompress with the PakDecrypt
Actually it worked fine for me with Sounds.pak from pc release. only problem is ryse uses a 64bit fmodex dll so lolfsb extract can't use that to decode the fsb vorbis.
## Post #14
- Username: Gora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 18, 2011 12:03 am
- Post datetime: 2014-10-20T17:04:10+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

Crysis 3 tool is working but the xml files not readed. Please anyone make the ryse xml converter to txt or another read fileformats. Thanks
## Post #15
- Username: nahuellamarca
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 14, 2014 7:07 am
- Post datetime: 2014-12-13T23:12:42+00:00
- Post Title: Ryse Son of Rome .pak Archive ( CryEngine (4th generation) )

HI TO YOU ALL!! im new here, id need sounds.pak archive, just if anyone of u could upload it, would be great. Because it says its corrupted this file in my game so i dont have any effect sound during the game. I would really appreciate
## Post #16
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2015-06-21T05:23:50+00:00
- Post Title: Re: Ryse Son of Rome .pak Archive ( CryEngine (4th generatio

> Reply from Gora
>
> Crysis 3 tool is working but the xml files not readed. Please anyone make the ryse xml converter to txt or another read fileformats. Thanks
It's not real XML format. Open in HEX editor.
## Post #17
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-05-08T20:47:13+00:00
- Post Title: Re: Ryse Son of Rome .pak Archive ( CryEngine (4th generatio

> Reply from Gora
>
> Crysis 3 tool is working but the xml files not readed. Please anyone make the ryse xml converter to txt or another read fileformats. Thanks

XML files are in Crytek Binary XML format - it is quite simple actually.

I have attached a quick and dirty maxscript that parses this format.
Just run the script in 3ds max (only tested with max 2017, but should work in recent versions as well, but not guaranteed).

As you process a file, take a look at the output, and if you know some maxscript, it will be easy to make sense of what is coming out.
/joq

[edit]
updated script attached...
[XML_binary_reader_2.7z](https://xentaxbackup.github.io/file/10933_XML_binary_reader_2.7z)
