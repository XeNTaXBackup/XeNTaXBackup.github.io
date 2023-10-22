## Post #1
- Username: devomako
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 26, 2019 10:19 pm
- Post datetime: 2019-10-26T14:35:06+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

Hoping someone can help me extract some stuff from this format, searching online hasn't brought in any results haha

Basically from what I can tell everything from looking at sizes and the names, every separate part of the game has a .DATA file and they contain all the parts for those areas, the programming (i assume), the models, textures, etc (minus the sound since that's a wwiseaudio thing) however I can't seem to get a grasp on the format itself since there's no reference of .DATA stuff online

If someone can look into it and help me with this it'd be great, here's the global .DATA file that I assume has stuff in it for base level stuff like UI, Luigi's stuff, etc
[https://drive.google.com/open?id=1wJkkG ... pdLNcJhWaf](https://drive.google.com/open?id=1wJkkG00lxoJcU7DfHtmIuLpdLNcJhWaf)
## Post #2
- Username: deschamps12
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 05, 2018 11:40 pm
- Post datetime: 2019-10-27T04:17:10+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

Did you need new keys to extract the xci for this? Trying to take a look at it but can't seem to extract. Will let you know if I get anything from the DATA file though
## Post #3
- Username: devomako
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 26, 2019 10:19 pm
- Post datetime: 2019-10-27T05:55:03+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

I got my keys from the /hbg/ discord since if I need something quick it's easier then dumping my own and those seemed to work fine, so I assume since those are probs newest firmware then that might be the reason? I'm not sure though
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-10-27T08:33:47+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

From what I can tell, the .data is compressed, the .dict file that's alongside them is the file location in the .data, which also tells the size of the file, offset location, and folder path? Seems to be hashed from a quick glance at the files from my dump.
## Post #5
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2019-10-27T13:47:03+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

I have extracted the global.data file with offzip and got an file called 0adfc330.sdb which contains model data. I'm currently trying to extract it with hex2obj/advanced mesh reaper...
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-10-27T13:59:38+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

Have you got the .dict file as well?  There are a few thousand files in that .data archive by the look of it.
## Post #7
- Username: devomako
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 26, 2019 10:19 pm
- Post datetime: 2019-10-27T14:08:09+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

[https://drive.google.com/open?id=12YYCh ... LQShDz0x3X](https://drive.google.com/open?id=12YYChNlSMyw_XKTYbIJ7zsLQShDz0x3X)

Here's the dict file
## Post #8
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2019-10-27T14:28:53+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

I now have gotten the mesh although it seems not correct.
[lm3.PNG](https://xentaxbackup.github.io/file/16953_lm3.PNG)
## Post #9
- Username: gilsongbj
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 08, 2017 3:34 am
- Post datetime: 2019-10-27T18:44:46+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

I found this on the internet. I don't know if it will help you

[https://gist.github.com/RoadrunnerWMC/f ... 6ee73eaa9f](https://gist.github.com/RoadrunnerWMC/f4253ef38c8f51869674a46ee73eaa9f)
## Post #10
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-10-27T21:10:15+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

that is for Dark Moon, that will most likely not help for us lol
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-10-27T23:30:55+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

You can use this QuickBMS script to extract and decompress the data - not sure yet how the filenames/folders are stored in the first table in the .DICT file so there's no proper filenames yet.


# Luigi's Mansion 3 - .dict extract
# By Dave, 2019
# Needs to be in same folder as global.dict, global.data, global.debug and global.nxpc

ComType zlib

Goto 0x0c
Get ENTRIES2 byte
Get ENTRIES1 byte
Get ENTRIES3 byte

XMath FILE_TABLE "(ENTRIES1 * 0x18) + 0x10"
XMath TEXT_TABLE "FILE_TABLE + (ENTRIES2 * 0x10)"

# Open data files

Goto TEXT_TABLE

For A = 1 to ENTRIES3

	Get JUNK byte
	Get DATA_FILE String
	Open FDDE DATA_FILE A

Next A


# Read file table entries

Goto FILE_TABLE

For A = 1 to ENTRIES2

	Get OFFSET Long
	Get SIZE Long
	Get ZSIZE Long
	Get JUNK Byte
	Get JUNK Byte
	Get SOURCE Byte
	Math SOURCE + 1
	Get JUNK Byte
	Set FILENAME "LM3_"
	String FILENAME + A

	If SIZE <> 0
		Clog FILENAME OFFSET ZSIZE SIZE SOURCE
	Endif

Next A
## Post #12
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-10-28T01:18:22+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

> Reply from DKDave ↑Mon Oct 28, 2019 7:30 am at Mon Oct 28, 2019 7:30 am
>
> 
You can use this QuickBMS script to extract and decompress the data - not sure yet how the filenames/folders are stored in the first table in the .DICT file so there's no proper filenames yet.


# Luigi's Mansion 3 - .dict extract
# By Dave, 2019
# Needs to be in same folder as global.dict, global.data, global.debug and global.nxpc

ComType zlib

Goto 0x0c
Get ENTRIES2 byte
Get ENTRIES1 byte
Get ENTRIES3 byte

XMath FILE_TABLE "(ENTRIES1 * 0x18) + 0x10"
XMath TEXT_TABLE "FILE_TABLE + (ENTRIES2 * 0x10)"

# Open data files

Goto TEXT_TABLE

For A = 1 to ENTRIES3

	Get JUNK byte
	Get DATA_FILE String
	Open FDDE DATA_FILE A

Next A


# Read file table entries

Goto FILE_TABLE

For A = 1 to ENTRIES2

	Get OFFSET Long
	Get SIZE Long
	Get ZSIZE Long
	Get JUNK Byte
	Get JUNK Byte
	Get SOURCE Byte
	Math SOURCE + 1
	Get JUNK Byte
	Set FILENAME "LM3_"
	String FILENAME + A

	If SIZE <> 0
		Clog FILENAME OFFSET ZSIZE SIZE SOURCE
	Endif

Next A

does the debug and nxpc files dump separately or are they inside a file, cause I'm not seeing a single instance of those two files in the game except for the reference in .dict
## Post #13
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-10-28T10:16:50+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

same with me, I only got .data and .dict from unpacking the romfs.
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-10-28T16:46:44+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

I just dumped the files in .DICT order.

If you add the line: Print "Source: %SOURCE%" after the Clog line, you can see which archive the files are from (1=.data, 2=.debug, 3=.nxpc)

So, files 59, 60 and 61 are from .nxpc, which looks to be about 500 MB of data.
## Post #15
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-10-30T00:16:27+00:00
- Post Title: [HELP] Luigi's Mansion 3 .DATA file

well I added it, but still no luck on getting those missing files..
## Post #16
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2019-10-30T06:10:50+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

I extracted .dict file with Dave's script but it ends with an error.
I don't have a .debug file and .nxpc file like the others. help...

P.S. I am beginner.
## Post #17
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-10-30T17:08:10+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

I also have problems, and no .DEBUG or .NXPC files in my dump.

```
- open script LM3DICT.bms
- set output folder LM3

  offset   filesize   filename
--------------------------------------
- enter in folder LM3_DMP
- open input file LM3\global.data
- enter in folder LM3_DMP
- open input fileLM3\global.debug

- error in src\file.c line 557: fdnum_open()
Error: No such file or directory

Last script line before the error or that produced the error:
  23  Open FDDE DATA_FILE A
```


Where to find them?
## Post #18
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-10-30T23:51:32+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

use offzip and put offzip -a <.data file> <output path>
## Post #19
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-10-31T05:15:49+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

I know offzip -a on most of the data files work, but I don't get proper names and directories when I do it that way...
## Post #20
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2019-10-31T17:55:32+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

By the way, is text data included in global.data?
Has anyone already found it?
## Post #21
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-11-02T17:38:50+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

Yeah there's text data in that I think.
## Post #22
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-11-02T18:12:30+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

update Switchbox it can open LM3 dict files
## Post #23
- Username: devomako
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 26, 2019 10:19 pm
- Post datetime: 2019-11-03T13:53:17+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

> Reply from Über Winfrey ↑Sun Nov 03, 2019 2:12 am at Sun Nov 03, 2019 2:12 am
>
> 

update Switchbox it can open LM3 dict files

Neat! How are you getting the rigged models though? Exporting from dae from Switch Toolbox doesn't seem to provide the rig itself
## Post #24
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2019-11-04T07:27:19+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

toolbox.png (62.63 KiB) Viewed 150 times


How can I extract files with toolbox?
## Post #25
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-11-05T18:24:18+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

> Reply from yham ↑Mon Nov 04, 2019 3:27 pm at Mon Nov 04, 2019 3:27 pm
>
> 
toolbox.png
How can I extract files with toolbox?
You open a .dict file and right click on the model folder and click export
## Post #26
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-11-05T18:25:29+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

> Reply from devomako ↑Sun Nov 03, 2019 9:53 pm at Sun Nov 03, 2019 9:53 pm
>
> 
Über Winfrey wrote: ↑Sun Nov 03, 2019 2:12 am

update Switchbox it can open LM3 dict files


Neat! How are you getting the rigged models though? Exporting from dae from Switch Toolbox doesn't seem to provide the rig itself

I rigged them manually
## Post #27
- Username: nanodrummer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 21, 2020 7:07 am
- Post datetime: 2021-10-20T02:38:44+00:00
- Post Title: Re: [HELP] Luigi's Mansion 3 .DATA file

> Reply from yham ↑Fri Nov 01, 2019 1:55 am at Fri Nov 01, 2019 1:55 am
>
> 
By the way, is text data included in global.data?
Has anyone already found it?

Have you found the text files?
I extracted “global”, but everything seems encrypted
