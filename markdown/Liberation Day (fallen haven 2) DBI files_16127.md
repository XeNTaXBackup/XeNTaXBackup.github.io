## Post #1
- Username: metalbass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 11, 2017 10:57 pm
- Post datetime: 2017-04-12T13:22:07+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

Hi everyone,

I recently started a hobby project to remake Liberation Day (sequest of the more known Fallen Haven), from 1998.
I'm pushing everthing as I go to github: [https://github.com/metalbass/LibDay](https://github.com/metalbass/LibDay)

As I want to reuse all assets from the original game I've decided that I'll want to extract them into something easier to use from actual game engines. So far I've managed to extract animations and UI assets.

I'm actually trying to extract DBI files, that seem to contain in-game assets, as they are called like roads.dbi, mines.dbi, walls.dbi... The issue here is that I cannot make too much sense out of it.

I've found lists of strings, probably filenames inside the archive, but I haven't been able to understand the data that's between those strings. I've also seen that the file seems to have a big header, an list of strings + 4 bytes ints, another blob of data (probably extractable data, like images?) and more lists...

Here you have one of those files (mines.dbi), in case anybody wants to take a look: [http://www.filedropper.com/mines_1](http://www.filedropper.com/mines_1)

The game runs ok on 256 color mode, so I'm assuming all assets are going to use 8-bit palettes (also, SMK files for animations from the game use them).

I'd really appreciate any help on this matter, since I've been blocked on extracting data from this format and it seems to be one of the last formats I'll need to export from.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-12T14:56:51+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

considering the file size and contents of the sample, i would say these are not textures but an index file for something else,
but then again i am not familiar with data from a lot of these older games so i could be wrong.
## Post #3
- Username: metalbass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 11, 2017 10:57 pm
- Post datetime: 2017-04-12T17:19:45+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

Thank you AceWell for taking the time to answer. I shared the Mines.DBI file, as it's the smaller DBI file.
There are other bigger DBI files on that folder, ranging from 33MB to 34KB.

The idea of files referencing each other did not come to mind; I hope the game is not making that, since that would be harder for me to track!   

All this talk about the possibility of this made me realize I still haven't found all the audios of the game, which could be stored here, but I don't think so, since the folder is in is called IMGS...

Any ideas of how I could understand whats in here? I can upload another file for comparison, if needed.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-13T14:59:10+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

yeah i guess you should upload larger sized samples for analysis and maybe someone else will know what to look for better than me.
## Post #5
- Username: metalbass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 11, 2017 10:57 pm
- Post datetime: 2017-04-13T21:50:26+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

Hi,

I've uploaded 2 more files, so, in the event anyone wants to take a look at them, there's enough material 

[http://www.filedropper.com/ub](http://www.filedropper.com/ub)
[http://www.filedropper.com/walls_3](http://www.filedropper.com/walls_3)

They are all .DBI files, but I cannot be certain that they contain the same type of files.
## Post #6
- Username: metalbass
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 11, 2017 10:57 pm
- Post datetime: 2017-04-14T09:35:31+00:00
- Post Title: Liberation Day (fallen haven 2) DBI files

Hi again.

I've continued looking into this and I now think this has something to do with access database files. On the attached Walls file, I've found mentions to it at offsets 0x4fef8, 0x4ffe8 and 0x53f63.

On the same walls.dbi file I've found some ASCII text that looks like table headers close to 0xb1def.

The game uses mdb files (that I'm already able to open and export into tsv files) for table storing. I should be able to connect to this on the same manner through C# apis, I guess. I'll keep looking into this.

Btw, since this no longer looks like image files, should I repost this on another subforum?
