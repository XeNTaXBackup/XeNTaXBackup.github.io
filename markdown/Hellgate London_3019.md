## Post #1
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-04-20T15:00:27+00:00
- Post Title: Hellgate London

since FSS has officially stated that they wont release an SDK, but dont care if modding is done to the game i was wondering if anyone at xentax was able to add function to unhell/multi-ex to deal with the game's file formats

unhell can unpack files, but cant repack them
no one (that i know of) has opened up the various files with the 'cooked' extension

i'd like to be able to play with something more than just textures


thanks in advance

-E
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-12T21:08:55+00:00
- Post Title: Hellgate London

Well, we would need more information. Like files etc. Do you have a full description of the file formats ? That would help any coder with time
## Post #3
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-06-20T02:34:40+00:00
- Post Title: Hellgate London

i have the files themselves, i can upload a couple from the directories if you like, i also have a python script from another coder that can look inside the .cooked files and make a little sense of them, john_doe's unpacker is really helpful for texturing, but without a way to repack the files there's little more than textures that the engine will allow to be unpacked while it runs *shrug* i'd be happy to pass along anything i can to help the cause, i'd really like to be able to make more armors and possibly do some mapping of my own, although i realixe that could be a long, long way down the road.


thanks guys
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2008-06-21T12:40:18+00:00
- Post Title: Hellgate London

Hellgate mini-dissection:
Uses zlib compression, audio is wav and mpeg, graphics are a DDS (a lot of DXT1), you can pack them with the zlibc from Rheini
## Post #5
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-06-22T08:38:13+00:00
- Post Title: Hellgate London

ok...
i can use unhell to open the archives
i cannot use unhell to repack them
i cannot edit the .cooked files, read them well, or repack them
i can edit the base textures for the armors and the default body
i cannot edit sounds, weapons, maps, skills, meshes, etc.
textures will allow themselves to be edited and sit upacked, nothing else in my expirience with hellgate will
i would like to be able to do more kinds of editing with the game

i know what and how when it comes to editing textures, i know how to use unhell
i do not know how to use zlibc for any purpose, i didnt see a download for it, and i am not on my own computer
i do know that Granny3D was used, i do not know to what extent
i do know that bink was used for the movies

however, none of this helps with what i want to do, some light mapping if possible and double the meshes and edit the drop lists to include my own custom sets of armor.
when i have access to my own machine i will upload a few samples of the .cooked files if you would like, however, as i have mentioned, i am not an engineer, debugger, coder, or game designer, i am a hobbyist trying to improve the game expirience and add some custom content, any and all help is appriciated

thank you

-E

it should also be noted that some of the meshes and textures seem to be at least partially dependant on information contained in the .xls and .xml files that have been repacked/encrypted with the .cooked extension
## Post #6
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-07-28T00:41:28+00:00
- Post Title: Hellgate London

i now have my machine setup, but not yet networthy, do i need to upload the .cooked files somewhere for dissection or will zlibc open those?
## Post #7
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-07-28T19:03:34+00:00
- Post Title: Hellgate London

zlibc doesnt open .cooked files, it might repack .idx i havent tried yet
## Post #8
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-08-29T22:05:53+00:00
- Post Title: Hellgate London

anyone there?
## Post #9
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-09-03T12:52:59+00:00
- Post Title: Hellgate London

i dont know if this is really allowed, but i need help with this:


[QUOTE=Kral2;1192264]Eh, I already linked around the old python scripts I used at release to transcode some of the .cooked files - they're GPLed so people can use them as a start at fully transcoding for purposes of modding.  I'm definitely not wasting any more time on this game, so don't expect them improved by me.   They're missing the part that writes the XML version of the cooked file back out (since I didn't care about modding the game, I was just looking for a cow level), but you can copy that from the versions I wrote for WoW that my Hellgate scripts are based on that do write it back out to the original file.  The WoW ones are far more complete as I was modding it.

Basically, the idea of the transcoders is to do a non-lossy conversion of as much as is known about a file into a format easily worked on by humans, then be able to transcode it back to the original file format.  You don't have to know the /entire/ file format in order to do this, only the parts that make a difference for reassembly have to be fully understood (e.g., anything that has a file offset as it will change if rewritten).  I only bothered converting the fields I was interested in, but you can figure out the rest and add more.  If nothing else, it at least documents the conventions the .cooked files use.

Here are the ones for Hellgate:

[http://ipv6.variadic.org/kral/decode-levels-pre-1.0.py](http://ipv6.variadic.org/kral/decode-levels-pre-1.0.py)
[http://ipv6.variadic.org/kral/decode-levels.py](http://ipv6.variadic.org/kral/decode-levels.py)
[http://ipv6.variadic.org/kral/decode-strings_level.py](http://ipv6.variadic.org/kral/decode-strings_level.py)

Here are examples of the transcoded content they produce (one is done with an earlier version of the script that mixed up UTF-8 and UTF-16 so isn't well-formed):

[http://ipv6.variadic.org/kral/levels.tx ... ecoded.xml](http://ipv6.variadic.org/kral/levels.txt.cooked.decoded.xml)
[http://ipv6.variadic.org/kral/strings_l ... ecoded.xml](http://ipv6.variadic.org/kral/strings_level.xls.uni.cooked.decoded.xml)

And here are the WoW scripts if you want to get the code to write the transcoded XML form back out to a cooked file (GPL licensed as well):

[http://ipv6.variadic.org/kral/wowtools/ ... eaTable.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeAreaTable.py)
[http://ipv6.variadic.org/kral/wowtools/ ... layInfo.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeCreatureDisplayInfo.py)
[http://ipv6.variadic.org/kral/wowtools/ ... delData.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeCreatureModelData.py)
[http://ipv6.variadic.org/kral/wowtools/ ... undData.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeCreatureSoundData.py)
[http://ipv6.variadic.org/kral/wowtools/ ... codeDbc.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeDbc.py)
[http://ipv6.variadic.org/kral/wowtools/ ... Entries.py](http://ipv6.variadic.org/kral/wowtools/transcode/transcodeSoundEntries.py)

And just for the lulz, those links only work over IPv6.  If you can't get to them, then you aren't clueful enough to do anything with them anyway. [/QUOTE]

as i'm sure i've mentioned before, i dont know jack about coding that's not q-basic, since that was the last time i did anything other than some database edits/very small scripts for various games... i would like assistance with these, as you are all expirienced coders, i was hoping one or more of you would be able to make sense of the code contained in the links and be able to make a workable tool from it. i also thought that coming here would be a good idea because it could potentially add another format to those mult-ex supports

at any rate, i appriciate the help i have been given here thus far, thank you for your aid. flagship studios no longer owns the IP for hellgate london and has closed it's doors. further work will be, i believe, left up to those who do it 'for the love of the game'

warm regards,

Etherdemon
## Post #10
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-09-14T22:12:34+00:00
- Post Title: Hellgate London

no interest in this at all?



in this post i've included the python for ease of use
i'd really appriciate someone taking a look at this, i believe at this point the future of HGL rests in the hands of those interested in modfiying it/creating fan-made patches. Kral's code could also be used in Multi-Ex (?) to increase it's functionality.

honestly i dont know any great amount of programmers/software engineers as talented as the Xentax team, i would deeply appriciate the assistance


regards

Etherdemon
[Python(coding)IMPORTANT.zip](https://xentaxbackup.github.io/file/1642_Python(coding)IMPORTANT.zip)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-14T22:36:29+00:00
- Post Title: Hellgate London

I guess/believe everybody is just busy with something for the time being.
## Post #12
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-10-28T18:12:13+00:00
- Post Title: Hellgate London

if anyone would like to further assist those of us who are trying to support/update/maintain hellgate london, the skills and talents of you would be vastly appriciated.

[http://hellgateguru.com/forum/forumdisplay.php?f=140](http://hellgateguru.com/forum/forumdisplay.php?f=140)

has all of the information posted here as well as some further work on getting the .cooked files into a format usable for editing/modding purposes

[http://www.hellgateaus.net/](http://www.hellgateaus.net/)

a very ambitious project in search of help, with the aim of creating an open source HGL client
