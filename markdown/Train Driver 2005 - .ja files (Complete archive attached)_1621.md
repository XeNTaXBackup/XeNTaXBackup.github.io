## Post #1
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-16T16:39:10+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

The filenames arent encrypted but are in the file 1 by 1. however i think a list  of the files is in the end!

Hope u can figure out which compression it uses (hopefully zlib))

[http://rapidshare.de/files/9282149/Core.rar.html](http://rapidshare.de/files/9282149/Core.rar.html)
4mb
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-16T21:24:54+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

If something is compressed with zlib within the file you can check it by yourself with Offzip:

[http://aluigi.altervista.org/mytoolz.htm#offzip](http://aluigi.altervista.org/mytoolz.htm#offzip)

create a temp folder and then type:

  offzip -a yourfile.dat temp 0
and if finds nothing:
  offzip -z -15 -a yourfile.dat temp 0

(the tool supports also other search-only options)
it will extract all the compressed data in the package or will display many errors (in this case press CTRL-C and we need to find what other compression algorithm has been used).
Why doesn't exist a demo or an official homepage for this game?
## Post #3
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-16T22:00:59+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

Dunno why theres no demo.. I bought the game in Game Workshop in Denmark yesterday..
## Post #4
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-16T22:06:42+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

yeah alot of errors :/
but the trainz are so beautyfull , i would like to drop a cc50 tank train inthere hehe!
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-16T22:25:19+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

That's bad, means the game uses encryption or other types of compression.
Unfortunately only zlib and another small number of libraries allows to know if a piece of data is correctly compressed with that algorithm.
I have written a simple tool which uses many algorithms for unpacking data but it cannot "search" the compressed data for the above reason, it's useful only when you know where the compressed data starts and what are the first bytes of the decompressed data.
In short, without the game is not possible to make something.
## Post #6
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-17T08:57:15+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

yeah maybe encrypted but so many words inthere, so i dont think its encrypted just compressed.. The words i spot is like dynamic.braks etc.. Inside the what looks like compressed data!

however everyfile has that CFIL header
after that i founc several values which shows offset position in the main archive file, and length of each file..
Fileend is marked with FIL
## Post #7
- Username: Sly
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 04, 2004 6:19 am
- Post datetime: 2005-12-17T22:27:16+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

> In short, without the game is not possible to make something.

It's possible.
[jaunp.rar](https://xentaxbackup.github.io/file/495_jaunp.rar)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-17T22:46:04+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

Sly, where did you get this from? Did you make this? Can you please explain the compression algorithm that was used if you made this? This is something we really need explained in the WIKI. [http://wiki.xentax.com](http://wiki.xentax.com) Please help us out. If you didn't write this tool, then who did?
## Post #9
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2005-12-18T19:36:50+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

this place rules!

from nowhere a guy post a tool who do the work
## Post #10
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-18T22:42:26+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

kiss kiss kiss! thanx hun.. case closed 
For ppl modding! For making the game read the unpacked data! Place it like this!

F.ex..
World\Core.ja

place in World\Core\*.*

or root\data.ja

to root\data\*.*

when decompressed! u can remove the ja files.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T19:13:14+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

Sly, I ask you once again. Will you explain the algorithm used to compress in the .JA archives? 

If not, why not? If you come here to bloat about your achievements only, we'd rather have you leave. The purpose of this forum is to openly share knowledge, not keep them to ourselves.
## Post #12
- Username: joqqy
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-08T00:32:58+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

Thanks to Rahly's excellent reverse engineering of Sly's attachment (hello Sly, Pespin doesn't protect enough!), we now have the .ja compression solved for the most part. 

I've written a plugin for MultiEx Commander that will enable you to extract the core.ja archive attached to this thread. Hopefully it'll work with other ja files as well. Scroll down to get the plugin! Make a JA folder in MexCom's data/plugins folder and put the dll there. 

Here's the raw VB source code for the routine:

```

' Rahly's cool effort resulted in a Delphi application
' Mr.Mouse converted Rahly's code to VB and adapted it to fit CFIL files. 

Public Function DecompressJAFile(source As String, dest As String) As Boolean

Dim MyFile
Dim Buffer1() As Byte, Buffer2() As Byte
Dim Count As Long, Count2 As Long
Dim Temp1(255) As Byte, Temp2(255) As Byte, Temp3(255) As Byte, Temp4(255) As Byte
Dim TempChar As Long, Counter As Long, Temp As Long, Temp2value As Long, TempIt As Long
Dim CFIL As Long, U1 As Long, UnCom As Long
Dim BlockSize As Integer

On Error GoTo Hell

MyFile = FreeFile
Open source For Binary Access Read As MyFile
Get MyFile, , CFIL
Get MyFile, , U1
Get MyFile, , UnCom
ReDim Buffer2(UnCom - 1)


 For Count = 0 To 255
 Temp3(Count) = Count
 Next Count
 
 Count2 = 0
 
Do

Get MyFile, , BlockSize

If BlockSize > 0 Then ' compression , max bock 7fff?

ReDim Buffer1(BlockSize - 1)

Get MyFile, , Buffer1
 
 Counter = 0
 
 Do
 
   For Count = 0 To 255
   Temp1(Count) = Temp3(Count)
   Next Count
   
   TempChar = Buffer1(Counter)
   Counter = Counter + 1
   Temp = 0

    Do
      If TempChar > &H7F Then
        Temp = TempChar + Temp - &H7F
      Else
        If TempChar >= 0 Then
          TempIt = TempChar + 1
           Do
            Temp1(Temp) = Buffer1(Counter)
            Counter = Counter + 1
            If Temp <> Temp1(Temp) Then
              Temp4(Temp) = Buffer1(Counter)
              Counter = Counter + 1
            End If
            Temp = Temp + 1
            TempIt = TempIt - 1
           Loop Until TempIt = 0
          End If ''tempchar >= 0
       End If '' else

      If Temp < &H100 Then
        TempChar = Buffer1(Counter)
        Counter = Counter + 1
      End If
        
    Loop Until Temp >= &H100
     
    TempIt = LShiftLong(Buffer1(Counter), 8) Or Buffer1(Counter + 1)

    Counter = Counter + 2
    Temp2value = 0
    Do
      
      If Temp2value <> 0 Then
        Temp2value = Temp2value - 1
        Temp = Temp2(Temp2value)
      Else
        Temp = TempIt
        TempIt = TempIt - 1
        If Temp = 0 Then Exit Do
  

        Temp = Buffer1(Counter)
        Counter = Counter + 1

      End If
      TempChar = Temp1(Temp)
      If Temp = (TempChar And &HFF) Then
        Buffer2(Count2) = Temp
        Count2 = Count2 + 1
      
      Else
        Temp = Temp4(Temp)
        Temp2(Temp2value) = Temp
        Temp2(Temp2value + 1) = TempChar
        Temp2value = Temp2value + 2
      End If
  Loop
  
  Loop Until Counter >= UBound(Buffer1) + 1
  
  Else ' maxblock
  ReDim Buffer1(32768 - Abs(BlockSize) - 1)
  Get MyFile, , Buffer1
  For t = 0 To (UBound(Buffer1))   Buffer2(Count2) = Buffer1(t)
  Count2 = Count2 + 1
  Next t
  End If
  
  'YES, I KNOW I SHOULD HAVE USED SOME 
  'COLONEL MEMCOPY BITCHING ROUTINE FOR THAT BUFFER1->2 BIT!!!!!!
  
  Loop Until Count2 >= UnCom
  
  Close MyFile
  ReDim Preserve Buffer2(Count2 - 1)
  
  On Error Resume Next
  Kill dest
  On Error GoTo Hell
  
  MyFile = FreeFile
  Open dest For Binary Access Write As MyFile
  Put MyFile, , Buffer2
  Close MyFile
  DecompressJAFile = True
  
  Exit Function

Hell:
 DecompressJAFile = False


End Function

```

[core.jpg](https://xentaxbackup.github.io/file/573_core.jpg)

[TrainDriver2005.zip](https://xentaxbackup.github.io/file/572_TrainDriver2005.zip)
## Post #13
- Username: Sly
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 04, 2004 6:19 am
- Post datetime: 2006-01-08T13:01:15+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

Well, if you can't write your own code then try to find and RE my unpackers for Guild Wars, Blood Magic and StarForce protected games (Bet on Soldier, etc).
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-08T13:48:17+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

> Reply from Sly
>
> Well, if you can't write your own code then try to find and RE my unpackers for Guild Wars, Blood Magic and StarForce protected games (Bet on Soldier, etc).

You have missed the point of this forum completely, Sly. This forum is not about feeling good about yourself because you can do things others can't (yet), it's about sharing knowledge. 

Coding extractors and stuff, like we do here, is not magic, it just takes some basic skill to do it. If you think you must act like a child who doesn't recieve much attention, so be it.  

But remember one thing, whatever you code, it means nothing. Don't make a big thing about nothing. We certainly don't, we are just here to help out others and have fun at solving puzzles. If we solve it, we post the solution, so others don't have to go through that again. You can see the result at the WIKI. And we are proud of it. 

Have fun at lurking at this forum! Hope you learn something, so you can use it in your own programs, to boast about it at other forums!
## Post #15
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-01-08T16:02:13+00:00
- Post Title: Train Driver 2005 - .ja files (Complete archive attached)

@sly:

all links appreciated for your work
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-08T16:55:46+00:00
- Post Title: 

> Reply from Sly
>
> Well, if you can't write your own code then try to find and RE my unpackers for Guild Wars, Blood Magic and StarForce protected games (Bet on Soldier, etc).

By your comment, thats a huge imply that you are REing those games as you specifically mention Starforce protection.  So don't even say its your own code, I'm sure you ripped out the code for decompression as well.  I just wrote up a pascal implementation of the assembly I saw. I didn't look any further, and I, unlike you, have no problems with giving that credit to you, because, I really don't care.  I could also poke and prick your coding methods as well, and seeing that code in any production code, would be scary.

We only took the decompression method also, i didn't even look into anything else, MrMouse did all the file format jive, I'm not even sure how its structured except for the fact that we found out it errored because it had multiple blocks for decompression.  Oh well though.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-01-08T22:50:08+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Code: Select allOn Error GoTo Hell
Heh, nice humor...  

@ Sly: Grow up, or jack off. Sorry to be so blunt, but that's honestly how I feel.  (Finally, a (bad) excuse to use that... YES!!!!!)
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-09T18:04:15+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Thanks to Rahly's excellent reverse engineering of Sly's attachment (hello Sly, Pespin doesn't protect enough!), we now have the .ja compression solved for the most part.

I can't believe, now we must do also double work!!!
That's really absurd... I think this Sly is totally useless to the community.
## Post #19
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-01-10T16:07:10+00:00
- Post Title: 

[quote=]"I think this Sly is totally useless to the community.[/quote]

not useless but if he dont want to share his tools and knowledges,the work is done twice as he already reversed the schemes.
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-10T17:55:57+00:00
- Post Title: 

> Reply from mambox
>
> 
not useless but if he dont want to share his tools and knowledges,the work is done twice as he already reversed the schemes.

Uhmmmm what part of "try to find" is not clear in what Sly said before?
(try to find is not a synonim of share)

If he wants really to help he should say something like "guys I have found and extracted the instructions which do the decryption/decompression work and have merged them in a tool available here (link), feel free to reverse the code I have ripped since I don't have time or desire to do it".
That means half work not double like now.
## Post #21
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-10T18:29:06+00:00
- Post Title: 

Ok, thats enough guys.
## Post #22
- Username: JDD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 29, 2006 4:18 am
- Post datetime: 2006-12-04T21:21:41+00:00
- Post Title: 

The ja file format is used by TRS2004 and TRS2006 by Auran.
I think some of the files use lzss compression. I can't get Mexcom to work with Trainz ja files though. I must be doing something wrong.

JDD
## Post #23
- Username: Marlboro
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 07, 2006 2:25 am
- Post datetime: 2006-12-06T18:40:21+00:00
- Post Title: 

First of all a big Thanks!

Whoever came up with this marvel is in my book a genius.
I do 3d and some hex but this stuff is way beyond me.

The plug-in works like a charm with Trainz06 but not 04 (no biggy - one can work around that)

The question I have is:
Is there a way to re-pack/compress .ja back using the original format?

Though the game works by substituting .ja with the unpacked folder structure, load times suffer somewhat.

And while I'm at it...Is .ja a proprietary format linked to the game-developer or is it a more widespread compression format like .zip or .rar
(in case one wants to distribute own content based on this format)? 

Thanks for your time
Have fun - Marl
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-12-06T20:19:17+00:00
- Post Title: 

.ja, I believe, is a proprietary format, as are most archive formats that games use.
## Post #25
- Username: JDD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 29, 2006 4:18 am
- Post datetime: 2006-12-06T20:25:54+00:00
- Post Title: 

I believe the ja archive format is a propietary format. I have only seen it used in Auran games. On the Auran Jet website there is some information on the formats used with the Auran Jet engine, which is used in TRS2004.
## Post #26
- Username: Marlboro
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 07, 2006 2:25 am
- Post datetime: 2006-12-06T21:02:23+00:00
- Post Title: 

ok, thanks for the quick and comprehensive answer.
I'll dig into the Jet pages as suggested.

My immediate conclusion would be: no distribution of 3rd party .ja without official permission - right?

But back to the core question...as the file-structure (unpacked)
seems to be documented, how difficult would it be to find a tool to pack again to recover load-times?

Auran provided that kind of tool (ways back) for both (unpack/pack)
alas, it is not suitable for the recent releases.

(since this is the "completed" part of the forum should I better ask in the open section?)

thanks - have fun - Marl
## Post #27
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-13T04:13:43+00:00
- Post Title: 

Hello, I'm new here and have worked with Trainz files previously.  I've written a file and animation viewer for Train IM and PM 3d graphics files previously. 

I stumbled across this thread while trying to figure out how to extract Trainz ja files.  

I downloaded and installed MultiEx commander (which now comes with the ja file dll mentioned in this thread).  As noted above, it does not work with Trainz 2004 ja files.  I do not have any Trainz 2006 files and the original link to the file mentioned in this thread no longer seems to work. 

I can provide some background information.  There was a non-commercial version of the Auran Jet engine -1.0 (Auran Jet engine is the basis for Trainz) , which I worked with for a couple of years.   Current versions of Trainz run on the 2.0 engine.   There was an extraction tool - Jarchive - which came with the 1.0 engine but not with Trainz.  I could kind of get the old extractor to work with Trainz files, but, in short, clearly the version had changed and either the input file and/or output file length had changed.  I know that the number following the header information (after ARCHINFO and OCRA) was almost certainly a version number.  

If I could get the copy of the TRS2006 file I might be able to supply additional details on the differences in the formats, or I would be willing to help someone with more knowledge in compression formats by supplying any helpful information that I can.  

The JArchive.exe program is dependent on DLLs that ship with the various versions of the Auran Jet engine, and I get different results depending on whether I run with the 1.0 or 2.0 versions of those DLLs, though neither method will completely successfully extract the trainz .ja files.  Typically the extraction is correct to a certain point but 'comes up short.'
## Post #28
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-13T14:46:11+00:00
- Post Title: 

Some additional information and a correction: 

There are 4 different versions of Trainz released by the Auran company:  Original Trainz, Ultimate Trainz, TRS2004 and TRS2006.  All are based on some version of the Jet engine.  Train Driver 2005 is based on some version of the Jet engine, but I'm not sure which.  Plus I have the original Jet 1.0 engine installed.

The Trainz .ja files that I have are from Ultimate Trainz, not TRS2004.  

The Jaunp exe that was posted by sly works for the .ja files from the original Jet 1.0 engine (I could already do those with the supplied Jarchive program).  The extracted files appear to be correct, as I can view them with my Jet file viewer. That strikes me as odd, as it implies that Trainz 2006 has reverted to the 1.0 engine version of the ja files or something similar enough to be recognized.  It could also imply that Train Driver 2005 was actually written with the commercial version of the old 1.0 engine, rather than with the 2006 engine.

Jaunp run against Ultimate Trainz .ja files will create the first file, but no data is written and no other files are created. 

MultiEx commander will not work with either the old 1.0 ja files or the Ultimate Trainz ja files.  I get a message box saying "PGN  not valid" and pointing to the Traindriver2005.dll.

I'm not very knowledgeable about compression.  I also don't know VB.  I'm just a C++ programmer.  Does the VB program that was posted reflect the complete algorithm for extracting these files?  If so, I could probably learn enough VB to figure out what's happening and convert it to C++ and see if I can modify it for different versions of the .ja files. 

If there is any interest in pursuing this, let me know what I can provide that would be helpful.  

Thanks
## Post #29
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-14T13:26:04+00:00
- Post Title: 

> DO NOT POST GAME REQUESTS HERE!!! Any new game requests should be posted in the Game Requests forum, not here. Requests for updated support for a game already in this forum should be made in that topic.
I hope I didn't post in the wrong place.  I understand the last sentence above to mean that I should continue in the existing topic in this forum.  If I was wrong, please let me know. 

Anyway, I can supply (nearly) complete documentation for the Jet/Trainz IM (Indexed Mesh) and PM (Progressive Mesh) 3D files, if you would like to have them.  There was already documentation for the original files in the 1.0 version of Jet; all I have added is the layout of subsequent versions of those files.  It will take me a few days as they exist programmatically, but not formally at the moment.  Let me know.
## Post #30
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-16T01:36:20+00:00
- Post Title: 

Well, I guess there's not much interest in this, so I'll drop my requests.  

I figured out how to extract the new Trainz .ja files by switching around a few fields and making them look like the original Jet. 1.0 ja files and then running the supplied jarchive program against them, but that still doesn't tell me anything about the actual compression method internally.  

I've learned a few more things about the files and how they are set up, and I could very easily supply a source .ja file AND the extracted files if anyone wants to look at them, but I think first I better ask on the Trainz forums and see if this is allowable.  I have a feeling it may not be and I don't want to violate anyone's licensing restrictions.
## Post #31
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-01-16T15:33:03+00:00
- Post Title: 

it could help much more to search on a dedicated forum.

such place is imho better for unknown formats.

well,my 0.2$
