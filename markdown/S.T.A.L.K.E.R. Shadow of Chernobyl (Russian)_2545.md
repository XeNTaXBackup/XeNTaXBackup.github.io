## Post #1
- Username: SupHamster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Oct 18, 2006 4:55 pm
- Post datetime: 2007-03-19T12:45:54+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-22T02:04:19+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

Please attach a file more big, like 5-10 mb's of zip
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-03-22T06:55:50+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

if you are just out for unpacking and not modding then you can use
jaeder naub v2.0.3a for extracting of most of the files in those .db 
archives. mostly DDS and OGM files.

however there are some filetypes in there which im not familiar
with yet.
## Post #4
- Username: SupHamster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Oct 18, 2006 4:55 pm
- Post datetime: 2007-03-22T08:35:41+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-22T10:21:23+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: SupHamster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Oct 18, 2006 4:55 pm
- Post datetime: 2007-03-22T14:05:18+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2007-03-22T19:16:01+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

Uses some sort of really annoying encryption for filenames.

file header is [dword b] [dword b]

seek to b's value, from current, so you end up with 8 + b

then there you have [dword c] [dword d]

dword d is size of following filename/file index block

which is encrypted with a runtime generated magic table, I havn't completely figured out the table stuff yet though.

I found an unpacker that functioned on the beta/'demo' of the game but no longer functions on the full release. No source though.

If anyone feels like diving into the encryption - 00410940 (generates encryption table) and 00410A10 (decrypts data) in XR_3DA.exe (US release though, not russian).
## Post #8
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-23T07:31:22+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

Are you sure?
In xrCore.dll there's an exported funtion called CLocatorAPI::ProcessArchive that opens an archive. It also uses the structure you described with the two DWORDs. If the MSB in the second DWORD of the archive directory is set, it's compressed and a LZ-based decompression function is called with the compressed directory data. I'm currently trying to figure out the decompression, it seems to be "rather" simple.

Edit: Seems you're half right. The compressed data is indeed encrypted. In the decompression code a function pointer strangely called g_temporary_stuff is called before the data is decompressed. This function pointer is the decryption function from the Exe you mentioned.

Edit 2: Ok, I think I got the decompression done. The decrypted buffer looks more like a stream of bits than just random bytes now. Also, the first DWORD correctly shows the decompressed size now, as expected by the decompression code.
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2007-03-23T09:28:28+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

> Reply from john_doe
>
> Edit: Seems you're half right. The compressed data is indeed encrypted. In the decompression code a function pointer strangely called g_temporary_stuff is called before the data is decompressed. This function pointer is the decryption function from the Exe you mentioned.Yup, yup. That's how I found it.

> Reply from john_doe
>
> Edit 2: Ok, I think I got the decompression done. The decrypted buffer looks more like a stream of bits than just random bytes now. Also, the first DWORD correctly shows the decompressed size now, as expected by the decompression code. I saw the data in memory but didn't bother to look at it much yet since I was wanting to do the encryption first.

Nice work - do you have a working unpacker tool now? I'd like to see (source or binary is fine).
## Post #10
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-23T10:02:08+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

No, I'm not that fast 
Maybe over the weekend.
## Post #11
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2007-03-24T17:56:45+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: Wildwing
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 25, 2007 3:57 am
- Post datetime: 2007-03-25T03:27:09+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

hi ive just finished a realistic hud for the g36 rifle... but i need to compress the new file into a db file... tryed to pack it with a normal zip and renamed it but it dosnt work that way... got the following error massage: 

Expression    : assertion failed
Function      : CLocatorAPI::ProcessArchive
File          : D:\xray-svn\xrCore\LocatorAPI.cpp
Line          : 331
Description   : hdr

i think the game demands a original compressed file...
so if anyone has got an compression tool for that db files or could tell me a console or cmd line way, would be great... got to replace this ugly visor...
## Post #13
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2007-03-25T05:59:25+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

> Reply from Wildwing
>
> hi ive just finished a realistic hud for the g36 rifle... but i need to compress the new file into a db file... tryed to pack it with a normal zip and renamed it but it dosnt work that way... got the following error massage: 

Expression    : assertion failed
Function      : CLocatorAPI::ProcessArchive
File          : D:\xray-svn\xrCore\LocatorAPI.cpp
Line          : 331
Description   : hdr

i think the game demands a original compressed file...
so if anyone has got an compression tool for that db files or could tell me a console or cmd line way, would be great... got to replace this ugly visor...Files in the archives take precedence over files on the filesystem. :\ So you can extract the archives then rename/delete/move the archives away so that the game loads from the harddrive rather than the archives.
## Post #14
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2007-03-25T09:37:53+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

I see the people from GSC forums [found us](http://www.gsc-game.com/main.php?t=community&s=forums&s_game_type=xr&thm_page=1&thm_id=4890&sec_id=16).
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-25T10:51:05+00:00
- Post Title: S.T.A.L.K.E.R.: Shadow of Chernobyl (Russian)

Thanks, but what encryption/compression whas used?
## Post #16
- Username: Wildwing
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 25, 2007 3:57 am
- Post datetime: 2007-03-25T14:15:20+00:00
- Post Title: 

figured it out... just got to create a new "gamedata" folder and put my tree there... so theres my crosshair, hf 

[http://rapidshare.com/files/22710119/cr ... g.rar.html](http://rapidshare.com/files/22710119/crosshair.g36.wildwing.rar.html)

[http://mitglied.lycos.de/mldl01/misc/cr ... ldwing.jpg](http://mitglied.lycos.de/mldl01/misc/crosshair.g36.wildwing.jpg)
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2007-03-25T15:25:40+00:00
- Post Title: 

You can turn on disk file precedence on by editing fsgame.ltx.

Open up fsgame.ltx in your root game directory, find:

```
$game_data$   		= false|	true|	$fs_root$|		gamedata\
```


Change that 'false' to 'true'.
## Post #18
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-25T20:23:02+00:00
- Post Title: 

Hmm, I guess the authors of the two tools just copied the disassembled assembly and didn't reverse engineer it, so the exact workings of the (de)compression are still unknown. At least the exisiting tools "satisfy the customer" , and I have more time to figure out the decompression.
## Post #19
- Username: Wildwing
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 25, 2007 3:57 am
- Post datetime: 2007-03-26T21:08:28+00:00
- Post Title: 

does anyone know in wich file you can rename the weapons?
## Post #20
- Username: Kye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2007 6:23 am
- Post datetime: 2007-03-28T13:21:08+00:00
- Post Title: 

Hey.

Ive successfully unpacked the db files, and been going through them. The main issue was the prices of everything, which is easy to find. Changing the damage to x2 is not. Is there not some universal paramater i can change to make all weapons x2 damage?

Also, if someone who knows can tell me where i can change the respawns i would be very grateful. Im sorry, if what im asking is a little below what is expected from this forum. The main GSC forum has been down for almost 3 days!

Kye.
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-02T20:30:10+00:00
- Post Title: 

old thread, new informations :)
for the people interested in the encryption and the compression adopted in this game series I have written a quickbms script (is required quickbms 0.3.10 to use it!) based on the reversing performed today:
[http://aluigi.org/papers/bms/stalker.bms](http://aluigi.org/papers/bms/stalker.bms)

seems that only STALKER Shadow of Chernobyl used that "useless" encryption of the information table while after having scanned all the files of these games I have found no archives containing compressed files (because the archives have both a compressed and uncompressed size for each file) so contact me if you have one of them

in my opinion it's interesting to notice that the game uses a compression algorithm very similar to the not-much-known LZAH, but I was too lazy to reverse it and finding the differences so... I simply dumped it :)
