## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-02-25T09:18:09+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

What's up everyone,

The games from Starbreeze Studios use XWC container for their audio files. 
Inside the folder Waves_Xenon there are two files: 
Waves_NonStreamed.xwc (75mb)
Waves_Streamed.xwc (484mb)


I've tried several tools, which all claim to have support of the same XWC format from the previous games by the same company, but none of them could open/convert it.

EkszBox-ABX v2.0 (XWC - Darkness, Chronicles Of Riddick:EFBB)
Dragon UnPACKer v5.3.3 Beta (XWC - Enclave, Chronicles Of Riddick:EFBB)
The Chronicles of Riddick XWC Unpacker v1.0 @ ctpax-x.ru

So either the developers updated the XWC format for the most recently released game and the old programs are no longer suitable for the task or maybe I'm not doing something right, which is kinda less likely since the tools are pretty straightforward. 

Uploading the front and end (1mb each) of Waves_Streamed.xwc (cut with FileCutter) as well as the whole thing. 
Someone please take a peek:

[http://jumbofiles.com/i84eku51fom7](http://jumbofiles.com/i84eku51fom7)

[http://jumbofiles.com/cky7s5mpw0gm](http://jumbofiles.com/cky7s5mpw0gm)
## Post #2
- Username: flashfight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 22, 2012 7:48 pm
- Post datetime: 2012-02-25T14:48:28+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

I don't know about the Xbox360 version, but the PC version's .xwc files can be scanned and extracted using Dragon Unpacker's HyperRipper very easily (I used Dragon Unpacker v5.6.2. so it's a slightly updated version)
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-02-25T19:14:33+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

Yeah if you want to extract them unnamed and messy.

Would like more research into this XWC format.
## Post #4
- Username: clauddiu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Aug 26, 2010 1:45 am
- Post datetime: 2012-02-25T22:45:12+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

> Reply from flashfight
>
> I don't know about the Xbox360 version, but the PC version's .xwc files can be scanned and extracted using Dragon Unpacker's HyperRipper very easily (I used Dragon Unpacker v5.6.2. so it's a slightly updated version)

I have tried to extract the music from Waves_NonStreamed.xwc and Waves_Streamed.xwc with no luck with Dragon Unpacker and I always get EOutOfMemory, is there a way to fix this?
## Post #5
- Username: flashfight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 22, 2012 7:48 pm
- Post datetime: 2012-02-25T23:58:39+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

> Reply from clauddiu
>
> flashfight wrote:I don't know about the Xbox360 version, but the PC version's .xwc files can be scanned and extracted using Dragon Unpacker's HyperRipper very easily (I used Dragon Unpacker v5.6.2. so it's a slightly updated version)

I have tried to extract the music from Waves_NonStreamed.xwc and Waves_Streamed.xwc with no luck with Dragon Unpacker and I always get EOutOfMemory, is there a way to fix this?

Maybe it's because you tried to open the xwc archive directly. You need to scan them first with the HyperRipper function (File menu ---> HyperRipper ----> in the formats" tab you click "ogg" ----> in the '"search" tab you choose the xwc file, then "search") and then you can extract everything. Either this is the problem, or it's because you tried with the Xbox version, but the sounds of the PC release extract to perfectly good .ogg files with this method
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-02-26T02:35:34+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

Indeed, since you mentioned that PC version uses Ogg, I was able to easily extract all tracks with Nova Software Extractor (or any other program that can search for ogg will do). 

Worth a note: PC version's Waves_Streamed.xwc is 688mb which is larger than its Xbox360 counterpart, so either console version has less tracks or they put something that takes up less space inside that XWC container. My guess is that it's still ogg, it's just compressed and encrypted, hence it cannot be detected/extracted by the tools we have.

Anyway, there's 850 tracks and it would be nice to have the actual names.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-02-26T05:52:27+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

Wrong


360 is XMA but seems to be of lower quality.
## Post #8
- Username: clauddiu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Aug 26, 2010 1:45 am
- Post datetime: 2012-02-26T08:54:28+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

@flashfight: Thank you for your instructions, I was able to extract the ogg files.
## Post #9
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-03-05T11:22:57+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

I just got the game today and had a peek at these xwc filezzzzzzzzzzz......
Their structure is certainly somewhat reminiscent of the XWC containers from Starbreeze's earlier games, but they've adjusted it a little (from what I can judge, the adjustments they've made were to improve efficiency and practicality, rather than to keep out prying eyes; as many might assume.)

I wrote a script for quickbms just a second ago, cause a dog with shifty-eyes told me I should totally do it. Though, not entirely sure what his motives were...   

```
get NULL longlong
get ASSETS long
math ASSETS += 0x58
goto ASSETS

get FILES long
get NULL long
idstring STRINGS\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0
get NCPOS long	# =next chunk position (ABSOLUTE)
get NULL long
get STRINGTABLE long
get STRINGTBLSZ long
get STRINGTBLSZ_2 long	# same A/A
get NULL long
set DIR long STRINGTABLE
math DIR += STRINGTBLSZ
goto DIR

log MEMORY_FILE STRINGTABLE STRINGTBLSZ

for i = 0 < FILES
	get UNKNOWN long
	get UNKNOWN long
	get FNPOS long
	get OFFSET long
	get SIZE long
	get NULL long
	
	goto FNPOS MEMORY_FILE
	get NAME string MEMORY_FILE
	
	log NAME OFFSET SIZE
next i

```


This was written specifically for the PC version of Syndicate (cause that's the one I own, Jeeves.) And it was subsequently tested on two files: "Waves_NonStreamed.xwc" and "Waves_Streamed.xwc", with no probs @ all.

Didn't bother to test it on any other files, cause these were the only ones ppl seemed interested in. (also I couldn't be bothered)

Anything else, just ask. (nothing sexual, please.)
## Post #10
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-08T06:17:43+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

Holly-shitty-guacamole!! Renikrill you own this b!tch, yo. Totally nailed the task. The script extracts all tracks perfectly all with proper names. Hell da fux yeah! 
The only thing should be noted is that files come out without extension, so .ogg needs to be added  them (or simply use Nova Software Extractor to scan all 850 files and when if finds oggs inside them just save it all as such).

I intend to share this gamerip, so it will surface in "usual places" very soon. Full credit for your top work will be given ofcourse including my badass seal of approval  

Thanks a lot doggy dog!
## Post #11
- Username: ragnar roamer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2012 3:22 am
- Post datetime: 2012-03-15T19:25:26+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

le new poster here 
i was about to follow these steps in order to extract the .XWC
then i noticed you were kindly about to share the rip anyway. Have you got round to doing this yet?

EDIT:
I tried using the above script, however i've never used quickBMS before. the extract seems to execute fine but the resulting files have no extension. I
s there a complete noob tutorial somewhere about how to load a script correctly? Or am i missing something?

thanks in advance guys
## Post #12
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-15T22:01:06+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

Yes you'll find the rip here: <link deleted by moderator>

And you did use QuickBMS correctly, in this case the resulting files don't have an extension, but it is actually Ogg, so what you can do is either manually add .ogg at the end of each file or use a tool that can search for Ogg within other files. 
For example Nova Software Extractor: [http://www.4shared.com/rar/UWa3SvRA/Nov ... or_24.html](http://www.4shared.com/rar/UWa3SvRA/Nova_Software_Extractor_24.html)
Run the program, on a filelist select Ogg only, and scan all those extension-less files. It will find one Ogg per each track, so save them as such.
## Post #13
- Username: ragnar roamer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2012 3:22 am
- Post datetime: 2012-03-16T02:00:19+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

> Reply from MiLØ
>
> Yes you'll find the rip here...

many thanks MiLØ
## Post #14
- Username: dannyz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 01, 2019 2:42 am
- Post datetime: 2019-11-30T18:43:58+00:00
- Post Title: Syndicate (2012) [Xbox360] .XWC

ok, are u guyz still here:)

I want to ask something.

I unpacked xwc and edited them, how can I pack oggs to xwc
