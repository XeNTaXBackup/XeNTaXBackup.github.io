## Post #1
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T15:10:06+00:00
- Post Title: Just Cause *.ARC file decompression

So I'm trying to decompress Just Cause's *.ARC archives, with no luck at all. It seems like both of Mr.Mouse's plugins do not work for me. If anyone has any suggestions for me, that would be great.

(P.S. Has anyone else noticed the word SARC at the header of these files? That would seem to be the original archiver, but google searches come back fruitless.)

[Here](http://www.sendspace.com/file/hu03y3) is the entire file, as pictured below.
[sarc.jpg](https://xentaxbackup.github.io/file/2890_sarc.jpg)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-28T16:49:07+00:00
- Post Title: Just Cause *.ARC file decompression

why not post a file here so people can look at it.
## Post #3
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T16:53:37+00:00
- Post Title: Just Cause *.ARC file decompression

Because it's ~56MB. And isn't the header good enough?
## Post #4
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-03-28T17:31:49+00:00
- Post Title: Just Cause *.ARC file decompression

Is there talk about depacking it for to translate it? If this is so, i'm joining for research too, and can upload head and tail for file archive. and if it won't help and wudbe neccessary will upload full archive but no more than 60mb
## Post #5
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T17:40:22+00:00
- Post Title: Just Cause *.ARC file decompression

> Reply from Gocha
>
> Is there talk about depacking it for to translate it?

Huh?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-28T17:51:34+00:00
- Post Title: Just Cause *.ARC file decompression

post the first 10 mb or just upload the 56mb file to sendpace.com
## Post #7
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T17:53:24+00:00
- Post Title: Just Cause *.ARC file decompression

> Reply from chrrox
>
> post the first 10 mb or just upload the 56mb file to sendpace.com

Well, ok.

EDIT: It's uploading right now, I'll make another post with the link, and link to it in the OP.
## Post #8
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T18:32:38+00:00
- Post Title: Just Cause *.ARC file decompression

Ok, [here is the file.](http://www.sendspace.com/file/hu03y3)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-28T20:48:00+00:00
- Post Title: Just Cause *.ARC file decompression

and here is the script see that was easy 

```
get NSIZE long
getdstring name nsize
get offset long
get size long
if NSIZE == 0
cleanexit
endif
log name offset size
next i

```
## Post #10
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T20:52:36+00:00
- Post Title: Just Cause *.ARC file decompression

Actually, I don't even know where I am supposed to put these "scripts". Could you tell me how to do this?
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-28T20:55:44+00:00
- Post Title: Just Cause *.ARC file decompression

save this as a text document and use quickbms.
[lave_041_body.PNG](https://xentaxbackup.github.io/file/2895_lave_041_body.PNG)
## Post #12
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T21:00:49+00:00
- Post Title: Just Cause *.ARC file decompression

Save the picture? Then what's QuickBMS? I don't see that in the BMS menu.
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-28T21:03:36+00:00
- Post Title: Just Cause *.ARC file decompression

here is the tutorial section with bms guides in it.
[viewforum.php?f=29](http://forum.xentax.com/viewforum.php?f=29)
but all you need to do i save my code as a text file
then download quickbms [http://aluigi.altervista.org/papers.htm#quickbms](http://aluigi.altervista.org/papers.htm#quickbms)
double click it and follow the on  screen prompts
## Post #14
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T21:12:48+00:00
- Post Title: Just Cause *.ARC file decompression

Ok, I saved your picture as a text file and used quickbms on it, it said

> Reply from QuickBMS
>
> 
Error: invalid command "IHDR" or arguments 0 at line 4

I'm still confused why you tell me to use this on a PNG picture.

EDIT: Ah, nvm. I had to use the text that you gave me, rather than that picture. Why did you upload a picture?

EDIT2: And are there any ways of repacking after you edited?
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-28T23:45:50+00:00
- Post Title: Just Cause *.ARC file decompression

Sorry but this thread gave me quite a laugh
## Post #16
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-28T23:49:40+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from OrangeC
>
> Sorry but this thread gave me quite a laugh

Well, I suppose that means I'm going to have to ask you why.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-29T00:04:10+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Im guessing that picture lol. not taking the piss out on you mate, just thought it was funny.
## Post #18
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-29T00:08:43+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from OrangeC
>
> Im guessing that picture lol. not taking the piss out on you mate, just thought it was funny.

Ah  At the time, I thought it could analyze the picture for a certain pattern, then extract all of the other files. Just a guess.
## Post #19
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-30T22:11:48+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Well, I would kind of like extraction and addition support for ARC archives, so I'm kind of hoping the current plugin can be fixed and/or updated.
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T05:50:38+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Okay, I need to know anyway what is going on, and why that plugin doesn't work. Can't make any promises on updating an arc though.
## Post #21
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-31T19:06:36+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Well, I can't really help you with either of those. I posted a log either in this thread or the other one I'm posting in, but that's about all I can offer. If you want my opinion, I think in may be a library you included that we don't have. I was looking through the DLL file with a hex editor, and noticed some references to a C:/WINXP folder, which I have never seen before.
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T19:26:18+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Try copying the zlib.dll from the MultiEx Commander folder to the arc plugin folder where there is also the plugin.
## Post #23
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-03-31T19:43:23+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Similar result, and I tried both the normal extractor, as well as Zlib.
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T20:13:19+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Well, I'll have to download an example file.
## Post #25
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-01T00:46:22+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Mr.Mouse
>
> Well, I'll have to download an example file.
[](http://www.sendspace.com/file/hu03y3)
## Post #26
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-01T20:20:39+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Soo, any ideas?
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-04-01T20:35:33+00:00
- Post Title: Re: Just Cause *.ARC file decompression

I have not yet got an example file.
## Post #28
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-01T21:14:34+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Mr.Mouse
>
> I have not yet got an example file.

I just gave you a link in my second to last post. The reason it's a smily face is because the same link is on the first page as well
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-04-02T20:36:27+00:00
- Post Title: Re: Just Cause *.ARC file decompression

I tried it on the original game and I could open the archives. 

```
22:33:56[i]- Archive process format  PGN
22:33:56[i]- PGN Calling 
22:33:56[i]- PGN Register  Just_Cause.dll
22:33:56[i]- PGN Connect  Just_Cause.archive
22:33:56[i]- PGN Info  Just Cause .ARC and SARC Extractor version 1.0, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
22:34:01[i]- Evaluating archive contents 

```
## Post #30
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-02T20:44:00+00:00
- Post Title: Re: Just Cause *.ARC file decompression

Did you try it on that file, though?
## Post #31
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-11T20:13:42+00:00
- Post Title: Re: Just Cause *.ARC file decompression

does anyone know how to convert a little-endian file into a big-endian file i want to replace Ricos model but the pc versions are little-endian and don't work all dds files work fine they don't need to be big-endian it seems.

if your wondering the tools for the PC version work on the 360 version but alot of the files are unknown also you need a Jtaged 360 or hacked dvd firmware to use mods.

any help/info would be much appreciated thank you.
## Post #32
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-11T22:57:44+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Rocky5
>
> does anyone know how to convert a little-endian file into a big-endian file i want to replace Ricos model but the pc versions are little-endian and don't work all dds files work fine they don't need to be big-endian it seems.

if your wondering the tools for the PC version work on the 360 version but alot of the files are unknown also you need a Jtaged 360 or hacked dvd firmware to use mods.

any help/info would be much appreciated thank you.

I think it's best if you made your own topic for that. I'm still waiting for my answer in this one.
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-12T00:14:38+00:00
- Post Title: Re: Just Cause *.ARC file decompression

you need to map out every part of the file and what it does to reverse the endian of a file.
## Post #34
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-12T01:40:07+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from chrrox
>
> you need to map out every part of the file and what it does to reverse the endian of a file.
Chrrox, can you maybe help me with my problem?
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-12T01:50:00+00:00
- Post Title: Re: Just Cause *.ARC file decompression

you would need to reverse the exe to see how the data is accessed i do not know how to do this
## Post #36
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T08:05:18+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from tgperson
>
> I think it's best if you made your own topic for that. I'm still waiting for my answer in this one.Are you looking for .arc extraction or something else? This is the first time I've written a BMS script.

```

endian little

get header_count long 0

# block alignment
if header_count > 1
	get block_alignment long 0
else
	set block_alignment 2048
endif

# archive count
if header_count > 2
	get archive_count long 0
else
	set archive_count 1
endif

set header_size header_count
math header_size *= 4

get file_count asize
math file_count -= header_size
math file_count /= 12

print "Alignment of %block_alignment%."
print "%archive_count% archives."
print "%file_count% files."

print "Getting %archive_count% archive sizes..."
set total_block_count 0
for i = 0 < archive_count
	get archive_path basename
	String archive_path += i
	String archive_path += ".arc"
	open FDSE archive_path 1
	
	get archive_block_count asize 1
	math archive_block_count /= block_alignment
	math total_block_count += archive_block_count
	
	putarray 0 i total_block_count
	print "%total_block_count%"
next i

print "Getting %file_count% file entries..."
for i = 0 < file_count
	get entry.name_hash long 0
	putarray 1 i entry.name_hash
	get entry.block_offset long 0
	putarray 2 i entry.block_offset
	get entry.size long 0
	putarray 3 i entry.size
next i

print "Extracting archives..."
set archive.block_offset 0
for i = 0 < archive_count
	get archive.path basename
	string archive.path += i
	string archive.path += ".arc"
	
	print "Extracting archive %archive.path%..."
	open FDSE archive.path 1
	
	getarray archive.block_count 0 i
	
	for j = 0 < file_count
		getarray entry.block_offset 2 j

		if entry.block_offset >= archive.block_offset		
			if entry.block_offset < archive.block_count
				getarray entry.name_hash 1 j
				getarray entry.size 3 j
				
				get entry.path basename
				string entry.path += i
				string entry.path += "/"
				string entry.path += entry.name_hash
				
				set entry.offset entry.block_offset
				math entry.offset -= archive.block_offset
				math entry.offset *= block_alignment
				
				log entry.path entry.offset entry.size 1
			endif
		endif
	next j
	
	set archive.block_offset archive.block_count
next i

```
To use, quickbms.exe extract_jc1.bms pc.tab extracted or whatnot.

To do filenames you'll need to figure out what algorithm the game is using to hash the names, it isn't Jenkins hashlittle() like Just Cause 2.

I know that "weapons_pc.bin" is hashed to 0xBB02F83B.
## Post #37
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-12T10:21:56+00:00
- Post Title: Re: Just Cause *.ARC file decompression

I think what they want is someone to map all the files out so they can port all the extracted resources from the pc to the xbox.
but very nice script.
## Post #38
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T17:14:18+00:00
- Post Title: Re: Just Cause *.ARC file decompression

sorry i miss read the thread name this was for just cause 2

extraction of arc files is done both using BMS Script and now an actual program [here](http://jc2wiki.info/index.php/Main_Page).

The problem i have is the xbox 360 has Big-Endian coded files  now the PC doesn't well we all know this but dds textures (L-E) work on the x360 so no need to convert but models, bin files and such must be Big-Endian or they wont load when the game is started, hens why i wanted to know how to convert them if possible.

I can give any resources needed (bar rbm files as these are not decrypted in the arc file yet  will need to find them first 18000+ unknown files lol) for some one to see if they can convert the dds (textures) files to big-endian as bin (xml) files can already be converted to B-E.
## Post #39
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T17:40:11+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Rocky5
>
> extraction of arc files is done both using BMS Script and now an actual program here.

The problem i have is the xbox 360 has Big-Endian coded files  now the PC doesn't well we all know this but dds textures (L-E) work on the x360 so no need to convert but models, bin files and such must be Big-Endian or they wont load when the game is started, hens why i wanted to know how to convert them if possible.

I can give any resources needed (bar rbm files as these are not decrypted in the arc file yet  will need to find them first 18000+ unknown files lol) for some one to see if they can convert the dds (textures) files to big-endian as bin (xml) files can already be converted to B-E.I recently committed updates to my file lists to include more 360 and PS3 content.

And I thought this thread was for Just Cause 1?
## Post #40
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T17:48:50+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Rick
>
> Rocky5 wrote:extraction of arc files is done both using BMS Script and now an actual program here.

The problem i have is the xbox 360 has Big-Endian coded files  now the PC doesn't well we all know this but dds textures (L-E) work on the x360 so no need to convert but models, bin files and such must be Big-Endian or they wont load when the game is started, hens why i wanted to know how to convert them if possible.

I can give any resources needed (bar rbm files as these are not decrypted in the arc file yet  will need to find them first 18000+ unknown files lol) for some one to see if they can convert the dds (textures) files to big-endian as bin (xml) files can already be converted to B-E.I recently committed updates to my file lists to include more 360 and PS3 content.

And I thought this thread was for Just Cause 1?

oh my bad lol sorry will make a new thread for Just Cause 2 Xbox 360 files.

and thank you for making these tools its much appreciated.

x360 eez support thanks man only need the dds and almost everything on the pc can be ported.
## Post #41
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-04-12T19:40:55+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Rocky5
>
> sorry i miss read the thread name this was for just cause 2

> Reply from Rick
>
> And I thought this thread was for Just Cause 1?

Ya, I guess Rocky5 misread it again.

> Reply from Rick
>
> Are you looking for .arc extraction or something else? This is the first time I've written a BMS script.

To use, quickbms.exe extract_jc1.bms pc.tab extracted or whatnot.

To do filenames you'll need to figure out what algorithm the game is using to hash the names, it isn't Jenkins hashlittle() like Just Cause 2.

I know that "weapons_pc.bin" is hashed to 0xBB02F83B.

I have no idea how to figure out hashes. I was kind of hoping the actual plugin would be fixed, too. Where were you guys a month ago 

> Reply from Rocky5
>
> 
oh my bad lol sorry will make a new thread for Just Cause 2 Xbox 360 files.

and thank you for making these tools its much appreciated.

x360 eez support thanks man only need the dds and almost everything on the pc can be ported.

Ported to what from the PC? XBox 360? I'm pretty sure there's a reason they make separate versions of the game.
## Post #42
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-02T17:33:24+00:00
- Post Title: Re: Just Cause *.ARC file decompression

The contents of this post was deleted because of possible forum rules violation.
## Post #43
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-06-03T06:06:15+00:00
- Post Title: Re: Just Cause *.ARC file decompression

My script will probably work if you switch quickbms into big endian mode.
## Post #44
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-03T10:58:33+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from Rick
>
> My script will probably work if you switch quickbms into big endian mode.
No, doesn't work. The PC version has a different structure than the Xbox 360 version. Try it on the sample file, you'll see that quickbms throws an error about not being able to open a certain file ( Error in myfopen() ).
## Post #45
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-03T12:45:09+00:00
- Post Title: Re: Just Cause *.ARC file decompression

I have not fully understood if it was jc1 or jc2 (the format is enough similar) anyway I updated my justcause2 script to work with the archive you provided.
but note that I used a work-around because the tab file contains also invalid offsets:
[http://aluigi.org/papers/bms/justcause2.bms](http://aluigi.org/papers/bms/justcause2.bms)
## Post #46
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-06-03T20:06:22+00:00
- Post Title: Re: Just Cause *.ARC file decompression

I'm kind of wondering here, but why to people reply in bursts spaced about a month apart?

Anyhow, I would like to keep this thread on topic for PC only. Anyhow, aluigi, does your script support decompression and re-compression? My whole reason for making this topic was so someone could fix the binary for this task.
## Post #47
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-03T20:22:31+00:00
- Post Title: Re: Just Cause *.ARC file decompression

like any other script from mine it supports only the extraction of the files
## Post #48
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-03T23:26:47+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from tgp1994
>
> Anyhow, I would like to keep this thread on topic for PC only.?
## Post #49
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-06-03T23:31:38+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from AlphaTwentyThree
>
> tgp1994 wrote:Anyhow, I would like to keep this thread on topic for PC only.?

As someone stated earlier, the XBOX360 and PC versions have slightly different formats which can make a huge difference come to decompress time. Thus, I would like to keep this thread on topic for PC only.
## Post #50
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-04T14:45:20+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from tgp1994
>
> As someone stated earlier, the XBOX360 and PC versions have slightly different formats which can make a huge difference come to decompress time. Thus, I would like to keep this thread on topic for PC only.Ah, that clears up things. On the other side: how often do you decompress *.arc archives? Only one time when you do something with Just Cause. So far I think no other game with this format is known. Decompression time doesn't change much I think because of the 'if causes', which take almost no additional time (couple of ms at most).
## Post #51
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-04T19:22:52+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from aluigi
>
> I have not fully understood if it was jc1 or jc2 (the format is enough similar) anyway I updated my justcause2 script to work with the archive you provided.
but note that I used a work-around because the tab file contains also invalid offsets:
http://aluigi.org/papers/bms/justcause2.bmsWorked, thanks a lot!  Just needed to change the NAME_CRC to just i because of some name problems.
## Post #52
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-06-04T19:51:50+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from AlphaTwentyThree
>
> Decompression time doesn't change much I think because of the 'if causes', which take almost no additional time (couple of ms at most).

What? I wasn't complaining about decompression time. I would like to see more modding for this game, so a decompresser and recompresser would be nice.
## Post #53
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-04T23:59:12+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from tgp1994
>
> ... which can make a huge difference come to decompress time.
> Reply from tgp1994
>
> What? I wasn't complaining about decompression time.I rest my case.
## Post #54
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2010-06-05T00:21:25+00:00
- Post Title: Re: Just Cause *.ARC file decompression

> Reply from AlphaTwentyThree
>
> tgp1994 wrote:... which can make a huge difference come to decompress time. tgp1994 wrote:What? I wasn't complaining about decompression time.I rest my case.

You're misunderstanding what I said there, I meant "the differing formats can make a huge difference, when you actually need to decompress it."
## Post #55
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-06-14T11:45:34+00:00
- Post Title: Re: Just Cause *.ARC file decompression

My script was intended for JC1, JC2 has a tab file for each arc, whereas JC1 has a single tab file for multiple arcs.
