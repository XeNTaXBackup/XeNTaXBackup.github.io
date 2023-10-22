## Post #1
- Username: Medstar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 04, 2020 9:16 am
- Post datetime: 2020-05-06T07:02:55+00:00
- Post Title: [Request] Help with Generals 2 Extraction (Frostbite 2/3)

Hello all,

A while back, I came across an archive containing an alpha build for Generals 2 (Command and Conquer F2P). The game is made either with Frostbite 2 or 3, as I have seen conflicting information from various sources.

I've tried various Frostbite extraction tools (the bms script, Frankelstner's stuff, bf4dumper, the Universal Frostbite Extractor, etc.), but to no avail. However, I did come across a packet of tools based on Frankelstner's dumper.py script dating to around 2013. The scripts I found..."work", in that they can extract the files with names and extensions; however, the resulting ebx files are...out of order(?) when compared to a successfully extracted ebx from SW:Battlefront 1. It's not like it's dumping gibberish to files; when comparing, I see that certain sections match up with the sample from SW:BF, but parts seem to be duplicated and/or shifted up a chunk of data or two. I will include the following example file to show what I am referring to.

The tools I found detail that they're for the game as well as an August 2013 patch; however, the patch is not included in the archive I found, but I don't think that's the issue here. I was wondering if anyone could throw me a bone here as to why the script is behaving as it is. I've tried debugging it to see where it goes wrong, but I can't seem to find where exactly. I can successfully unXOR the toc files and such; but other than that, I am inexperienced with this sort of reverse engineering.

I AM NOT aiming to reverse engineer the game; I just want to find out what's wrong with these scripts so that I can take a peek into the files of a game that never really got to see the light of day.

I will include a dumped file that I examined and the tools that I found (Python 2.7 required); I'll also provide the link to the archive that I found so that y'all don't have to go hunting around for it yourselves.

Thank you for your time; any help is much appreciated. If having this particular link here is an issue, I can provide a new one that only holds the .cas/.cat/.toc/.sb files and not the entire client.

Archive link: [https://drive.google.com/uc?id=1LNEOjfj ... t=download](https://drive.google.com/uc?id=1LNEOjfjvJqAEMG-ExIQj5G5I_s3LBka-&export=download)
[Data.zip](https://xentaxbackup.github.io/file/18098_Data.zip)
