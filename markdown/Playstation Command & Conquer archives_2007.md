## Post #1
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2006-07-27T21:22:37+00:00
- Post Title: Playstation Command & Conquer archives

On the PS command & Conquer CD's there's always a DATA.FAT and a DATA.MIX

I know the DATA.FAT is the offsets table for the (large) DATA.MIX, and I figured out how to get the starting offset for the files, but I can't figure out how to get the ending offset...

The problem is, all file offsets are multiplications of 0x800.
This means files are padded with 0x0 bytes until the next multiplication of 0x800 where the next file can start.

The FAT file has the following format:
-[pre]: 8 bytes, of which only the first four seem to have any important data
-the filename, just plain text, ended by 0x0
-the structure is filled to 28 bytes, with the last four (which I refer to as [post]) giving the offset, but divided by 0x800

The bytes between the filename and the [post] part seem to have no importance. They're usually 0x0 bytes, although there's some places where there is some junk text in it.


I know that the offset == [post]*0x800 (2048 dec) but I can't seem to find any relation between [pre] and the length.
I COULD just cut off all trailing 0x0 bytes, but that seems a bit unsafe. Some files like colour palettes could indeed end on 0x0 bytes, since they have colour values and a fixed length.

This is my study so far, using 2 consecutive files as study objects:


"MISSION.ENG"

pre:
0C 01 00 00 00 00 00 00
filename: (padded with 0x0 bytes for 8.3 format)
4D 49 53 53 49 4F 4E 2E 45 4E 47 00
post:
00 00 00 00 B0 06 00 00

[pre]: 0C 01 00 00 = 0x010C = [268]
[post]: B0 06 00 00 = 0x06b0 = [1712]

From DATA.MIX:
address "mission.eng" = [1712]*2048
Length  "mission.eng" = 20441 (+39 bytes 0x00)


"MISSION.FRE"

pre:
D9 4F 00 00 00 00 00 00
filename:
4D 49 53 53 49 4F 4E 2E 46 52 45 00
post:
00 00 00 00 BA 06 00 00

pre:  D9 F4 00 00 = 0xF4D9 =[62681]
post: BA 06 00 00 = 0x06bA  = [1722]

From DATA.MIX:
address "mission.eng" = [1722]*2048
Length  "mission.eng" = 22109 (+419 bytes 0x00)


I don't know if any of you can help me figure this out... the problem is the extraction tool I got now ([Red Alert Retaliation Extractor](http://ra.afraid.org/html/downloads/utilities-3.html)) only seems to extract about half of the files, AND for some odd reason only reads the extensions from the FAT file and just gives numbers as filenames.

I started by writing a tool to fix the filenames in PASCAL, which works perfectly but showed me that the RA Ret Extractor didn't extract all files.
(It bases itself on the log file created by the Extrator program, but due to a bad count bug in my proggie the renaming went 2 files beyond the number of files in the log and showed me the .FAT had in fact more filenames than there were extracted files)

So I want to write a better extractor... but to do that I need that EOF offset.

I could decompile the orginal proggie perhaps... I tested the program with an edited .mix file, and it doesn't seem to just cut off all trailing zeroes. Though I've never done decompiling before.
[DATA.zip](https://xentaxbackup.github.io/file/779_DATA.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-29T21:00:22+00:00
- Post Title: Playstation Command & Conquer archives

Hi, nice little problem you got there. Are you sure you got the format of the FAT file right? I see that the filenames in there are really just 12 in length at max, standard DOS lengths actually, 8 for the name and 4 for the dot plus file extension. Then come some other variables, some of which increment as you go through the FAT. This is probably not junk.
## Post #3
- Username: Nyerguds
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jul 28, 2006 4:48 am
- Post datetime: 2006-07-30T09:26:41+00:00
- Post Title: Playstation Command & Conquer archives

Well it might be that the 28 bytes are split up in 4/4/12/4/4, but there's a problem with that...

See, on the Red Alert Retaliation (Allied CD), just behind the first filename there's a 0x00 and then the string "oClass"
It's totally random to have that string there compared to the C&C GDI FAT file, that's why I thought it'd be best to ignore it... especially since it joins the filename and the 4 bytes just behind it. It seems like the format might just be 4/4/16/4, with indeed just some random junk behind the filename to fill up the 16. I can't imagine a string like 'oClass' coincidently appearing in binary information.

pre1:
44 01 00 00
pre2:
2E 00 00 00
"WARN1.TIM" / 0x00 / "oClass"
57 41 52 4E 31 2E 54 49 4D / 00 / 83 55 9F 06 B0 A0
post:
00 00 00 00

(Pre2 is usually empty, but not always... I should look deeper into possible meanings of this)

The fact I saw it as random junk was also because the 2 files I took as study objects didn't have it at all. This means that that data doesn't increment... the first file has some of that 'junk', and these 2 later files don't.

I didn't even intentionally take 2 files with nothing but zeroes behind the filename - I just chose them because they are text files, which makes it easy to find them in the big file with nothing but a simple text search.

But I thought the fact those 2 files really only have zeroes there 'd prove it has nothing to do with the file size.

Well, I'm stumped... 


I attached the list of files the extractor program managed to extract, with their lengths... could be useful. (Why can't I attach bare .txt files?)
[data_len.zip](https://xentaxbackup.github.io/file/782_data_len.zip)
