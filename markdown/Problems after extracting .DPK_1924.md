## Post #1
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-27T21:02:00+00:00
- Post Title: Problems after extracting .DPK

Hey there,

I'm been trying to extract the Project Earth (Starmageddon) .DPK file for awhile and stumbled across these forums and found a relavant post:
([here](http://forum.xentax.com/viewtopic.php?t=573&highlight=starmageddon))

Which is great - very useful. Except that MultiEx crashes when extracting unless I use only the dpk_com.bms - and once extracted the files that were readable, look like plain gibberish now. So I have a couple of Questions:

How can you tell which files are zlib'd with respect to using the 2 different BMSs?

and...(assuming that this isn't solved by answering the first question)

Is there any way to "un-gibber" some of these files?

Thanks in advance
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-27T22:26:46+00:00
- Post Title: Problems after extracting .DPK

Wow, old subject, two years ago! 

Anyway, I'm not sure what the problem is. Could you upload an example archive? If files are not compressed, and they are gibberish to you, it depends. What is your knowledge of file formats?
## Post #3
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-27T23:25:40+00:00
- Post Title: Problems after extracting .DPK

The problem with Starmageddon (I'll use this name as it was the Amercanized one and thus prolly the most well-known) is that it is all one big-ass .DPK

I know somewhat about file formats - I just wasn't paying very much attention when I was opening files from inside the MultiEx window so I couldn't tell you which ones I tried and got visable text from (though it wasn't silly things like .pngs or .oggs or other image or audio formats) - I was looking at the object class files and etc - things which I SHOULD be able to read. (like .inc and .inv files - as I'm fairly certain I got something out of those before - but the .inv files look just like any other hex file, albeit a very short one - I'll add one anyhow).

Of course, I could be horribly confused and mistaken - which wouldn't be for the first or the last time, no doubt 

In short, I'm looking to muck about with things like costs of objects in the game and build-times (if that isn't directly related to the cost).

btw - I study Comp. Sci. w/ Games Dev at Uni so if it's about computers and I don't know it (and there's an awful lot I haven't a clue about, I'll be the first to admit; I should pick it up pretty quickly) 
[UEF.zip](https://xentaxbackup.github.io/file/752_UEF.zip)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-28T05:52:44+00:00
- Post Title: Problems after extracting .DPK

Well, the files you sent are clearly Zlib compressed. I do not understand why the script did not decompress them. They should be decompressed by MexCom with that first script. 

In the meantime, you can open them as Utils - ZLib files (look it up in the file type list). If you don't see the files, just type *.* in the filename box to show all files (it will only show .zlb files). You will then open the compressed file as an archive containing one file (uncompressed.bin). This is not very handy, I know, but I can't tell from a distance what goes wrong. 

Perhaps you could upload the log from MexCom? Just start it, use the first script on the file and extract all. you say it will crash, perpaps MexCom has logged something useful. Just hit CTRL-L in MexCom to show up the log. It's in the data folder (debug.log).
## Post #5
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-28T10:58:27+00:00
- Post Title: Problems after extracting .DPK

Okay, I used the "dpk" BMS and as usual it stopped, told me it couldn't decompress (not sure what files cause it to trip up) and then mc32 gives me "runtime error 5".

Anyhow - log included and I appreciate the help 
[debug.zip](https://xentaxbackup.github.io/file/753_debug.zip)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-28T11:25:31+00:00
- Post Title: Problems after extracting .DPK

Ok, that wasn't much use, I guess MexCom crashed before it logged anything. Which is weird though, cause it should. Do you see the files in the archive listed? If so, try extracting just those two files you uploaded before.
## Post #7
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-28T12:04:29+00:00
- Post Title: Problems after extracting .DPK

I just did a search for all things in the .dpk that when Species\Inventions\UEF (as the 2 files from before were in there) and it crashed on me - but I noticed that it crashed on files in Species\Inventions\UEF\Restore which contains 8 .SPEC and 5 .obj files - each about 1KB big.

Those 2 files from before extracted fine on their own though.

Seeing this I just decided to try extracting the entire file using the "dpk" BMS and decompression fails on Objects\Shapes\DAM_OFFS.png.

I've included the files in Restore and also DAM_OFFS.png.
[Restore.zip](https://xentaxbackup.github.io/file/754_Restore.zip)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-28T20:46:37+00:00
- Post Title: Problems after extracting .DPK

the reason it fails on the PNG is because it isnt packed.
its a normal png image...!  try open it in photoshop.
## Post #9
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-28T21:38:47+00:00
- Post Title: Problems after extracting .DPK

So... I'm going to have to find out via trial-and-error what parts are packed and what aren't before I run the extractor? That's gonna take awhile
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-29T05:03:23+00:00
- Post Title: Problems after extracting .DPK

Well, probably a lot of files are packed. But when I have the time I'll download the demo (again) and see for myself. Like my original post stated, for some reason some files are left unpacked.
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-29T09:55:04+00:00
- Post Title: Problems after extracting .DPK

I could only guess that the files that had
a too low compression ratio was left as they where.

especially som PNG files, as these allready have internal
compression .....=o
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-29T10:10:12+00:00
- Post Title: Problems after extracting .DPK

Like I said in 2004:

> The *.DPK format uses ZLib compression on most, but not all resources (for reasons unbeknownst to me, ZLib probably did not achieve enough compression on some files, or it was just a sloppy employee at work).
## Post #13
- Username: SleepingLyric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 28, 2006 4:53 am
- Post datetime: 2006-05-29T11:35:56+00:00
- Post Title: Problems after extracting .DPK

Okay - I'll get to working out which files are compressed and which aren't.

Thanks for your help, both of you. I greatly appreciated it. I just guess I'll have to stop being a lazy student bum now, eh?
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-29T12:24:02+00:00
- Post Title: Problems after extracting .DPK

Well, it's also pretty lame that MultiEx Commander dares to crash if the decompression fails. That should be forbidden by law. So, I'll fix that.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-29T19:30:38+00:00
- Post Title: Problems after extracting .DPK

Okay a work-around. 

Two scripts, one to get the compressed ones, the other for the uncompressed ones.
[dpk_bms.zip](https://xentaxbackup.github.io/file/755_dpk_bms.zip)
