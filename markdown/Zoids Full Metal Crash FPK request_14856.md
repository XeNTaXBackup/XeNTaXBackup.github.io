## Post #1
- Username: Falcarius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 4:34 pm
- Post datetime: 2016-08-14T11:24:00+00:00
- Post Title: Zoids Full Metal Crash FPK request

I was wondering if anyone could help me unpack the .fpk files from the Gamecube game Zoids Full Metal Crash?
I've included one of the story mode files as an example. Opening it in Notepad, I can tell that it contains five .txd files (bg3_gc.txd, bg3_r_gc.txd, scene_selmes_gc.txd, scene_selwin_gc.txd and scene_win_gc.txd), each of which contains a .png file.
I've tried using QuickBMS and Game Extractor to unpack them, but I don't know enough about coding to figure out what's going wrong. If someone could provide a working script for either program (or something else, if it's easier), that would be great.
[scene00_01.zip](https://xentaxbackup.github.io/file/11558_scene00_01.zip)
## Post #2
- Username: Falcarius
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-14T16:35:59+00:00
- Post Title: Zoids Full Metal Crash FPK request

```
{
	char m_filePath[36];
	unsigned int m_fileOffset;
	unsigned int m_fileSize;
	unsigned short m_unk00;//?
	unsigned short m_unk01;//Always 0x2B8?
};

struct FPK
{
	unsigned int m_magic;//0xBFC5
	unsigned int m_fileCount; //Number of files in FPK archive
	unsigned int m_fileTableOffset; //Offset to FPK entries
	unsigned int m_archiveSize; //Entire size of FPK
	FPKEntry[m_fileCount] m_fpkEntries;
};

```


File is endian big.
## Post #3
- Username: Falcarius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 4:34 pm
- Post datetime: 2016-08-16T00:20:49+00:00
- Post Title: Zoids Full Metal Crash FPK request

I tried running the script as a .bms file in QuickBMS, but it failed to understand the second mention of FPKEntry (meanwhile, Game Extractor just gave me a generic error message). Could I have some instructions on how to use the script, please?

EDIT: Never mind, I just noticed a Full Metal Crash script has recently been added to the QuickBMS site. 
I tried making my own by referring to your recent Tak 2 post, but it turns out there was some compression ("PRS_8ING") involved as well, which I wouldn't have spotted on my own.
I did have some trouble opening the extracted .txd files, but then I tracked down a different viewer that could handle Gamecube .txds and everything's working now. Thanks for the response!
