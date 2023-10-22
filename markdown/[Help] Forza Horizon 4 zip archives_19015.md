## Post #1
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2018-11-04T06:40:08+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

I need help decompressing the files within the zip archives from Forza Horizon 4


[Camera.zip](https://xentaxbackup.github.io/file/15120_Camera.zip)
## Post #2
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2018-11-20T03:38:07+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

use forza studio 4.1 to decrypt forza archives
## Post #3
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2019-04-26T20:57:14+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

ForzaStudio will only unpack decrypted archives.
## Post #4
- Username: Reclaimer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 31, 2016 12:14 am
- Post datetime: 2021-02-06T15:14:29+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

Did you have any success?
## Post #5
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2023-07-02T14:29:18+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

Is there a fh4 zip extractor?
## Post #6
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-17T21:37:23+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

In continuation of the conversation started in [Forza Apex database - gamedb.slt](https://forum.xentax.com/viewtopic.php?p=193216#p193216) about encrypted zip archives in Forza Horizon 5 v1.405.2.0 (Steam) [EMPRESS] (ForzaHorizon5.exe CRC32: BFCEECA8).
I found a way to extract .txt and .dat files for now. The archive header is not encrypted, so we can see the name, size and crc32 of the stored files.
After CreateFile breakpoint reached, place another one at <vcruntime140.dll.memmove> or at more stable 0000000145509E3D with the condition: qword(rdx) == 656C74746F726854 || byte(rdx) == 30 && byte(rdx + 1) == 0D && byte(rdx + 2) == 0A, where 656C74746F726854 is the beginning of .txt file "Throttle" in big endian, and 30 0D 0A is the first line of .dat file "0\r\n". To save the result use: savedata :memdump:,rdx,r8.
[](https://fastpic.org/view/122/2023/0717/_17178fc31a234152cde7bfa39e2f49af.jpeg.html)

It calls in the following order:

```
Exh_Acc_G_I6TTC_Asian_Street_1_Acc_Sweep_GS.dat
Exh_Dec_G_I6TTC_Asian_Street_1.txt
Exh_Dec_G_I6TTC_Asian_Street_1_Dec_Sweep_GS.dat
```


The call stack related to decompressing the encrypted zip file.

```
0000000145508C1C
0000000140F45C66
0000000140F3BC2A
```


There are other .zip files encrypted in the same way, such as "media\Stripped\TIDETables.zip". It loads right after the game executable is launched, so this is a good place to start. It contains files with "BXML" at the beginning: qword(rdx) == 4C4D5842.

Once I got G_V8NM_American_Truck_1_Eng.zip/Acc_01_Acc_2438_ADPCM.wav file, but I can't reproduce it anymore. Now the game crashes or all threads are suspended. Luckily I took two screenshots and saved the file. I used the car FOR_SVTRaptor_12.
[](https://fastpic.org/view/122/2023/0717/_ecdc8e9a49518653f21f8b82ce362307.jpeg.html) [](https://fastpic.org/view/122/2023/0717/_5cb10ff2d2a361b0b06fcb9713bb4c69.jpeg.html)

All mentioned files are in an attachment (four .txt and .dat, and one .wav).
[EngineSynth.7z](https://xentaxbackup.github.io/file/24082_EngineSynth.7z)
## Post #7
- Username: umisery
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 21, 2018 12:17 pm
- Post datetime: 2023-07-18T01:51:55+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

@Doliman100 I think I love you. The information you're providing to the Forza community right now is invaluable, thank you so much.
## Post #8
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-20T15:48:23+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

I found a way to extract both files compressed with the common methods and files compressed with method 22. The game usues some method of class IOSys::CCompressedFileStream (d:\p4\woodstock_hf\engine\iosys\Src\CompressedFileStream.cpp) for this. So, if someone wants to make a quickbms script for decompressing method 22, you are welcome. By the way, the ForzaHorizon5.exe file from the EMPRESS crack (v1.405.2.0, CRC32: BFCEECA8) can be decompiled by IDA Pro, because EMPRESS has already unpacked it. This version has an Arxan log that can be downloaded separately. You can use it to see some class names and their methods.

```
  rcx: looks like IOSys::CCompressedFileStream *
    [rcx+30]: pointer to some class
      [[[rcx+30]]+110]: GetVolumePath
      utf8([[rcx+30]+30]): volume_path "C:\Program Files (x86)\DODI-Repacks\Forza Horizon 5\media\stripped\tidetables.zip"
  r8: char *destination
  r9: int filesize
```


At the moment, I don't know how to get the file names, only the full path to the archive. To extract media\Audio\EngineSynth\*.zip files, you can place a breakpoint at these two addresses. They are right after the call to that decompress function.

```
000000014075D762 wav + dat
```


0. In x64dbg/memdumps/ directory, create folders with the names of the zip files you want to export.
1. Debug > Run
2. Command
For txt: savedata memdumps\{utf8([rbp+258]+1E)}{utf8([rbp-40])},qword(rsp+58),r14d
For wav and dat: savedata memdumps\{utf8([rbp+F]+1E)}{utf8([rbp-59])},qword(r14),dword(rsi)
3. Goto step 1
If you have doubts about what you've saved, you can always compare it to CRC32.

I tested it with TOY_SupraRZ_98 "Toyota Supra RZ (1998)". Here are 7 decompressed zip files that it uses.
[https://mega.nz/folder/jsQFmSZD#5Y65-CrrT8PLMa2bvdX3GA](https://mega.nz/folder/jsQFmSZD#5Y65-CrrT8PLMa2bvdX3GA)

```
G_I6TTC_Asian_Street_1_Int
G_I6TTC_Asian_Street_1_Exh
G_I6TTC_Asian_Street_1_InL
G_I6TTC_Asian_Street_1_InR
Turbo_I6TC_Asian_Street_6_Tbo
Transmission_V6TTM_American_Supercar_1_Trn
```
## Post #9
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-20T20:01:52+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

amazing! Ill try extracting some more samples with this!

as for making a quickbms script, i don't have the necessary knowledge, but maybe some one who reads this can!
## Post #10
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-21T05:22:53+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

i was successfully able to extract the .txt's, but when trying to extract the wav's i'm having a memory allocation error and the software crashes, is there any aditional step for the wavs?

i'm able to successfuly create the breakpoint
## Post #11
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-21T07:03:27+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

What version of Forza Horizon 5 are you using? What is the exact error message? At what step does the error occur? Does this happen right after entering the command for wav and dat files in step 2? What car and zip file are you trying?
## Post #12
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-21T08:13:19+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

I think I reproduced it. The problem was the wrong type of the size variable. Now I have defined it explicitly. Try these commands instead:

```
savedata memdumps\{utf8([rbp+F]+1E)}{utf8([rbp-59])},qword(r14),dword(rsi)
```
## Post #13
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-21T18:10:56+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

Hi, sorry for the lack of information in the preivous post, but yes! indeed your new approach works! thank you for your work, you've finnally put an end in this 2 year long quest!

for anyone else who'd like to try, i've used the 1.405 verison, with empress crack.

i, and i think the whole community, truly appreaciate the work you've done

i wish you the best!
## Post #14
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-24T17:15:34+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

I confirmed that method 22 is encrypted the same way as stage 1 of .slt powered by Arxan TransformIT. After decryption, this is the usual method 8 (Deflate).
## Post #15
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-26T00:56:38+00:00
- Post Title: [Help] Forza Horizon 4 zip archives

is it there a known "decryptor" for such a method?
## Post #16
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-26T12:15:13+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

It seems that the RAGE engine on which the GTA and RDR series are based also uses Arxan's TransformIT. I found two projects for decrypt their resources.
[https://github.com/Neodymium146/gta-too ... ryption.cs](https://github.com/Neodymium146/gta-toolkit/blob/master/RageLib.GTA5/Cryptography/GTA5Encryption.cs)
[https://github.com/0x1F9F1/Swage/blob/m ... /tfit2.cpp](https://github.com/0x1F9F1/Swage/blob/master/src/crypto/tfit2.cpp)

There is an open source messenger that uses TransformIT. The developer has also uploaded the TransformIT 8.0 evaluation kit headers. By the way, the game uses GuardIT 10.5.2.154616 x64.
[https://github.com/EOSIO/mojey/blob/mai ... FIT/TFIT.h](https://github.com/EOSIO/mojey/blob/main/MojeyCommon/Arxan/TFIT/TFIT.h)

The file structure of encrypted files is described here [https://github.com/Nenkai/010GameTempla ... za/TFIT.bt](https://github.com/Nenkai/010GameTemplates/blob/main/Forza/TFIT.bt). Here are my notes:

```
  u8[16] IV?
  u32 padding -- amount of zeros at the end of the last block
  u8[16] unknown
}
Block {
  u8[200 or 20000] encrypted_data
  u8[16] MAC?
}
```

The header is used by class Crypto::DecryptionStream constructor.

```
0000000141D8E4A0: public: __fastcall Crypto::DecryptionStream::DecryptionStream(class TReference<class IOSys::CBinaryStream, struct ReferencePolicy<class IOSys::CBinaryStream>, struct NonThreadSafeReferencePolicy> const &, class TReference<class Crypto::ICryptoProvider, struct ReferencePolicy<class Crypto::ICryptoProvider>, struct NonThreadSafeReferencePolicy> const &, bool, unsigned long)
  rcx: Crypto::DecryptionStream *
  rdx: IOSys::CAutoMemoryStream::CAutoMemoryStream *
  r8: Crypto::TransformITCryptoProvider<class nullkeywrapper, class keywrapper_sfs_decryptionkey, class keywrapper_sfs_mackey> * -- stores 16-byte fields from the header.
  [rsp+20]: data_block_size -- 0x20000
```

The data is used by some method of that class. Looks like Crypto::DecryptionStream::ReadFile(...) except for rdx argument.

```
0000000141D8FAF0: public: virtual class Core::ErrInfo __fastcall Crypto::DecryptionStream::ReadData(void *, long, long &) -- maybe
  rcx: Crypto::DecryptionStream *
  rdx: Crypto::DecryptionStream ** -- null after return
  r8: void *destination
  r9: u32 data_size -- 0x4F80000
  [rsp+20]: u32 *data_size_out -- 0x4F80000
```


The values are given for the media/sfsdata file, because it is the very first file loaded.

file size: 0x4F827E4
data size: 0x4F80000
block size: 0x20000
padding: 0x6797
decrypted file size: 0x4F79869
## Post #17
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-27T03:46:46+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

I'm not sure if it will help much, because this is way out of my scope, but i did some look into the 2 unknown vars

BaseIV might refer to Initialization Vector, 

which according to google is:

"is an arbitrary number that can be used with a secret key for data encryption to foil cyber attacks. This number, also called a nonce (number used once), is employed only one time in any session to prevent unauthorized decryption of the message by a suspicious or malicious actor."

As for the MAC i could think of mac address but that wouldn't make any sense
## Post #18
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-30T17:38:33+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

I am working on a standalone application that decrypts such files. Demo console utility in attachment. It only supports non-archived files that use the "file" decryption key from Forza Horizon 5, such as .xml and .ini. FH5 and FH4 use the same table, some other keys for them are included in keys.h file.
I want to package it as a 7-Zip plugin, but feel free to suggest your ideas. After that I'll add the following:

keys to all other games since FM6Apex
archive support
gamedb deobfuscator
MAC (Message Authentication Code) support
trimming padding zeroes at the end

There are several problems.

Encrypted files don't have any information other than the file size. So there is no way to determine which game version or decryption key to use. It has to brute force over all known keys and tables, which is currently 5 * 6 = 30 attempts. MAC can be used for verification.
Same for the block size. It can be either 0x200 or 0x20000 bytes. Although it may depend on a key. I've only seen 0x20000 for sfsdata and gamedbRC.slt.
The decryption algorithm uses a table of 278528 bytes supposedly unique for each game and several keys of 272 bytes each.

Here are some related functions.

```
  rcx: decryption keys
  rdx: source encrypted
  r8: size 0x200 or 0x20000
  r9: 0x10
  [rsp+20]: destination decrypted
0000000145511A60: fun DecryptBlock
  rcx: decryption keys
  rdx: source encrypted
  r8: destination decrypted
0000000145505770: fun CalculateMAC
  rcx: keys
  r8: u32 0x18
  r9: destination calculated MAC

```

By the way, here is a list of keys from Forza Horiozn 5. They are stored in memory in an encrypted form and decrypted for short periods of time as needed. So, in order to automatically extract them from the executable dump, reverse engineering of their decryption algorithm is required.

```
keywrapper_profile_decryptionkey
keywrapper_profile_mackey -- User_69C2EF99.ProfileData, User_69C2EF99.VersionFlags

keywrapper_gamedb_decryptionkey
keywrapper_gamedb_mackey -- gamedbRC.slt

keywrapper_file_decryptionkey
keywrapper_file_mackey -- .zip, .xml, .ini

keywrapper_sfs_decryptionkey
keywrapper_sfs_mackey -- sfsdata

keywrapper_photo_encryptionkey
keywrapper_photo_decryptionkey
keywrapper_photo_mackey -- Photo_0000_20211112155819.header, Photo_0000_20211112155819.image, Photo_0000_20211112155819.metadata, Photo_0000_20211112155819.thumb

keywrapper_dynamic_encryptionkey
keywrapper_dynamic_decryptionkey
keywrapper_dynamic_mackey -- CustomRoute_0000_20211112181230.header, CustomRoute_0000_20211112181230.RouteData

keywrapper_telemetry_encryptionkey

```

As you can see, there is a profile encryption key, so the executable also has the encryption part of this asymmetric algorithm. It also seems possible to make a "save editor".
[TransformIT.7z](https://xentaxbackup.github.io/file/24142_TransformIT.7z)
## Post #19
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-08-03T00:53:14+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

that is very nice, we appreaciate alot what you're doing!
## Post #20
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2023-08-07T16:58:55+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Will there be a method 22 .zip decryptor made? Would love to get the .wav from fh4 and fh5 finally after so many years.
## Post #21
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-08-07T18:17:08+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Here is the decryptor for any file (.ProfileData, .LevelRewardCache, .RouteData, .image, sfsdata, .ini, .xml, ...) from any game sice FM6Apex up to FH5 but .zip, second stage of gamedb.slt and sfsdata of FM7. By calculating the MAC, it automatically tries all existing keys until it finds the right one. Since the Forza Motorsport file format doesn't have a padding size, it just trims trailing zeros, which may be incorrect if they are part of a file.
I'm currently working on gamedb.slt deobfuscation. After that, I'll move to .zip support.
This is a command line utility that accepts two arguments: input and output file paths.

```
D:\downloads\TransformIT\TransformIT.exe "C:\Program Files (x86)\DODI-Repacks\Forza Horizon 5\media\Physics\PI.xml" "PI.xml"
```

Please, post here if it can't decrypt some file.
[https://mega.nz/file/K9JClBLT#U95oWc7Yk ... K6y7oCqDVE](https://mega.nz/file/K9JClBLT#U95oWc7YkwHmXL2LqTqROkw-kQNZ7BM11K6y7oCqDVE)
## Post #22
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2023-08-07T19:07:04+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from Doliman100 ↑Tue Aug 08, 2023 2:17 am at Tue Aug 08, 2023 2:17 am
>
> 
Here is the decryptor for any file (.ProfileData, .LevelRewardCache, .RouteData, .image, sfsdata, .ini, .xml, ...) from any game sice FM6Apex up to FH5 but .zip, second stage of gamedb.slt and sfsdata of FM7. By calculating the MAC, it automatically tries all existing keys until it finds the right one. Since the Forza Motorsport file format doesn't have a padding size, it just trims trailing zeros, which may be incorrect if they are part of a file.
I'm currently working on gamedb.slt deobfuscation. After that, I'll move to .zip support.
This is a command line utility that accepts two arguments: input and output file paths.
Code: Select allD:\downloads\TransformIT\TransformIT.exe "C:\Program Files (x86)\DODI-Repacks\Forza Horizon 5\media\Physics\PI.xml" "PI.xml"
Please, post here if it can't decrypt some file.
https://mega.nz/file/K9JClBLT#U95oWc7Yk ... K6y7oCqDVE

This is simply genius.....

Can you post how i run it from command line step by step?

For those that are only interested in the engine, exhaust and intake audio it would be very handy to have a program that extracts all files from the .zip and makes a new folder and puts them in there. For example all the contents of "G_V10NM_European_Supercar_2_Exh.zip". Because many people who want the audio files are not that good on computers.
## Post #23
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-08-08T00:08:33+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

you can already extract audio files using x64 dbg, it is extremely easy, just read the previous posts
## Post #24
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-08-08T04:12:01+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

I tried to figure out how to build it as 7-Zip plugin or quickbms script but it's too complicated due to lack of documentation. For 7-Zip, I don't know how to make it open alone files that aren't part of an archive and detect that file needs to be decrypted without trying all keys on every file that you extract, which will affect performance.
As for quickms, I couldn't figure out how to make it to support non-hardcoded keys.
So if anyone can make something more convenient, you are welcome. Sources are available inside the archive.
## Post #25
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2023-08-10T16:28:58+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from smurf100 ↑Tue Aug 08, 2023 8:08 am at Tue Aug 08, 2023 8:08 am
>
> 
you can already extract audio files using x64 dbg, it is extremely easy, just read the previous posts

If i wanted to extract the .wav only from the method 22 zip i can do this how using that?
## Post #26
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-08-10T16:49:21+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from Doliman100 ↑Thu Jul 20, 2023 11:48 pm at Thu Jul 20, 2023 11:48 pm
>
> 

read this
## Post #27
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-08-12T05:00:40+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

I've added support for gamedb deobfuscation and .zip. It just takes off the encryption from .zip without extracting files. All flags and fields are untouched, so I think you can decrypt files from the latest version of FH3 and use them in OpusDev. I also removed zero trimming from FM files as it is too inaccurate. The next step is to support encryption for .ProfileData and others that have an encryption key.

I also added boost::program_options so it's more user friendly now.

```

```


Here is a list of encrypted .zip files from FH5 and FH3.

```
media\Audio\EngineSynth\*.zip
media\Stripped\TIDETables.zip
media\Camera.zip
media\EntityModel.zip
media\GameTunableSettings.zip
media\ProfileSchema.zip
media\Rendering.zip
media\RenderScenarios.zip
media\Rules.zip
media\stateflow.zip

-- FH3
media\audio\enginesynth\pc\*.zip
media\camera.zip
media\entitymodel.zip
media\gametunablesettings.zip
media\matchmakingstateflow.zip
media\profileschema.zip
media\rules.zip
media\stateflow.zip

```


Upd 1. Fixed an unexpected end of data error.
Upd 2. Fixed zero file size error and added support for offset recalculation for extra field 0x1123.
Upd 3. Fixed zero file skipping caused by previous fix.
[https://mega.nz/folder/T5IkFIbB#obP-SfTD2Y2MyaqXPAuwlg](https://mega.nz/folder/T5IkFIbB#obP-SfTD2Y2MyaqXPAuwlg)
## Post #28
- Username: Skajdrovski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 07, 2020 7:09 am
- Post datetime: 2023-08-12T12:18:15+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Thank you for the tool. I've successfully decrypted 'GameTunableSettings.zip', but when I try 'Rules.zip' file, program returns this:

```
File name: ANNAVO.rulebot.bin
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 430
Data size: 0x200
IV: BB 03 0E CC 4C F1 95 56 91 58 85 4B F7 44 44 40

File name: ANNAVO.rulebot.xml
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 414
Data size: 0x400
IV: C1 84 5E 65 25 2E 9C 2E C8 CF 2F 46 CC 0B 81 FD

File name: AnnouncerVO.rulebot.bin
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 408
Data size: 0x200
IV: D5 1B 7B 41 36 C2 8E 69 46 DC 84 DF E8 41 5C 11

File name: AnnouncerVO.rulebot.xml
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 477
Data size: 0x400
IV: 98 9F 05 DC 8A 1D AD 6B D9 BE 87 A2 CA 64 2E 17

File name: Asphalt_Expedition.rulebot.bin
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 248
Data size: 0x200
IV: 23 D9 8F EA 5D C6 0D 6D C1 D8 E1 00 5B 21 F5 FA

File name: Asphalt_Expedition.rulebot.xml
Game: Forza Horizon 5
Key: File
Data block size: 0x200
Padding size: 474
Data size: 0x600
IV: FF 91 FA D7 F1 3D 9C 21 A0 05 95 BB BC F2 8A EF

File name: AstraFreeroam.rulebot.bin/
Error: None of the keys matched.

```


> Code: Select all-- FH5
>
> media\Rules.zip
## Post #29
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-08-12T12:36:09+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Send me the original zip file and which game version do you use? The file from 1.405.2.0 (Steam) [EMPRESS] decrypts well.
[](https://fastpic.org/view/122/2023/0812/_80402a846f42c6c69455636ed46a0bd9.png.html)
## Post #30
- Username: Skajdrovski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 07, 2020 7:09 am
- Post datetime: 2023-08-12T13:09:24+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

I'm using the latest version (3.604.481.0) from Microsoft Store. 
[https://drive.google.com/file/d/1_ESQU3 ... sp=sharing](https://drive.google.com/file/d/1_ESQU30m_Fke9HThO0D0W-1_FCPZaTGn/view?usp=sharing)
## Post #31
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-08-12T14:57:10+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

The link updated. Check the v3.2.
## Post #32
- Username: Skajdrovski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 07, 2020 7:09 am
- Post datetime: 2023-08-12T15:10:05+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Works
[Screenshot 2023-08-12 170831.png](https://xentaxbackup.github.io/file/24219_Screenshot 2023-08-12 170831.png)
## Post #33
- Username: KyoJinVAN
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 21, 2021 5:50 pm
- Post datetime: 2023-09-04T07:54:46+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from smurf100 ↑Fri Aug 11, 2023 12:49 am at Fri Aug 11, 2023 12:49 am
>
> 
Doliman100 wrote: ↑Thu Jul 20, 2023 11:48 pm


read this

idk why but that whole x64 dbg method i find really hard and stuff. btw can i get a walkthrough on how to use TransformIT to decrypt a file since i can't figure it out
## Post #34
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-09-04T08:04:23+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from KyoJinVAN ↑Mon Sep 04, 2023 3:54 pm at Mon Sep 04, 2023 3:54 pm
>
> 
Someone from Forza Mods discord server made a detailed guide with pictures. Btw, it's no longer necessary to use x64dbg, it's only for developers who want to know how it was achieved.
[https://gist.github.com/TehChozinOne/6f ... 0045869cf4](https://gist.github.com/TehChozinOne/6f32ccddbf6091356480be0045869cf4)
## Post #35
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-05T11:29:40+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

@Doliman100 : Thanks for all your work. I didn't look into your implementation, but if you're interested how dynamic data can be used from external file in quickbms, it would be something like this:

```
string NAME p "decrypted/%s" NAME	# output file will be in "decrypted" subfolder of output folder
					# thus you can extract in the input folder, it will create subfolder anyway
									
open FDSE "keys.txt" 2			# open keys.txt as 2 file, it should exist in the same folder as input file
					# also it can be placed in output folder, then instead of FDSE -> "." should be used
									
# all of the variables can be hardcoded or read from input file / external file
# here both KEY and IV are read from external file, assuming they're stored as binary data there
goto OFFSET 2						
getdstring KEY KEY_SIZE 2
getdstring IV IV_SIZE 2
encryption aes KEY IV 0 KEY_SIZE
clog NAME POSITION ZSIZE SIZE 		# here 2 is not used, since this operation is related to original input file (0) and 0 can be omitted
encryption "" ""
```


Unfortunately after zenhax closure a lot of test code samples from alugi became unavailable, but you can still use [official documentation](https://aluigi.altervista.org/papers/quickbms.txt) and scripts from quickbms site as examples.
## Post #36
- Username: TGR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 12, 2023 11:56 pm
- Post datetime: 2023-09-14T23:21:40+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

The extractor doesn't work anymore with the FH5 latest patch (PC 3.614.70.0)
## Post #37
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-09-15T03:38:20+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

TGR, please send any proof. Which file makes problem? What tool version are you using? The latest game version requires at least tool v4.2.
## Post #38
- Username: TGR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 12, 2023 11:56 pm
- Post datetime: 2023-09-15T06:26:12+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

> Reply from Doliman100 ↑Fri Sep 15, 2023 11:38 am at Fri Sep 15, 2023 11:38 am
>
> 
TGR, please send any proof. Which file makes problem? What tool version are you using? The latest game version requires at least tool v4.2.

Sorry, my bad. I didn't check for the latest version on mega
## Post #39
- Username: Zonda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 24, 2021 1:29 am
- Post datetime: 2023-10-12T21:27:06+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Seems to not be able to find keys in latest version.
## Post #40
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-10-13T04:12:20+00:00
- Post Title: Re: [Help] Forza Horizon 4 zip archives

Yes, the developers screwed it up again. It seems they will continue to do this with every update. I don't have time for this. I will release an update at the end of life of this game.
