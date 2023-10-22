## Post #1
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-01T01:36:07+00:00
- Post Title: Deer Hunter Tournament....

I am in need of a packer/unpacker for deer hunter tournament made by south logic studios
when i use quickbms try to unpack it tells me

Error:  The Compressed  zlip/Deflate input is wrong or imcomplete <-3>
Error : There is an error with the decompresson the returned output size is negative.

i  was also  wondering if anyone knew or could make a packer for  the following games  if not its alright we can release it with folders showing.
deer hunter 2005
deer hunter 2004 
trophy hunter 2003


we are addin new animals and replacing some in the games itself  but would like a packer so we dont have to release all the folders involved. If by chance a fellow member can help out i will be sure to give credit where credit is due
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-01T08:38:04+00:00
- Post Title: Deer Hunter Tournament....

This is the new secret password the Deer Hunter Tournament uses for the .SPR archives: "winmm.lib!ddraw.lib"

First I tried to modify aluigi's DeerHunter2005 script: [http://aluigi.org/papers/bms/deer_hunter_2005.bms](http://aluigi.org/papers/bms/deer_hunter_2005.bms)

Data.Common.spk  Looks O.K. 
Data.Common.001  Looks O.K. 
Data.Win32.spk   Looks O.K. 
Data.Shaders.Win32.v1.spk  Error 
Data.Shaders.Win32.v2.spk  Error 

Deniz Özmen already wrote a .SPR maker for the Deer Hunter 2005: [http://oezmen.eu/gameresources/files/deerhunt.zip](http://oezmen.eu/gameresources/files/deerhunt.zip)
It's possible that works with the Deer Hunter Tournament too, but dont't forget to modify the password in the "MakDH2K5.dpr" source file: 
const MasterKeyPhrase: string = 'winmm.lib!ddraw.lib';
## Post #3
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-01T09:13:23+00:00
- Post Title: Deer Hunter Tournament....

Thanks
will this work on windows vista 32/64 bit or windows 7 ? i tried launchn the application but it just launchesscreen pops up and then goes away
## Post #4
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-02T23:14:23+00:00
- Post Title: Deer Hunter Tournament....

so far i havent been able to unpack DHT or pack the dh04 and 05 data files... i will try on windows xp later tonight
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-03T07:32:31+00:00
- Post Title: Deer Hunter Tournament....

I'm working on a graphical interfaced .SPK maker + extactor for DHT + DH05. (Based on work of Luigi and Deniz.)
Now it's in an early state, it can only list the contents of the .SPK file.
## Post #6
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-03T09:33:15+00:00
- Post Title: Deer Hunter Tournament....

thanks bacter
## Post #7
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-05T09:12:59+00:00
- Post Title: Deer Hunter Tournament....

could ya also implement dh2004 as well ?

we have 2004 finished but need testers but before we can get testers we need to make it and the ones above doesnt work
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-05T10:24:53+00:00
- Post Title: Deer Hunter Tournament....

Here's the first, test version of my SPK maker/extractor util.

UPDATE:
Hm. Is it possible, that my work was  unnecessary? I found a Map Editor for the Deer Hunter 2004:
[http://www.fileshack.com/file.x/4235/De ... Map+Editor](http://www.fileshack.com/file.x/4235/Deer+Hunter+2004+Map+Editor)

If you open the editor (LevelEditor2.exe), go to File menu and select Create Level Pack that also packs your level data into a single .SPK file!
## Post #9
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-05T11:50:30+00:00
- Post Title: Deer Hunter Tournament....

packer and unpacker is for the data files
 the unpackers work the packers pack but once ya launch the game it doesnt show none of ya work
where it says .SPK  Extract or Make.spk  i put file in Data.001-data.007
all the work we did did pack but it didnt load up in game


the game comes with Data.spk which has everything stored inside
Once You Unpack It It Puts It inside The Data Folder IE:

Animals ( we have new animals)
Weapons ( new weapons)
commonfx
interface ( new interface)
Items ( new items)
globals ( new deerhunter2004.txt)
language( new items.txt)
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-05T16:32:41+00:00
- Post Title: Deer Hunter Tournament....

The latest version of my SPK util!
[Attached file deleted! See my latest post for the latest version!]
## Post #11
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-05T16:35:04+00:00
- Post Title: Deer Hunter Tournament....

it all works but packing the resources back still dont work

fine tool tho for packing maps alot easier than the editors thats for sure


it also extracts data.001 - data.008 but unable to repack those resources
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-05T18:29:32+00:00
- Post Title: Deer Hunter Tournament....

Could you upload some of those tricky data.001 - data.008 files? I don't know why they don't work.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-10-05T19:24:36+00:00
- Post Title: Deer Hunter Tournament....

so bacter, what was the difference between the levels created by the editor and the main ones?
is this difference the same that didn't allow to extract Data.Shaders.Win32.v1.sp?
I need to update my scripts with these changes
## Post #14
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-05T19:48:50+00:00
- Post Title: Deer Hunter Tournament....

The DH2oo5 editor uses just another password: "dh2005custom"

I'll have some time, I'll try to describe all my experiences with the different SPK file formats, so you can merge everything to one, big, clever script.

It's possible that the script error occured, because some SPK files contain bad data.
For example: zero filesize, bad CRC32 value, some duplicated filenames, bad Flag values. (Valid Flags: 0,1,2,3, but some files have 4,8 or 16)
## Post #15
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-05T23:39:21+00:00
- Post Title: Deer Hunter Tournament....

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-10-06T07:48:06+00:00
- Post Title: Re: Deer Hunter Tournament....

well done bacter.
I have updated my dh2005 script adding a simple scanner for finding the right key of the 4 available (2005, demo, custom and tournament).

so I guess that the only problem remains in those shaders.spk archives of DHT but I don't have one of them at the moment so I can't verify them
## Post #17
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-06T09:04:26+00:00
- Post Title: Re: Deer Hunter Tournament....

Tip: Try to check the Size and the CRC32 of the Entries:
IF STOREDSIZE=0 AND CRC32=0  ---> good entry, file with zero size
IF STOREDSIZE=0 AND CRC32<>0 ---> BAD ENTRY

Example bad entries from DHT:
(storedsize#flag#originalsize#crc32#unknown#filename)
Data.Shaders.Win32.v1.spk:
 00000000#08#00000000#ED030B6F#16CA0B40#fxdata\_def_glossiness.png
 00000000#08#00000000#81B267A3#16CA0B40#fxdata\_def_heatgradient.png
 00000000#08#00000000#618B2EA4#16CA0B40#fxdata\_def_noise.png

Data.Shaders.Win32.v2.spk:
 00000000#08#00000000#ED030B6F#16B697E0#fxdata\_def_glossiness.png
 00000000#08#00000000#81B267A3#16C1DC60#fxdata\_def_heatgradient.png
 00000000#08#00000000#618B2EA4#16B697E0#fxdata\_def_noise.png



O.K. Here's every important information I collected about the .SPK files:
There are 3 different versions of SPK files, so first always check the Header's version number! (They use different Header size, and different Entry sizes!!!)

If 1 or 2, then no problem, but the 3 contains some more trick, the decoding needs a MASTER_KEY, which is game-dependant. These MASTER_KEYS are derived from some passwords:

Deer Hunter Tournament: (I didn't find demo version of the game, so this is for the full version)
  MASTER_KEY=0x48C20726  comes from this: "winmm.lib!ddraw.lib"

Deer Hunter 2005 FULL:
  MASTER_KEY=0x32E105A4   comes from this: "dh2005.exe;d3d.dll"

Deer Hunter 2005 DEMO:
  MASTER_KEY=0x3CB80690  comes from this: "d3dx.lib;ddraw.dll"

DeerHunter 2005 custom level:
  MASTER_KEY=0x18D9042F  comes from this: "dh2005custom"

Trophy Hunter 2003 + Deer Hunter 2004 use the v1 or v2 format, so they don't need password or MASTER_KEY

```

Type DeerHuntTour_SPK_HeaderType = Packed Record // 12 or 13 bytes!
       APK_ID : Array[0..2] Of char; // 'APK'
       VersionByte : byte; // (1,2 or 3)
       DirStartPos : dword; // points to the end of the file
       DirOrigSize : dword; // the original, unpacked size of the directory data
       // ----------------------------
       // This, last byte is only if the VersionByte = 3 !!!!!
       MoreCryptFlag : boolean; // 1 byte! Indicates more encryption!
     End;

The file information data is compressed (with zlib) and encrypted.
So first we need do decrypt:
If version=1 or 2 then:
  DeerHunter_Encrypt(Buffer,Hdr.DirStartPos * Hdr.DirOrigSize,FALSE);

If version=3 then:
  you can generate the MASTER_KEY, from the appropriate password:
  MASTER_KEY := DeerHunter_GenerateMasterKey('... place of the password...');
  and then:
  DeerHunter_Encrypt(Buffer,MASTER_KEY Xor Hdr.DirStartPos Xor Hdr.DirOrigSize,Hdr.MoreCryptFlagByte);

If everything is OK, the decoded buffer now contains zlib compressed data.
Unpack it. The unpacked data size must be equal to the value of Hdr.DirOrigSize

Now we can process the Entries (repeat until the end of the buffer):

Type DeerHuntTour_SPK_EntryType = Packed Record
       Name : Array Of char;  // The filename, with a terminating zero character
       StartPos  : dword;     // start of the file data
       StoredSize  : dword;   // the stored size (the compressed size, if compression used, otherwise the original size)
       FlagsByte : byte;      // 00 = stored
                              // 01 = encrypted
                              // 02 = zlib_compressed
                              // 03 = zlib_compressed+encrypted
       OriginalSize  : dword; // the original size
       CRC32  : dword;        // the crc32 value of the original file
       //-----------------------------
       // This, last dword is only if the VersionByte = 2 OR 3 !!!!!
       unknown  : dword;      // absolutely unknown value
     End;

If the file data is encypted ( (Entry.FlagsByte AND 1) = 1) then use the same decryption method as above:
If version=1 or 2 then:
  DeerHunter_Encrypt(DataBuffer,(Entry.OriginalSize * Entry.StartPos) Xor Entry.CRC32  );

If version=3 then:
  // we generated the MASTER_KEY, so we can use it again:
  DeerHunter_Encrypt(DataBuffer,MASTERKEY Xor Entry.OriginalSize Xor Entry.StartPos Xor Entry.CRC32,Header.MoreCryptFlagByte);


Function DeerHunter_GenerateMasterKey(MasterKeyPhrase : PChar) : dword;
// source: Deniz Özmen   http://oezmen.eu/gameresources/
Var I, Temp : dword;
    MasterKey : dword;
Begin {Function DeerHunter_GenerateMasterKey}
  MasterKey := 1;
  For I := 0 To StrLen(MasterKeyPhrase) - 1 Do
    Begin
      Temp := (MasterKey And $0000ffff + Ord(MasterKeyPhrase[I])) Mod $0000fff1;
      Asm
        push ebx
        mov  eax, MasterKey
        sar  eax, 16
        mov  ebx, Temp
        add  eax, ebx
        mov  ecx, $0000fff1
        cdq
        idiv ecx
        shl  edx, 16
        add  edx, ebx
        mov  MasterKey, edx
        pop  ebx
      End;
    End;
  Result := MasterKey;
End;  {Function DeerHunter_GenerateMasterKey}

Procedure DeerHunter_Encrypt(Var Buffer : TArrayOfByte;
                           Key : dword;
                           AdditionalKeyRound : Boolean);
// source: Deniz Özmen   http://oezmen.eu/gameresources/
Var I: Integer;
Begin  {Procedure DeerHunter_Encrypt}
  If AdditionalKeyRound Then // THIS CAN BE ONLY IF THE VERSION=3, OTHERWISE WE SKIP THIS!
    Asm
      mov eax, Key
      mov ecx, Key
      and eax, $0000ffff
      mov edx, $00006054
      mul edx
      sar ecx, 16
      add eax, ecx
      mov Key, eax
    End;

  For I := 0 to High(Buffer) do  // = Length(Buffer) - 1  !!!
    Begin
      Asm
        mov eax, Key
        mov ecx, Key
        and eax, $0000ffff
        mov edx, $00006054
        mul edx
        sar ecx, 16
        add eax, ecx
        mov Key, eax
      End;
      Buffer[I] := Buffer[I] Xor Key;
    End;
End;   {Procedure DeerHunter_Encrypt} 
```
## Post #18
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-07T04:40:21+00:00
- Post Title: Re: Deer Hunter Tournament....

still a no go  on packing the resources
Data/Animals  which would be Data.009
Data/Globals which would be Data.010
DataInterface which would be Data.011
Data/Weapons which would be Data.012


[http://www.deerhunterpatches.com/images/allinone.jpg](http://www.deerhunterpatches.com/images/allinone.jpg)

Devrim wont share his program and will only let us have it for 50.00 usd he said because of all the new things that will be in dh2004 and dh2005 and his works he saud he used luigi's script for unpacking and denniz's script for packin  ive tried everything and nothin happens

DHT is a whole new story we will have to find a s3d imorter/exporter for new models
## Post #19
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-07T11:29:58+00:00
- Post Title: Re: Deer Hunter Tournament....

it all works 100% i figured it out

would ya rather have forum name or real name in credits ?
## Post #20
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-07T15:38:38+00:00
- Post Title: Re: Deer Hunter Tournament....

I updated my program. Little cosmetic changes: If you open or extract a SPK file, the list jumps to the correct game version.

Unforgiven:
#1: What was the solution?
#2: You can mention my forum name (bacter) in your credits if you want.
## Post #21
- Username: Unforgiven
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Oct 01, 2010 7:23 am
- Post datetime: 2010-10-07T17:17:36+00:00
- Post Title: Re: Deer Hunter Tournament....

it was simple actually

i was tryin to pack the edited files within the game directory which would pack  but wouldnt load up in game.
so them i figured ive tried everything there is so why not try this ( this was the solution)

Right clicked on Desktop created new folder, renamed the folder Game
then inside the game folder i created a data folder

put all of our work inside of it and packed it  with ur deer hunter util and it works flawlessy  on all games
## Post #22
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-07T18:48:23+00:00
- Post Title: Re: Deer Hunter Tournament....

aluigi!
Now I solved the script problem with the "Data.Shaders.Win32.v1.spk" and "Data.Shaders.Win32.v2.spk"!
Your script, line 31-32, when you allocate some memory for the dir table decompression:
    set OUT_INFO_SIZE long INFO_SIZE
    math OUT_INFO_SIZE *= 8    # more than enough

file1: 26,656*8 = 213,248 -> but we need: 228,780
file2: 27,222*8 = 217,776 -> but we need: 228,780

So, we need some more memory, for example:
math OUT_INFO_SIZE *= 10
or, the simple and elegant way (because the header contains the uncompressed size):
    set OUT_INFO_SIZE long CRYPT_INIT
## Post #23
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-10-08T01:58:06+00:00
- Post Title: Re: Deer Hunter Tournament....

corrected, thanx bacter :)
## Post #24
- Username: deve
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 22, 2009 4:56 pm
- Post datetime: 2011-01-04T22:53:05+00:00
- Post Title: Re: Deer Hunter Tournament....

the tool works but have somebugs, like when you pack dh04 files or sometimes it just doesnt pack says only "error:("

anyway I have a question about , dh05 when the data.001 is packed and I make new changes and pack it us data.002 the game reads only the data.001 and not other data.00x , how can we fix this ?
