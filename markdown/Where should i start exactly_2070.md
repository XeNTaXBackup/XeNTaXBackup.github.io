## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-03T19:04:56+00:00
- Post Title: Where should i start exactly?

OK for the past 2 or so days I have been learning Visual Basic 6.0, and I have made much progress (thanks to Strobe of course).
I have completed my 1st SIMPLE application which does nothing except VIEW bmp, gif and jpeg images, oh and icons aswell.

Now id like to learn about File extraction or archieve viewers.
I spoke with Strobe about the types of extraction, so i know the pros and cons of both Achiev viewers and Archieve rippers.
IE: solidus is a viewer and Jaeder Neub is a ripper only.

Where do i start on archieve viewers?
I tihnk itd make sense ot start with a SIMPLE archive such as PAK from Doom or ZIP or RAR maybe.
But i have NO IDEA where to start when it comes to viewing the stuff inside them.
like looking at the list. i mean, i can often find out from a HEX VIEWER but thats not help to me when im making the viewer lol.

Please can someone help me.
Im really interested in gettign somewhere in all this as i dont enjoy asking for help from people.
this way i can give something BACK to this site eh.
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-04T02:20:02+00:00
- Post Title: Where should i start exactly?

I suggest to take a look at the flag article on the site:
[http://multiex.xentax.com/](http://multiex.xentax.com/)
Guide To Exploring File Formats 
I it really worth reading as it teaches amazingly well what is this all about. 
Most recommended.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-04T10:49:40+00:00
- Post Title: Where should i start exactly?

> Reply from Xela
>
> I suggest to take a look at the flag article on the site:
http://multiex.xentax.com/
Guide To Exploring File Formats 
I it really worth reading as it teaches amazingly well what is this all about. 
Most recommended.
Yes i have looked at and completed that guide.
But it exaplains how to hack the files with a HEx editor and gather information about what you need ect...
But it doesnt explain HOW to  actually VIEW the inside of the files AFTER you have gained the information about them.
Eg: it explains EVERYTHING about the Quake PAK files and stuff, but it doesnt tell you how if say you wanted to make a viewer of your own the kind of things you would need to take into consideration.
If only i could view a  source code of a viewer in Visual Basic, I have seen much on Jaeder Neub but thatsa ripper, still I have learnt a lot form it thoough.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-04T11:51:55+00:00
- Post Title: Where should i start exactly?

What is it that you want? 

Is this it? 

- Open an Archive
- Show the contents of the Archive to the user. 
  i.e. you wish to play sounds as sound, show graphics as graphics and text as text 

What you need is: 

1. The Archive structure, so you can gain access to the contents of the Archive. This you will need to figure out. If this is not the problem, move on. 
2. Identify which type of files are in the archive. Suppose you know the Archive structure and you could save each file in it. What you're asking is how to identify files as sounds, graphics etc? If this is the case, then Strobe would be one to ask (again) as this is what he does, know how to identify files. Basically, you need to examine each file for features that distinguish them as files of a given format (e.g. JPG, WAV, BMP, DDS etc) . Then write a program that scans each file for these tags. Then, when found, show them using appropriate code. There are many free libraries available on the internet that will play sounds of many types, show graphics of many types etc. These you can call from within your program when appropriate. So, when your scanning code identifies a file within an archive as Microsoft ADPCM (WAV) trigger the right routine to play it. 

Is this what you want ?
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-04T14:10:58+00:00
- Post Title: Where should i start exactly?

> Reply from Mr.Mouse
>
> What is it that you want? 

Is this it? 

- Open an Archive
- Show the contents of the Archive to the user. 
  i.e. you wish to play sounds as sound, show graphics as graphics and text as text 

What you need is: 

1. The Archive structure, so you can gain access to the contents of the Archive. This you will need to figure out. If this is not the problem, move on. 
2. Identify which type of files are in the archive. Suppose you know the Archive structure and you could save each file in it. What you're asking is how to identify files as sounds, graphics etc? If this is the case, then Strobe would be one to ask (again) as this is what he does, know how to identify files. Basically, you need to examine each file for features that distinguish them as files of a given format (e.g. JPG, WAV, BMP, DDS etc) . Then write a program that scans each file for these tags. Then, when found, show them using appropriate code. There are many free libraries available on the internet that will play sounds of many types, show graphics of many types etc. These you can call from within your program when appropriate. So, when your scanning code identifies a file within an archive as Microsoft ADPCM (WAV) trigger the right routine to play it. 

Is this what you want ?
Yes pretty much yes.
Thankyou.
I have written the code for a WAV and MIDI player already by following tutorials and stuff.
SO now its bakc to hexkign to understand it a bit more, then once i understand the file fully in HEX il do what you have said.
Ok thanksyou very mushc Mr Mouse.
But one question: Are there and example VB code for scannign for archieve types?
I already have the one for both TGA conversion and Sony VAG scanning.
But they are rather uncommented and there is a lot of this:

```
Dim VAGByte2 As Byte
Dim VAGByte3 As Byte
Dim VAGByte4 As Byte
Dim VAGByte5 As Byte
Dim VAGByte6 As Byte
Dim VAGByte7 As Byte
Dim VAGByte8 As Byte
Dim VAGByte9 As Byte
Dim VAGByte10 As Byte
Dim VAGByte11 As Byte
Dim VAGByteA As Byte
Dim VAGByteB As Byte
Dim VAGByteC As Byte
Dim VAGByteD As Byte
Dim VAGByteE As Byte
Dim VAGByteF As Byte
Dim VAGByteG As Byte
Dim VAGByteH As Byte
Dim VAGHeader As String * 4
Dim VAGTitle As String * 16
Dim VAGLength As Long
Dim VAGFreq As Long
Dim TimerVAG As Long
```

I have NO IDEA what that means at akk.
Header i GET but thats really where it ends, I assume thats how the MultiEx looks in parts aswell.
AS THATS how all of the Jaeder Neub stuff looks really.
Anyone can help?
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-04T20:10:22+00:00
- Post Title: Where should i start exactly?

Hey! =D Thats code from my Universal VAG Scanner =))))
*giggles*

well..code and code...thats declarations.......=o

and i told you, the UVag scanner is nothing you should look
in the first you do when coding a converter/ripper. it will
just make your head spin. better look at my JPEG ripper,
which i atleast documented 
(and is about 95% shorter in code)

For the interested, the full code for my VAG data detector! 

[http://jaedernaub.ath.cx/FullUvag.txt](http://jaedernaub.ath.cx/FullUvag.txt)

It still has some flaws though, but seems to work on most VAG stuff
without headers.
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-04T21:07:09+00:00
- Post Title: Where should i start exactly?

[quote="Strobe"]Hey! =D Thats code from my Universal VAG Scanner =))))
*giggles*

well..code and code...thats declarations.......=o

and i told you, the UVag scanner is nothing you should look
in the first you do when coding a converter/ripper. it will
just make your head spin. better look at my JPEG ripper,
which i atleast documented 
(and is about 95% shorter in code)
[quote] Yes lol I am looking at that now actually.
Tho any tips of makign a VIEWER.
As now i have the CODE for the Jpeg thing and i already made a Jpeg viewer(VERY SHORT AND LITTLE CODE) any way i can make a viewer for lets say and easy archieve such as "rar" or "Zip"?
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-11T18:57:06+00:00
- Post Title: Where should i start exactly?

I believe I have the GENERAL idea of all of this Hexign and Ripping stuff.
Of course this is all made easier by workign with strobe a lot.

Now I have a RipperCore (90% strobes work) i can add formats to Rip MUCH MUCH easier.
Now i am able ot rip a collection of formats, MOST being Images, but there are also 1 or 2 Audio files in there.
But Im not to fond of the Whole "Rip Everything form the Archieve"job, So i realised that itd be much better If i was able to simply View what files an Archieve Contained, then Extract only the files that I wanted.
THough i am UNSURE where to start on this, I have looked through many Visual Basic Guides,(Why are there so many for .NET but os few for normal VB 6.0?) but I havent found anything that has helped me (I didnt really expect to but it was best to double check).
So would it be possible for someone to create a few lines of Code in VB with comments that would explain ot me where to start and stuff.
Thankyou in Advance everyone who can help.
