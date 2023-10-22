## Post #1
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-04-10T19:17:39+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T06:38:45+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

Extracted most of the sampledata, they are in Sony VAG format,
I couldn't however determine how the DIR file worked, since the offsets in there seems to not be related to where in the file
the audiodata is. (but im also tired, so i could have done some very silly mistakes)

So the audiodata was bruteforced out of IMG file, with no particular naming scheme, and some wrong rips.
you can do this with JaederNaub, load the file, and press UVAG 1.0 button and it should rip most of the sounds out,
until i figured out a proper way to do this.

VAG Files can be replayed with in_cube.dll plugin for WinAmp.

Some of the extracted VAGS: [http://lmao.rotfl.at/upload/Str0be/vags.zip](http://lmao.rotfl.at/upload/Str0be/vags.zip)

The chattering voices are specifically included in there because JaederNaub extracted them at the wrong Samplerate, fixed after rip.
The mainreason why this is hard currently is because the VAGs in the IMG file are headerless, so i dont really know where they begin or end without properly interpreting the DIR file,
but the UVAG bruteforcer seems to do a pretty good job atleast.
## Post #3
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-05-17T17:46:14+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

> Reply from Strobe
>
> Extracted most of the sampledata, they are in Sony VAG format,
I couldn't however determine how the DIR file worked, since the offsets in there seems to not be related to where in the file
the audiodata is. (but im also tired, so i could have done some very silly mistakes)

So the audiodata was bruteforced out of IMG file, with no particular naming scheme, and some wrong rips.
you can do this with JaederNaub, load the file, and press UVAG 1.0 button and it should rip most of the sounds out,
until i figured out a proper way to do this.

VAG Files can be replayed with in_cube.dll plugin for WinAmp.


Some of the extracted VAGS: http://lmao.rotfl.at/upload/Str0be/vags.zip

The chattering voices are specifically included in there because JaederNaub extracted them at the wrong Samplerate, fixed after rip.
The mainreason why this is hard currently is because the VAGs in the IMG file are headerless, so i dont really know where they begin or end without properly interpreting the DIR file,
but the UVAG bruteforcer seems to do a pretty good job atleast.

Thanks for your help please keep this post up here so I can do this later. right now i'm on a different computer and I dont want to install anything on it. VAG files I can convert to wav with MFAudio pending that they dont require any interleave or offset numbers unless you know the right settings. I was successful with the music as thgat used 10 bytes interleave but I'm not exactly sure. I would like to try those same numbers with the original BIN files and maybe I can simply run it thru MFAudio with those numbers and make 1 long WAV file of all the chatter vs spending hours converting thousands of files to wave. such as in the MUSIC.WAD files in the tony hawk series of games which convert into a really nice long WAV file that I can chop up into individual wavs.
## Post #4
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-05-17T17:54:40+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

BTW strobe can you post a link to the program that was used to extract the files from the Bully scream IMG file? I would like to do this on my PC. I will DL the file you linked above of the VAGs.

I have another issue with another game its the Driver3.IMG file from the PS2 game driv3r but thats another topic unless I can talk about it here? I posted the Driv3r issue on a dozen forums and I havent heard anything from it, I even included detailed descriptions and pics of what shows up in explorer.

Thanks again.
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-17T22:19:45+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

Cheers! 
Tool for extraction [http://www.jaedernaub.com/JaederNaub2.1.6a.zip](http://www.jaedernaub.com/JaederNaub2.1.6a.zip)
(new version uploaded today, hopefully i didnt break anything that previously was working)
File/Load File, press "Load into Jaeder Naub", then press UVAG 1.0 on the mainscreen, and it will scan the file for VAG data, and then slap a proper VAG header ontop of
everything it finds. this technique is though a last resort as it can miss some things.
But its the best i have until i can extract the archive properly.

and sure, post the other IMG file here and i can take a look at it
## Post #6
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-05-19T00:22:16+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

> Reply from Strobe
>
> Cheers! 
Tool for extraction http://www.jaedernaub.com/JaederNaub2.1.6a.zip
(new version uploaded today, hopefully i didnt break anything that previously was working)
File/Load File, press "Load into Jaeder Naub", then press UVAG 1.0 on the mainscreen, and it will scan the file for VAG data, and then slap a proper VAG header ontop of
everything it finds. this technique is though a last resort as it can miss some things.
But its the best i have until i can extract the archive properly.

and sure, post the other IMG file here and i can take a look at it

Thank you very much for posting that I'll dl it when I get internet on my PC but for right now I'll download it to a flash drive as I'm not on My own PC. There is a problem uploading the other IMG file. its about 3.6 GB in file size so unless theres a file host out there that can handle that big of a file I dont know of any way to open this file. I believe its a game resource archive and all the games info (sounds, music, etc.) is inside this file and I want the sound effects and music. There are some new file hosts but I tried uploading to them and it said uploading but nothing was moving. I could try again some time or I can say get a used copy of this game for the PlayStation 2 and put it into your DVD drive on your PC and it's the DRIVER3.IMG file on the disc.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-19T04:14:48+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

I now have the Driver3.IMG file. its huge )))
Ill make some tests and see what i can find.
## Post #8
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-05-19T20:45:29+00:00
- Post Title: Bully PS2 Scream.IMG files Can they be extracted?

> Reply from Strobe
>
> I now have the Driver3.IMG file. its huge )))
Ill make some tests and see what i can find.

Thanks alot and good luck. I hope there is some way to break into that file and see whats inside. I bet its simply an archive file with everything in it and all that's needed is the right program that can read it and break it into individual folders. if you can do that, that would be so awesome I would ram that "thank post" button a million times if I could but it only lets u do it once.

Another project for down the road.

 I have some PAK files from GTA San andreas on the PS2 but I'll save that for another time. BTW I tried the prog you linked and it did get all the VAG's out of the img files but I cant change any settings (interleave, offset, sample rate, channels Etc.) when I load it into MFAudio why is that? 

Thanks so much.
