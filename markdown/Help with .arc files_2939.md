## Post #1
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2008-02-17T17:47:06+00:00
- Post Title: Help with *.arc files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2008-02-17T18:04:38+00:00
- Post Title: Help with *.arc files

Plz next time try to upload in another file hosting
Thanks
Let's to see this file
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T01:27:39+00:00
- Post Title: Help with *.arc files

Well the data is completely encrypted. I managed to decrypt everything. It is a simple xor algorithm. The directory can be decrypted with the global xorValue (data is treated as dwords, see the first file as an example, the last 3 bytes aren't encrypted there)
Each file is encrypted using its own xorValue.

However, the best way to deal with arc archives is to write a program for the system.dll. All functions to modify ARC archives are available in there.

my [010 editor binary template](http://www.sweetscape.com/010editor/templates.html):

```
uint version;
uint numFiles;
uint dirOffset;

FSeek(FileSize()-4);
uint xorValue<format=hex>;

FSeek(dirOffset);
struct Entry
{
	char filename[128]; // 0 terminated
	char pathname[256]; // 0 terminated
	uint offset;
	uint size;
	uint xorValue; // the value used
} directory[numFiles];
```

after applying it, you need to select the directory and binary xor it with the global xorValue to get the correct values.

I attached the first 3 decrypted files as an example.
[samplefiles.rar](https://xentaxbackup.github.io/file/1452_samplefiles.rar)
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T13:54:39+00:00
- Post Title: Help with *.arc files

> Reply from Rheini
>
> However, the best way to deal with arc archives is to write a program for the system.dll. All functions to modify ARC archives are available in there.
Well, it's harder than I thought. Got to figure out all the class hierarchy relations.

```
{
	namespace system
	{
		class TE_DLL_API IArchive
		{
		public:
			struct FileEntry
			{
				uint uk1;
				uint uk2;
				uint uk3;
				uint uk4;
				uint uk5;
				uint uk6;
				uint uk7;
				uint uk8;
				uint uk9;
				uint uk10;
				uint uk11;
				uint uk12;
				uint uk13;
				uint uk14;
				uint uk15;
				uint offsetInFIle; // Offset of the file in the ARC0 ?!
				uint filesize;
			}; // ????
			struct FindData {}; // ???
			IArchive();
			IArchive(const IArchive& rhs);
			~IArchive();
			string getName();
		};

		class TE_DLL_API ArchiveARC
		{
		public:
			ArchiveARC();
			ArchiveARC(const ArchiveARC& rhs);
			~ArchiveARC();
			int addFile(string name, const char* name2, uint id); // bool
			uint addFolder(string name);
			uint clear();
			uint close();
			uint findFile(string name, IArchive::FileEntry fileEntry);
			void* findFileBegin(IArchive::FindData findData);
			void* findFileNext(IArchive::FindData findData);
			virtual uint load(const string& name);
			uint open(uint id);
			int readFile(const IArchive::FileEntry& fileEntry, void* destBuffer);
			uint removeFile(const IArchive::FileEntry& fileEntry);
			uint save(string filename);

		};

		class TE_DLL_API ArchiveFilter
		{
		public:
			ArchiveFilter();
			ArchiveFilter(const ArchiveFilter& rhs);
			~ArchiveFilter();
			IArchive* addArchive(string name);
			int findFile(string name, IArchive::FileEntry& fileEntry); // bool
			uint forAllArchives(int (*callbackFunc) (IArchive*,void*), void*);
			IArchive* getArchive(string name);
			string getExtension();
			string getName();
			void registerArchives(string name);
			void setExtension(string ext);
			void setName(string name);
		};
	}
}
```

Anyone got experience with C++-DLLs (exported classes and stuff)?
[system.rar](https://xentaxbackup.github.io/file/1453_system.rar)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-02-19T22:35:50+00:00
- Post Title: Help with *.arc files

Hmm, I've only "google" experience from the past, when I created a dlll in C++ that I needed as a wrapper. But that would not help you. .. .
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-19T22:59:17+00:00
- Post Title: Help with *.arc files

The problem is the exe doesn't use many functions, mainly just createInstance or getInstance functions.
This seems like compiler generated stuff.
So I can't really see how the ARC management code is called.
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-20T21:01:51+00:00
- Post Title: Help with *.arc files

> Reply from Rheini
>
> The problem is the exe doesn't use many functions, mainly just createInstance or getInstance functions.
This seems like compiler generated stuff.
So I can't really see how the ARC management code is called.Interfaces and vtable calls. I'm working on this game now myself.
## Post #8
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-20T22:53:51+00:00
- Post Title: Help with *.arc files

I have a functional extractor now, I will post it later if I confirm it to be working correctly.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-21T06:09:46+00:00
- Post Title: Help with *.arc files

> Reply from Rick
>
> Rheini wrote:The problem is the exe doesn't use many functions, mainly just createInstance or getInstance functions.
This seems like compiler generated stuff.
So I can't really see how the ARC management code is called. Interfaces and vtable calls. I'm working on this game now myself.
So you have knowledge about that stuff? Would you tell me where you got that from? Are there any tutorials out there (or something like that)?
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-21T20:39:55+00:00
- Post Title: Help with *.arc files

> Reply from Rheini
>
> So you have knowledge about that stuff? Would you tell me where you got that from? Are there any tutorials out there (or something like that)?Yes I do, it's mostly from experimenting myself rather than tutorials, though I believe there is some information on vtables and such.

Attached is ExtractArc.zip (with a single file, ExtractArc.exe), command-line application, specify archive file as first argument, will extract contents to current directory. 'system.dll' from the game directory is required to be present in the directory of ExtractArc.exe. I suggest placing ExtractArc in the game directory then changing to the resources directory and doing ..\ExtractArc.exe archiveName.arc.

You can override any file in the archives by placing it in the same path it was extracted to in either the main game directory or resources, eg, scripts\start.lua in scripts.arc can be in .\scripts\start.lua or .\resources\scripts\start.lua (the game checks both paths for existence of this file before checking archives for it).
[ExtractArc.zip](https://xentaxbackup.github.io/file/1454_ExtractArc.zip)
## Post #11
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2008-02-21T21:36:45+00:00
- Post Title: Help with *.arc files

It's working great Rick!! Thanks to everybody!
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-22T16:24:04+00:00
- Post Title: Help with *.arc files

There's another game from that developer, probably they use the same system for that one.
[http://www.gamershell.com/download_22691.shtml](http://www.gamershell.com/download_22691.shtml)
## Post #13
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-24T12:49:43+00:00
- Post Title: Help with *.arc files

> Reply from Rheini
>
> There's another game from that developer, probably they use the same system for that one.
http://www.gamershell.com/download_22691.shtmlThe Experiment and Experience 112 are the same game. The Experiment is the US title for Experience 112.
## Post #14
- Username: qorilla
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 02, 2007 11:19 pm
- Post datetime: 2008-03-10T20:56:48+00:00
- Post Title: Help with *.arc files

Hi!

Thanks for this extractor program!
My question is, would it be possible to somehow pack new archives? I mean repacking the archive, with some changes to some files in it.

Thank you very much!
## Post #15
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-03-15T09:33:22+00:00
- Post Title: Help with *.arc files

> Reply from qorilla
>
> Hi!

Thanks for this extractor program!
My question is, would it be possible to somehow pack new archives? I mean repacking the archive, with some changes to some files in it.

Thank you very much!Probably, but what is the need when you can just use overriding the files as I mentioned earlier?
## Post #16
- Username: nobange
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 17, 2008 6:11 am
- Post datetime: 2008-09-18T20:40:11+00:00
- Post Title: Re: Help with *.arc files

Hello,

Rick, could you make such extractor for other language version of this game? It cannot be extracted with your program because of different encryption key. Here's the link to smallest .arc file and system.dll from the game: [http://uploaded.to/?id=1z2r7l](http://uploaded.to/?id=1z2r7l).
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-09-24T09:54:35+00:00
- Post Title: Re: Help with *.arc files

My tool uses a DLL from the game to extract... if it's failing for your version then I don't know why, sorry.
## Post #18
- Username: nobange
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 17, 2008 6:11 am
- Post datetime: 2008-09-24T18:40:12+00:00
- Post Title: Re: Help with *.arc files

I know, that's why I attached this dll for you  Could you just look at it? With your experience I hope you'll manage to modify the tool to extract files from my version too. It's easier than trying to figure it out from the beginning, I think. Sorry for bothering if you don't have time... but maybe... maybe... Noone else can help me with this.
## Post #19
- Username: Mordar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 17, 2008 10:24 pm
- Post datetime: 2008-11-17T15:54:56+00:00
- Post Title: Re: Help with *.arc files

I had similar problem with Polish version of the game so I used Rheini format description to create my extracting tool. The only diffrence I found is that in my files some data are written on 2 bytes instead of 1 (FileName[256],FilePath[512]). The file type can be selected in the tool.

I've made this application only because the movies from the game are not working on my PC. Thanks to this forum I can play the game and watch the movies in external player.
[ARCExtractor.zip](https://xentaxbackup.github.io/file/1747_ARCExtractor.zip)
## Post #20
- Username: Davero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 18, 2008 5:30 am
- Post datetime: 2008-12-18T17:49:05+00:00
- Post Title: Re: Help with *.arc files

I'd like to thank you very much Mordar for your tool. It's easy to use and do exactly what should be done. Music form this game is really worth listening to.

Of course many thanks also to Rheini and Rick who started deal with it .
## Post #21
- Username: GUGUCHA
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 22, 2016 5:41 am
- Post datetime: 2016-01-22T12:52:24+00:00
- Post Title: Re: Help with *.arc files

hi sorry for the Google translation 
I unpacked "Experience 112" the English version of Steam, but I can not unpack "Experience 112" the Russian disc version - there are probably other encoding - I need to get out Russian text and audio - help me please 
Here one file .arc [https://mega.nz/#!St4xCKqR!GaORZPm9M9Nq ... a1NpuYNlqc](https://mega.nz/#!St4xCKqR!GaORZPm9M9NqOPn9wMj2QkEq56ft9pmEXa1NpuYNlqc)
## Post #22
- Username: abcdef
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 28, 2017 10:25 pm
- Post datetime: 2017-06-04T12:08:58+00:00
- Post Title: Re: Help with *.arc files

Hello, sorry for extreme necroposting, but that thread seems to be the only thread about unpacking Experience112 resources. I've tried to use extractors posted earlier here, but no one of them works correctly in my case. So I wrote my own extractor, it doesn't use game libs and works with archives that have either 1-byte and 2-byte character encodings (it automatically determines which one is used). Tested on English and Russian localization, probably will work with other ones. You can get it from GitHub [here](https://github.com/dasbarr/Exp112ArcExtractor/releases/latest).

Usage
Put the extractor executable file to the directory with .arc file, open console window and type: exp112ArcExtractor archiveName.arc

Thanks to guys from this thread for .arc file structure explanation.

P.S. Probably you don't need that extractor. In my case the game was stuck on French localization (according to logs, for some strange reason the game tried to find some files from French localization when the installed localization was Russian). Also the game ignored changes that I made in experience112.ini. I thought that I'll unpack some archives and rename some files to make the game think that it uses French localization and run correctly. But the solution was much simpler: All I needed to do is to delete experience112.ini, run the game (it recreates config file if it doesn't exist), and after that the game used the information from the new config file and worked properly with Russian localization.
