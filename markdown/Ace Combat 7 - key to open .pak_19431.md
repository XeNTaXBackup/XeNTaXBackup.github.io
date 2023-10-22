## Post #1
- Username: hooner11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 02, 2019 4:34 am
- Post datetime: 2019-02-01T20:37:40+00:00
- Post Title: Ace Combat 7 - key to open .pak

Hi there

I have tried unpacking the .pak files with umodel.exe (unreal 4 game engine), but as expected it needs a AES decryption key...

So, has anyone else tried or had any luck, or know a better way of going about this?

thanks!
## Post #2
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-02-20T19:15:19+00:00
- Post Title: Ace Combat 7 - key to open .pak

Hi, I'm trying to find the key for this game but for now nothing, I do not understand much about programming but I try the same 
Here's everything I've discovered so far:

The type of AES:
[https://www.intel.it/content/www/it/it/ ... ology.html](https://www.intel.it/content/www/it/it/architecture-and-technology/advanced-encryption-standard-aes/data-protection-aes-general-technology.html)
[https://www.openssl.org/~appro/](https://www.openssl.org/~appro/)
[https://crypto.stanford.edu/vpaes/](https://crypto.stanford.edu/vpaes/)
[https://cryptojedi.org/crypto/index.shtml](https://cryptojedi.org/crypto/index.shtml)
AESNI-CBC+SHA
AES_XTS
[https://blogs.technet.microsoft.com/dub ... tion-type/](https://blogs.technet.microsoft.com/dubaisec/2016/03/04/bitlocker-aes-xts-new-encryption-type/)
[https://en.wikipedia.org/wiki/Camellia_(cipher)](https://en.wikipedia.org/wiki/Camellia_%28cipher%29)

Here some code that could be useful:
[https://groups.google.com/forum/#!msg/g ... Ys7f7DBwAJ](https://groups.google.com/forum/#!msg/golang-codereviews/VJCIjZ3fnIg/t-Ys7f7DBwAJ)
[https://github.com/dot-asm/cryptogams/b ... -x86_64.pl](https://github.com/dot-asm/cryptogams/blob/master/x86_64/aesni-x86_64.pl)

I would like to try to create a script that can scan the file, so I can find certain values of type AES encryption, many games that use the UE4 they have the key in "explicit" Ascii.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-02-21T00:40:40+00:00
- Post Title: Ace Combat 7 - key to open .pak

Can the aes key be found in the memory dump? or is it in the exe?
## Post #4
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-02-21T13:46:24+00:00
- Post Title: Ace Combat 7 - key to open .pak

In many games the key is in the exe file and also visible:
SoulCalibur 6 AES key "QyNTD(BsaNlg_)q2uO96blfz%tNCy#.gKo*y7JpYe6U(TL,M#~88Pkqs/l0~x,gc"
[https://imgur.com/a/9YbLI33](https://imgur.com/a/9YbLI33)
## Post #5
- Username: vedmysh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 07, 2017 7:44 pm
- Post datetime: 2019-02-21T13:58:31+00:00
- Post Title: Ace Combat 7 - key to open .pak

> Reply from OrangeC ↑Thu Feb 21, 2019 8:40 am at Thu Feb 21, 2019 8:40 am
>
> 
Can the aes key be found in the memory dump? or is it in the exe?

Short answer - yes, its in the executable or/and it should be in memory at some point of execution.
Long answer (useful generic information about keys extraction, carefully read second post): [http://www.gildor.org/smf/index.php/topic,6134.0.html](http://www.gildor.org/smf/index.php/topic,6134.0.html)
## Post #6
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-14T00:20:53+00:00
- Post Title: Ace Combat 7 - key to open .pak

I went to the trouble to reverse engineer this today with a disassembler and debugger.

> Reply from vedmysh ↑Thu Feb 21, 2019 9:58 pm at Thu Feb 21, 2019 9:58 pm
>
> 
Long answer (useful generic information about keys extraction, carefully read second post): http://www.gildor.org/smf/index.php/topic,6134.0.html
This information was highly useful in helping me quickly track down the specific code I needed to dig for, so thanks for posting it!

------

The AES key for this game is, comically, simply the string "[https://ace7.acecombat.jp/special/](https://ace7.acecombat.jp/special/)", truncated down to 32 characters to make it 256 bits long. As the whole string is 34 characters, that means that the key is all of it except the last two characters. 

```

String: https://ace7.acecombat.jp/specia
Hex:    68747470733a2f2f616365372e616365636f6d6261742e6a702f737065636961
```


I've tested this key with QuickBMS's unreal_tournament_4.bms script, and it appears to work perfectly.
## Post #7
- Username: TraccKrodm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 12:39 pm
- Post datetime: 2019-03-14T16:35:23+00:00
- Post Title: Ace Combat 7 - key to open .pak

Hi, i am subsidiary/friend of JilKylefield at Gildor's forums. tested the key, for some files like audio containers(Wwise .bnk/.pck), it works with no problem, however with the Unreal game assets trying to load at Umodel tool made by Gildor, it not works(even saying the game files are decrypted).

the key to works at Umodel needs the use of 0x at the beginning, which are the two characters remaning you mentioned. also they are more bits of the URL, which if you add it works(but they are optional, due the size is like the first one you found), like this picture :


Checking the files at a binary will result in a .uasset with ACE7 header and gambled data.  the .uexp also is compressed. you can check the details at the post of Jil i mentioned :
[http://www.gildor.org/smf/index.php/topic,6509.0.html](http://www.gildor.org/smf/index.php/topic,6509.0.html)

If you don't mind and active, could you check if there's another AES keys at the game with the debug methods you used? my team are suspicious that they are another AES keys that needs to be used for the game files.
## Post #8
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-14T18:21:52+00:00
- Post Title: Ace Combat 7 - key to open .pak

Yes, I've also attempted to open the uasset files and found that they were unreadable.

My presumption is that either there is a second layer of encryption being used on them (which is a tad silly, but not inconceivable), or that perhaps there's merely a tiny header modification going on. (These uasset files all seem to start with a magic number of 'ACE7' rather than the normal PACKAGE_FILE_TAG value of 0x9E2A83C1. I haven't yet tested simply seeing if replacing the 'ACE7' bytes with C1 83 2A 9E in a hex editor makes things magically work, or if there's indeed more to it than just that.)

I do plan to look into that further. If anyone else is interested, an important function of interest related to this is sub_147AB3940; I do not yet know the identity of this function precisely, but it definitely seems to check for 'ACE7' (or '7ECA', the byte-swapped version of that) and replace it with 0x9E2A83C1/0xC1832A9E, and then go on to do some other things that I haven't fully identified yet.

(Full disclosure: I purchased a copy of the game on Steam and I do own it legally; but I'm using the cracked initial release EXE of the game for reverse engineering purposes, as I figured it would be less of a pain to run in a debugger etc. So that subroutine address is correct for that particular EXE variation, but not necessarily the uncracked initial PC release EXE or the subsequently released version 1.02 EXE.)
## Post #9
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-14T19:04:30+00:00
- Post Title: Ace Combat 7 - key to open .pak

Okay, I did some quick testing in the debugger just now.

Every call to FAES::DecryptData during the loading process (from firing up the EXE, through the various loading splash screens, up to the title screen that says to press ENTER) uses the same key parameters, those for the "[https://ace7.acecombat.jp/special/](https://ace7.acecombat.jp/special/)" key. There were probably several dozen calls in total.

Then, right after the title screen, I immediately start seeing a ton of calls to FAES::DecryptData from thread "SaveLoadThread0" that specify a key length of 0x20 and which specify the 32-character key string "M$KW=w4,knvovE8u0000000004100000". The data length always appears to be 0x200 (512 bytes).

I skipped over those, and then re-enabled the FAES::DecryptData breakpoint a bit later, once I was at the fully loaded-up menu screen. From that point forward, I did not observe any further calls to FAES::DecryptData. This was while browsing the menus, looking at various aircraft, loading up maps, playing missions with their cinematics, etc., all of which I assume would involve dynamically loading asset data.

So from that, I think it's reasonable to conclude that one of the following is true:
1. The individual asset files themselves are not AES-encrypted. (Or at least, not AES-encrypted using the Unreal Engine AES functions, but still possibly decrypted using functions elsewhere, perhaps.)
2. The individual asset files perhaps are all AES-encrypted (maybe at least a small stub at the beginning), and the game goes through literally all of its asset files' stubs during that time period between the title screen and the main menu and pre-decrypts that bit of header data.

I'll have to go back and see if I can get a reasonably quick complete breakpoint count on that complete second sequence of FAES::DecryptData calls.

For now, anyway, I seem to have unearthed a second AES key that's being used for something...

OH, and I actually just realized, the cracked game version uses a fake steam ID of 0x4100000041000000 (or something like that... in any case, the SaveGames subdir name is 292733975847239680, which is decimal for that number). Combined with the fact that these AES decryption calls were coming from the thread named "SaveLoadThread0", and with the timing of "right before loading the main menu and no other times" (I didn't do anything that would have triggered a game save at any point, like completing a mission or unlocking an aircraft part etc), I think it's entirely reasonable to conclude that the "M$KW=w4,knvovE8u0000000004100000" AES key is in fact the user-specific savegame encryption key for user 0x4100000041000000. So that perhaps has some usefulness in determining the AES keys for the user-specific savegame file encryption. But it also strongly points towards "the asset files themselves are not AES-encrypted (at least not with the Unreal Engine functions)".
## Post #10
- Username: TraccKrodm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 12:39 pm
- Post datetime: 2019-03-14T21:19:02+00:00
- Post Title: Ace Combat 7 - key to open .pak

Thanks for the help about this, in short, i guess is an additional external encryption layer(it even had a entry in the debug). because at least it can read all the files with the same key, no other is using another one(and if it was, probably they would not even import). about the Save File discovery, i would suggest showcase this to FluffyQuack, due he worked at a SoulCalibur VI Save Editor, but said that for decompressing the save file was a little hard by the encryption. with the key already found, it is a possible way to create a Ace Combat 7 Save Editor, which it will be important for one factor, the account like you mentioned. because each user that plays the game, it will have his own save file, but passing another file from one account folder to other, it will not work. as a preveition ala PS3 saves.

In case of someone interresed in the thread, i uploading some samples of the files, starting with a file from A-10 Thunderbolt plane from AC7, which uses this type of encryption :
[https://www.dropbox.com/s/nxnpqygvd5ntn ... 7.rar?dl=0](https://www.dropbox.com/s/nxnpqygvd5ntnfi/a10aAC7.rar?dl=0)

and as a sample, here's Goku model from Dragon Ball FighterZ, which is one of the most examples of .uasset structure. i even checked my Tekken 7 for see if they would have similarities considering some elements like Wwise Audio. but no, the .uassets are normal, i think the .PAK from the game somewhat uses the encryption, when AC7 case it uses at the files itself :
[https://www.dropbox.com/s/bf67tt81ilptc ... Z.rar?dl=0](https://www.dropbox.com/s/bf67tt81ilptcsy/GKNDBFZ.rar?dl=0)

Will be on awaiting if you can found more stuff, i even was suspicious you will need to use a cracked version to check because of the anti-cheat device from the game.
## Post #11
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-14T22:10:05+00:00
- Post Title: Ace Combat 7 - key to open .pak

> Reply from TraccKrodm ↑Fri Mar 15, 2019 5:19 am at Fri Mar 15, 2019 5:19 am
>
> about the Save File discovery, i would suggest showcase this to FluffyQuack, due he worked at a SoulCalibur VI Save Editor, but said that for decompressing the save file was a little hard by the encryption. with the key already found, it is a possible way to create a Ace Combat 7 Save Editor, which it will be important for one factor, the account like you mentioned. because each user that plays the game, it will have his own save file, but passing another file from one account folder to other, it will not work. as a preveition ala PS3 saves.
Would you mind tracking this person down for me? You seem to already be at least somewhat familiar with him, whereas I'm not.

And yeah, I could already tell that the save files were made to be, in some manner, account-specific, even before this. (The save file from the cracked copy wouldn't load in the legit copy and vice versa, and they were saved under different numeric directories corresponding to different user IDs.) So it does make a great deal of sense then that they're encrypted with a key that incorporates the account ID.

> Reply from TraccKrodm ↑Fri Mar 15, 2019 5:19 am at Fri Mar 15, 2019 5:19 am
>
> i even was suspicious you will need to use a cracked version to check because of the anti-cheat device from the game.
Yeah. I essentially just automatically assumed that the non-cracked version of the game is going to have all sorts of anti-debugger checks and stuff like that (probably built-in as part of the awful Denuvo DRM), which I just don't want to deal with if I don't have to. (Nor do I want to risk my real Steam account either, for that matter, in case if I were to e.g. inadvertently trip some kind of anti-cheat account ban thing in the game while doing entirely non-cheat-related reverse engineering. That would really suck.)

> Reply from TraccKrodm ↑Fri Mar 15, 2019 5:19 am at Fri Mar 15, 2019 5:19 am
>
> Will be on awaiting if you can found more stuff
I definitely plan on doing more digging.

Thanks for the non-encrypted .uasset file example, by the way; that'll probably be handy for comparison purposes. (I have basically zero prior knowledge of how UE4 game files work; I just have a lot of general reverse engineering experience and a bunch of knowledge from other projects I've worked on. So it's good to have a sample file to compare against.)

Perhaps for a first step, I can try to use the debugger to find the unencrypted version of one or more of the AC7 .uasset files once it's in memory, and then we will at least have a ciphertext/plaintext comparison to look at. That would likely make it easier to reverse engineer the code that's responsible for doing whatever obfuscation or decryption is going on, because then I would have information like the difference in file size before and after the decoding and so forth (which would tell me if there's additional header data that AC7 is tacking onto the front of the file or whatever; that sort of thing).

Incidentally... could you shed any light on what the purpose of the .uexp files is? So far what I can infer is that the .uasset files contain the actual main data for each game asset package, and then the corresponding .uexp file holds some sort of additional information (metadata?) of some kind. [EDIT: Actually I think I have that backwards.] (And from some Internet searching, it seems that they're related to the UE4.14 "Event Driven Loader" feature, which to my understanding appears to be a newer/improved system for asynchronously loading game assets dynamically at runtime... but that still doesn't entirely help me understand what the purpose of those files specifically is or what data is in them.)
## Post #12
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-14T22:37:14+00:00
- Post Title: Ace Combat 7 - key to open .pak

I think I might understand... it seems that the .uasset file is basically the "front part" of the archive, with metadata and stuff, and then the .uexp file is the "back part" of the archive, where the actual bulk data is stored.

Correct me if I'm wrong.
## Post #13
- Username: TraccKrodm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 12:39 pm
- Post datetime: 2019-03-14T23:56:45+00:00
- Post Title: Ace Combat 7 - key to open .pak

Well, according to a UE4 staff from the forum, .uasset is the configuration and metadata of the file directories when using the .uexp/.ubulk method, more or less like you said, they are for not giving the engine trouble of loading a huge file instantanely, .uexp seems to be export configurations and when contains the data(thus the size). also another type of file(.ubulk) used for textures, is the texture file itself compressed with all the mipmap variants, the texture most of the time are DDS.
[https://answers.unrealengine.com/questi ... files.html](https://answers.unrealengine.com/questions/587400/what-are-uexp-and-ubulk-files.html)

Also, i'm sending samples from a model and texture, because i think i sent the config data.
[https://www.dropbox.com/s/6spyzyg0tnlpz ... x.rar?dl=0](https://www.dropbox.com/s/6spyzyg0tnlpzd5/a10amodeltex.rar?dl=0)
## Post #14
- Username: jgottula
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 14, 2019 8:05 am
- Post datetime: 2019-03-15T00:13:40+00:00
- Post Title: Ace Combat 7 - key to open .pak

Quick update: I have finally determined the identity of sub_147AB3940 (the function that does the "ACE7" header magic manipulation). It's void operator<<(FStucturedArchive::FSlot Slot, FPackageFileSummary& Sum) from PackageFileSummary.cpp. Presumably with a bunch of stuff inlined, I don't doubt.
## Post #15
- Username: sovereign73811
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 02, 2010 11:05 am
- Post datetime: 2019-03-15T05:53:54+00:00
- Post Title: Ace Combat 7 - key to open .pak

I actually tried to get the bnk/pck files to open up but that didn't work out all that well. Here are some samples for you to check out. The BGM.pck file only had 12 files in it? Then in a hex editor I saw one of the wem files has the word JUNK right after the header. It's great progress though. Keep up the good work!

[https://drive.google.com/open?id=1YY6AH ... oCK91WlQ4f](https://drive.google.com/open?id=1YY6AHyFciQ76vLN3TL2DXgoCK91WlQ4f)

[https://drive.google.com/open?id=1eGU9J ... vXjPecKwTP](https://drive.google.com/open?id=1eGU9J5bomPP8rV9BBsTWu_vXjPecKwTP)
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-19T13:00:44+00:00
- Post Title: Re: Ace Combat 7 - key to open .pak

How do you get the key 68747470733a2f2f616365372e616365636f6d6261742e6a702f737065636961 working with the script? i tried it but it doesn't extrac anything.
## Post #17
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-03-20T01:17:48+00:00
- Post Title: Re: Ace Combat 7 - key to open .pak

> Reply from OrangeC ↑Tue Mar 19, 2019 9:00 pm at Tue Mar 19, 2019 9:00 pm
>
> 
How do you get the key 68747470733a2f2f616365372e616365636f6d6261742e6a702f737065636961 working with the script? i tried it but it doesn't extrac anything.

try 0x68747470733a2f2f616365372e616365636f6d6261742e6a702f737065636961
## Post #18
- Username: sovereign73811
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 02, 2010 11:05 am
- Post datetime: 2019-03-20T23:16:55+00:00
- Post Title: Re: Ace Combat 7 - key to open .pak

Update on my last post: I am an idiot. The rest of the BGM files are in another .pak. For some reason I thought QBMS was pulling files from all the other .paks but it was not. Must have been half asleep when I was trying that. Also, yes the pck/bnk files are perfectly fine. I just needed to use a tool whose name includes a tasty Italian food.
## Post #19
- Username: Andersson799
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 08, 2016 4:16 pm
- Post datetime: 2019-03-21T08:33:37+00:00
- Post Title: Re: Ace Combat 7 - key to open .pak

Does anyone knows where are the map specific BGM files located? I tried to extract "bgm.pck", "game_se.pck", and "bgm_chunk1.pck" but i can't seem to find the BGM files for each map. I was using "Wwise-Unpacker-1.0.2" to extract it btw.
## Post #20
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2019-03-31T07:36:05+00:00
- Post Title: Re: Ace Combat 7 - key to open .pak

I looked at the uasset/uexp files too, they are clearly extracted at the right size so there is no compression on them but actual data is entirely ciphered as actual textural data has no zeroes along data (except header fields) which is typically the case and decoded texture data is total garbage thus cipher is all over than just header edit, now what the cipher method is...
