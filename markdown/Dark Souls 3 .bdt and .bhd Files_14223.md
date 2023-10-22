## Post #1
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-13T13:22:09+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

I would like to know if anyone can break the encryption of dark souls 3's files
here is sample of the files BDT and BHD:
[https://drive.google.com/folderview?id= ... aring#grid](https://drive.google.com/folderview?id=0ByoZQWl-HzbMQ2lfaURNMlk1RDg&usp=sharing#grid)
## Post #2
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2016-04-13T15:56:51+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

Me too. More specifically, I would like to extract all the textures and item images from these files. Hope someone can figure this out 

EDIT: Managed to extract the bdt files partially using offzip.

Now I have a folder full of TPF files that I can't see to open. I tried using Rick's tools but it crashes every time I try (so probably incompatible)

Anyone have any ideas on how to work with these TPF files?
## Post #3
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-13T17:18:06+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

can you please post step-by-step how you were able to extract them using offzip?
the tpf files I think there is a tool with Rick Tewls that can extract tpf files 

EDIT: i tried using Offzip but it uses a different zip format or something....
## Post #4
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-13T19:10:59+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

If you can explain on how to unencrypted the files, I'll be glad to look into the TPF files.
## Post #5
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2016-04-14T13:26:16+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

I have already tried using Rick's Tools unpack the TPF files, but like I said, the tool crashes.

Here's how I unpacked them using offzip. Thanks to chrrox's post in this thread: [viewtopic.php?f=10&t=7453&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=7453&start=15)

Optional steps but make the process a bit easier:
1. Copy the relevant Data.bdt file to your system's root for ease of access. (Data5.bdt contains all the TFP files as far as I know)
2. Create a new folder on that same drive in root called extract.
3. Copy your offzip folder to the same drive's root

Your folder structure should look something like this now:

```
D:\offzip
D:\extract
```

Extracting the files
4. Run the windows command line as Administrator by going to Start and typing cmd, then right click cmd.exe and choose Run as Administrator
5. Write the command line to unpack the files. Look at the optional steps to see why I use these paths. For me it was the following:

```
D:\offzip\offzip.exe -a D:\Data5.bdt D:\extract 0x0
```


6. Press Enter and let it run until finished.
7. Share any new information you may find out in this thread 

Note that you will probably see a lot of errors. So far, I've only been able to successfully extract most files from Data5.bdt. (About 7GB worth of TPF files) The other Data*.bdt files have barely extracted any content for me. Maybe someone can figure out how to properly extract those files as well.
## Post #6
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-14T13:58:24+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

Okay so I was able to extract multiple .BND files from Data3.bdt and I tried using BinderTool to extract them but I come up with a files named "N" with no extension. Maybe we are getting closer

EDIT: Okay I was able to extract the BND files using offzip command. I came up with alot of extensions including dat and txt.
## Post #7
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-16T02:17:50+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

Extracting the BDT files right now, but you should be able to open the TPF texture files with a hex editor and see if it's a DDS file with a TPF header. That's what it was like for Demon Souls, Dark Souls, DSII, and DSII SotFS.

It also looks like all the filed named N are also DDS files with a TPF header, and all the WAAW files I believe are HKX animations. The DAT files seem to be the engine's coding for shaders and lighting.
## Post #8
- Username: HunterAP
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-04-16T18:35:54+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

not sure what are you doing now but DS3 is supported... [https://github.com/Atvaark/BinderTool](https://github.com/Atvaark/BinderTool)
## Post #9
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-16T19:44:13+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

How can I use the source files? I can't seem to find an exe version and I have no experience in compiling programs whatsoever....
## Post #10
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-04-17T00:06:53+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

i get a error when trying to use the binder tool

C:\WINDOWS\system32>D:\binder\BinderTool.exe D:\A\Data5.bdt D:\Extract

Unhandled Exception: System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadInt32()
   at BinderTool.Core.Bhf4.Bhf4Entry.Read(Stream inputStream) in c:\Users\Tim\Documents\GitHub\BinderTool\BinderTool.Core\Bhf4\Bhf4Entry.cs:line 27
   at BinderTool.Core.Bhf4.Bhf4File.Read(Stream inputStream) in c:\Users\Tim\Documents\GitHub\BinderTool\BinderTool.Core\Bhf4\Bhf4File.cs:line 78
   at BinderTool.Program.UnpackBdf4File(Options options)
   at BinderTool.Program.Main(String[] args)
## Post #11
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-17T01:53:46+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

pewposterous, this happens when you don't spell the BDT filename correctly, BinderTool is case sensitive.
## Post #12
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-04-17T03:10:04+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

Thanks for the help but im not sure i follow. I type this "D:\binder>BinderTool.exe D:\A\Data5.bdt D:\Extract". This is all case sensitive as far as i can tell and ive triple checked that im spelling everything right. Am i missing something?

I even tried copying the bdt/bhd files into the binder tool folder and mounting from there "D:\binder>BinderTool.exe Data5.bdt" but still get the same error
## Post #13
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-17T04:06:10+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

Some things to note:
The new version of BinderTool doesn't have a file name / folder hierarchy dictionary, so all the files are just named after thier archive with a hash after them, making finding what textures relate to what models nearly impossible. This mean even if you got all the files out, you'd spend months to try to arrange the files accordingly. Might as well wait until an update that includes a dictionary comes out.

Secondly, and also ironically, the updated BinderTool actually found less TPF files than using offzip. BinderTool also has trouble with all the DCX files, but I tried offzip and it seemed to work fine (but without any file naming whatsoever). Whatever DCX files BinderTool did unpack, it unpacked BND files without the BND extension, making the process just that much harder to deal with. I haven't tried out using offzip yet, but I'll look into it.

I'd still recommend waiting until a file/folder dictionary is created, you won't get far from unpacking a bunch of unnamed/unstructured files.
## Post #14
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-17T16:03:43+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

> Reply from pewposterous
>
> Thanks for the help but im not sure i follow *snip*

I'm not sure what the problem is then, I put BinderTool and its required DLLs in my path and call it without specifying the absolute path to the exe, but looking through the source that shouldn't make any difference at all and it'd be weird if that was your problem. I managed to unpack by following the readme instructions exactly, but as HunterAP states above, it's not incredibly useful at this point. I'll look more into it during the upcoming week as well as seeing if ResoRep can be used for texture replacement.
## Post #15
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2016-04-18T00:31:20+00:00
- Post Title: Dark Souls 3 *.bdt and *.bhd Files

So, has anyone been able to successfully extract and view any of the game's files yet? Personally, I'm most interested in the texture files, item images and sound files. Has anyone been able to extract these in a usable format yet?
## Post #16
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-18T06:38:02+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

From what I've seen, so far all menu items are like previous games, actual model's textures are in DDS format with DX10 headers (meaning they are indeed PBR). I haven't gone through the hassle of converting anything to actually look, but the DX10 header is almost always an indication that PBR is being used. Right now it's just really hard to find anything since nothing is structured.
## Post #17
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-18T21:41:51+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Swennet
>
> So, has anyone been able to successfully extract and view any of the game's files yet? Personally, I'm most interested in the texture files, item images and sound files. Has anyone been able to extract these in a usable format yet?

It's easy to get stuff like this:

[http://imgur.com/a/7Lac9](http://imgur.com/a/7Lac9)

It's hard to actually do anything with it
## Post #18
- Username: tehopeologist
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2016 11:39 pm
- Post datetime: 2016-04-18T22:12:42+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Zoetropes
>
> Swennet wrote:So, has anyone been able to successfully extract and view any of the game's files yet? Personally, I'm most interested in the texture files, item images and sound files. Has anyone been able to extract these in a usable format yet?

It's easy to get stuff like this:

http://imgur.com/a/7Lac9

It's hard to actually do anything with it

how were you able to extract those?  i have the extracted files using the bindertool, but i haven't been able to figure out which files are textures/etc.  could you elaborate on how you got those images?  thanks!
## Post #19
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-20T21:49:12+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Like I said before, you can open the files if they don't have an extension in a Hex editor program. If the extension is TPF or there no extension and the Hex Editor shows the first thre characters are TPF, then it's a DDS with a special header that needs to be removed.
If the extension is HKX or the Hex Editor shows the first few characters are WaaW, then it's animation/skeletal bone files.

So far we can't seem to find any other files.
## Post #20
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2016-04-24T23:31:55+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

FROM Software has been stepping up their game in hiding their data with each iteration of Dark Souls.

Here's some info about the files so far:
The root archives are composed of 2 files each: A .BHD file (header), and a .BDT file (data). Historically, these files are slightly different than the similarly named .BHD/.BDT files contained inside, however this hasn't been confirmed yet for DS3, since we haven't gotten full unpacking done yet.

Data0 seems to be unused by the game? At the very least, I haven't found any info about it.
For Data1, Data2, Data3, Data4, and Data5:
The .BHD is encrypted using 2048bit RSA. Each of these files have their own keys, and the keys are encrypted and hardcoded into the .exe file.
Data1:

```
MIIBCwKCAQEA05hqyboW/qZaJ3GBIABFVt1X1aa0/sKINklvpkTRC+5Ytbxvp18L
M1gN6gjTgSJiPUgdlaMbptVa66MzvilEk60aHyVVEhtFWy+HzUZ3xRQm6r/2qsK3
8wXndgEU5JIT2jrBXZcZfYDCkUkjsGVkYqjBNKfp+c5jlnNwbieUihWTSEO+DA8n
aaCCzZD3e7rKhDQyLCkpdsGmuqBvl02Ou7QeehbPPno78mOYs2XkP6NGqbFFGQwa
swyyyXlQ23N15ZaFGRRR0xYjrX4LSe6OJ8Mx/Zkec0o7L28CgwCTmcD2wO8TEATE
AUbbV+1Su9uq2+wQxgnsAp+xzhn9og9hmwIEC35bSQ==
-----END RSA PUBLIC KEY-----
```

Data2:

```
MIIBCwKCAQEAvCZAK9UfPdk5JaTlG7n1r0LSVzIan3h0BSLaMXQHOwO7tTGpvtdX
m2ZLY9y8SVmOxWTQqRq14aVGLTKDyH87hPuKd47Y0E5K5erTqBbXW6AD4El1eir2
VJz/pwHt73FVziOlAnao1A5MsAylZ9B5QJyzHJQG+LxzMzmWScyeXlQLOKudfiIG
0qFw/xhRMLNAI+iypkzO5NKblYIySUV5Dx7649XdsZ5UIwJUhxONsKuGS+MbeTFB
mTMehtNj5EwPxGdT4CBPAWdeyPhpoHJHCbgrtnN9akwQmpwdBBxT/sTD16Adn9B+
TxuGDQQALed4S4KvM+fadx27pQz8pP9VLwIEL67iCQ==
-----END RSA PUBLIC KEY-----
```

Data3:

```
MIIBCwKCAQEAqLytWD20TSXPeAA1RGDwPW18nJwe2rBX+0HPtdzFmQc/KmQlWrP+
94k6KClK5f7m0xUHwT8+yFGLxPdRvUPyOhBEnRA6tkObVDSxij5y0Jh4h4ilAO73
I8VMcmscS71UKkck4444+eR4vVd+SPlzIu8VgqLefvEn/sX/pAevDp7w+gD0NgvO
e9U6iWEXKwTOPB97X+Y2uB03gSSognmV8h2dtUFJ4Ryn5jrpWmsuUbdvGp0CWBKH
CFruNXnfsG0hlf9LqbVmEzbFl/MhjBmbVjjtelorZsoLPK+OiPTHW5EcwwnPh1vH
FFGM7qRMc0yvHqJnniEWDsSz8Bvg+GxpgQIEC8XNVw==
-----END RSA PUBLIC KEY-----
```

Data4:

```
MIIBCwKCAQEArfUaZWjYAUaZ0q+5znpX55GeyepawCZ5NnsMjIW9CA3vrOgUGRkh
6aAU9frlafQ81LQMRgAznOnQGE7K3ChfySDpq6b47SKm4bWPqd7Ulh2DTxIgi6QP
qm4UUJL2dkLaCnuoya/pGMOOvhT1LD/0CKo/iKwfBcYf/OAnwSnxMRC3SNRugyvF
ylCet9DEdL5L8uBEa4sV4U288ZxZSZLg2tB10xy5SHAsm1VNP4Eqw5iJbqHEDKZW
n2LJP5t5wpEJvV2ACiA4U5fyjQLDzRwtCKzeK7yFkKiZI95JJhU/3DnVvssjIxku
gYZkS9D3k9m+tkNe0VVrd4mBEmqVxg+V9wIEL6Y6tw==
-----END RSA PUBLIC KEY-----
```

Data5:

```
MIIBCwKCAQEAvKTlU3nka4nQesRnYg1NWovCCTLhEBAnjmXwI69lFYfc4lvZsTrQ
E0Y25PtoP0ZddA3nzflJNz1rBwAkqfBRGTeeTCAyoNp/iel3EAkid/pKOt3JEkHx
rojRuWYSQ0EQawcBbzCfdLEjizmREepRKHIUSDWgu0HTmwSFHHeCFbpBA1h99L2X
izH5XFTOu0UIcUmBLsK6DYsIj5QGrWaxwwXcTJN/X+/syJ/TbQK9W/TCGaGiirGM
1u2wvZXSZ7uVM3CHwgNhAMiqLvqORygcDeNqxgq+dXDTxka43j7iPJWdHs8b25fy
aH3kbUxKlDGaEENNNyZQcQrgz8Q76jIE0QIEFUsz9w==
-----END RSA PUBLIC KEY-----
```


Once decrypted, the .BHD format is as follows:

```
//--- 010 Editor v3.1.2 Binary Template
//
// File: Dark Souls 3 .BHD (Archive Header)
// Author: Jed "Nyxojaele" Lang
// Revision: 1
//--------------------------------------
SetBackColor(cLtBlue);

typedef struct
{
    ulong StringLength;
    char String[StringLength] <bgcolor=0xffff55>;
} StringStruct <read=ReadStringStruct>;
string ReadStringStruct(StringStruct &ss)
{
    return ss.String;
}

typedef struct
{
    ulong Hash <format=hex, bgcolor=0xffff55>;
    ulong BdtSize <format=hex>;
    quad BdtOffset <format=hex>;
    quad SaltedHashOffset <format=hex, bgcolor=0x22aaff>;
    quad AesKeyOffset <format=hex, bgcolor=0x77aaff>;       //Sometimes 0 (no encryption), 0x10 bytes each
    quad DataSize <format=hex>;  //Sometimes 0 (is compressed)

    local ulong oldPos = FTell();
    if (SaltedHashOffset != 0)
    {
        FSeek(SaltedHashOffset);
        byte SaltedHash[1] <bgcolor=0x22aaff>;    //Not actual size, just marking first byte
    }
    if (AesKeyOffset != 0)
    {
        FSeek(AesKeyOffset);
        byte AesKey[0x10] <bgcolor=0x77aaff>;
    }
    FSeek(oldPos);
} EntryStruct <read=ReadEntryStruct>;
string ReadEntryStruct(EntryStruct &es)
{
    if (es.AesKeyOffset != 0)
    {
        if (es.DataSize == 0)
            return "Encrypted, Compressed";
        else
            return "Encrypted";
    }
    else
    {
        if (es.DataSize == 0)
            return "                   Compressed";
    }
    return "";
}

typedef struct
{
    ulong EntryCount;
    ulong EntriesOffset <format=hex>;
} BucketStruct <read=ReadBucketStruct>;
string ReadBucketStruct(BucketStruct &bs)
{
    string ret;
    SPrintf(ret, "%d Entries", bs.EntryCount);
    return ret;
}

byte Signature[4];
ulong Version;
ulong EndianCheck;
if (EndianCheck != 0x01)
    BigEndian();

ulong ArchiveSize;  //Doesn't match up perfectly? There may be padding at the end
ulong BucketCount;
ulong BucketsOffset <format=hex>;

StringStruct ArchiveName;

FSeek(BucketsOffset);
struct
{
    BucketStruct Bucket[BucketCount] <optimize=false>;
} Buckets;
struct
{
    local int i;
    for (i = 0; i < BucketCount; i++)
    {
        if (Buckets.Bucket[i].EntryCount > 0)
        {
            FSeek(Buckets.Bucket[i].EntriesOffset);
            EntryStruct Entry[Buckets.Bucket[i].EntryCount] <optimize=false>;
        }
    }
} Entries;

```


If an entry has an AESKeyOffset defined, it's data in the .BDT file is encrypted using that key. The size of the bytes that need decrypting is the entry's BdtSize. After decrypting, the data can be truncated to the entry's DataSize. (This is because the form of AES encrypting used requires data to be padded to a certain size)

If the entry has a 0 DataSize (whether encrypted or not), it's DCX compressed. Decryption must always happen before decompression. The DCX compression hasn't changed much since Dark Souls 1 -- it's basically a custom (Big-Endian!) header around a gzipped blob:

```
ulong Version;  //?
ulong DCXSize;
ulong DCXUnknown1[3];

byte DCSMagic[4];
ulong DCSUncompressedSize;
ulong DCSCompressedSize;

byte DCPMagic[4];
char DCPZlibCompSig[4];
ulong DCPSize;
ulong DCPLvl;
byte DCPUnknown1[12];
byte DCPFlags[4];

byte DCAMagic[4];
ulong DCASize;

byte[?] GZipBlob;

```


This GZipBlob is why some of you have had luck getting some files out of the archives, but it'll only work for compressed, non-encrypted, files.

As far as I know, this is pretty much everything anybody has figured out so far. Most of this I've put together myself, but I'd be lying if I said I did it all without some indirect help from Atvaark (author of BinderTool).

The current (rather large) issue that both my DS3Explore, and Atvaark's BinderTool exhibit is that while the encryption and compression data above is correct when used individually, any entry (this is most of them!) that is both encrypted AND compressed don't seem to work exactly as described above. Decryption seems to work fine (it generates a valid DCX header, all the way up until, and including, the 2 byte header for the GZipBlob). However, decompression fails with various internal errors. I believe the compressed data may be further encrypted, but I'm not 100% sure on this - I'm conducting further research into this at the moment.

Also worth noting is that there is no complete filename lookup dictionary available yet. This is going to be an ongoing process, as there's no simple way to just get all of the filenames.

Once these 2 issues are resolved, we'll have full unpacking of all of the main archives available, however internal archives (such as .BND, .TPF, .BHD/.BDT, etc..) may or may not work immediately. For all we know at this time, perhaps FROM Software has put further encryption on their internal file entries as well.
## Post #21
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-04-25T12:15:38+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Wow thanks for the hard work! Hopefully things go smoothly
## Post #22
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-04-25T18:49:06+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from nyxo
>
> As far as I know, this is pretty much everything anybody has figured out so far. Most of this I've put together myself, but I'd be lying if I said I did it all without some indirect help from Atvaark (author of BinderTool).

The current (rather large) issue that both my DS3Explore, and Atvaark's BinderTool exhibit is that while the encryption and compression data above is correct when used individually, any entry (this is most of them!) that is both encrypted AND compressed don't seem to work exactly as described above. Decryption seems to work fine (it generates a valid DCX header, all the way up until, and including, the 2 byte header for the GZipBlob). However, decompression fails with various internal errors. I believe the compressed data may be further encrypted, but I'm not 100% sure on this - I'm conducting further research into this at the moment.

Nice summary of the current situation. I can also share some of my findings you didn't write about yet.

1.
Data0.bdt is just a single .bnd.dcx file which contains the following .param files. [http://pastebin.com/raw/52Q2Mq2K](http://pastebin.com/raw/52Q2Mq2K)
Data0.bhd isn't even used by the game and the decryption key is probably not even included in it.

2.
The DataX.bhd files use the BHD5 format while the other .bhd files use the BHD4 format (which at least contains unicode filenames).

3.
010 Editor typedefs of the AES key and the SHA Hash structs look like this:

```
   byte hash[32];
   int type; // 1 or 3 
   int size;
   int unknown;
   int size;
   int unknown;

   if (type == 3) {
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
   }
} Bhd5ShaHash;

typedef struct {
   byte key[16];
   int type; // 1 or 3
   int size;
   int unknown;
   int size;
   int unknown;

   if (type == 3) {
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
     int size; // or -1
     int unknown;
   }
} Bhd5AesKey;

```


4.
If the file size of an entry is 0 (DCX files), then the game loads the first 48 byte to determine how much of the data has to be read.

5.
DCX encryption is a bit overkill. The data that is read from the DataX.bdt files is:
-Decrypted with the AES key found in the DataX.bhd file
-All the data after offset 78 is processed two times by some unknown algorithm that is related to zlib
-All the data after offset 80 is then decrypted with the AES key a second time
-The data after offset 78 can then be decompressed with zlib

See: [BinderTool Issue #3 Decrypting BDT5 files](https://github.com/Atvaark/BinderTool/issues/3)

6.
Besides exporting all the static file names I could find in the executable I haven't worked on recreating the file name dictionary.
The hash function looks like this, but I couldn't confirm it with some test cases yet.

```
        .ToLowerInvariant()
        .Aggregate(0, (i, c) => i * 137 + c)

```

See:
[BinderTool Issue #4 Rebuilding the dictionary](https://github.com/Atvaark/BinderTool/issues/4)
## Post #23
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2016-04-25T23:16:45+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Zoetropes
>
> Swennet wrote:So, has anyone been able to successfully extract and view any of the game's files yet? Personally, I'm most interested in the texture files, item images and sound files. Has anyone been able to extract these in a usable format yet?

It's easy to get stuff like this:

http://imgur.com/a/7Lac9

It's hard to actually do anything with it

I would also like to know how you were able to extract and open these files. Could you provide a step-by-step guide for us? Thank you!
## Post #24
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-04-27T18:57:49+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I just released the [BinderTool v0.4-pre1](https://github.com/Atvaark/BinderTool/releases) binaries. I haven't checked if all files are supported now, but it looks good so far.
What's missing is support for Data0.bdt and DS30000.sl2 and a working file name dictionary.
## Post #25
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2016-04-27T19:50:11+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Atvaark and I solved this last piece together via chat -- while he put together his new release, I confirmed that everything directly inside the main archives extracts without errors. Presumably that means the files are all correct, but we won't know 100% for sure until we start looking more directly at them.

For those curious, here is an updated section of the 010 Template with the pertinent information:

```
{
    quad OffsetStart;
    quad OffsetEnd;
} OffsetSetStruct <read=ReadOffsetSetStruct>;
string ReadOffsetSetStruct(OffsetSetStruct &oss)
{
    string ret;
    SPrintf(ret, "%X[%X]", oss.OffsetStart, oss.OffsetEnd-oss.OffsetStart);
    return ret;
}

typedef struct
{
    byte Hash[32] <format=hex, bgcolor=0x22aaff>;
    ulong OffsetSetCount <bgcolor=0xEEEEEE>;
    OffsetSetStruct HashOffsetSets[OffsetSetCount];
} SHAHashStruct;

typedef struct
{
    byte Key[16] <format=hex, bgcolor=0x77aaff>;
    ulong OffsetSetCount <bgcolor=0xEEEEEE>;
    OffsetSetStruct EncryptionOffsetSets[OffsetSetCount];
} AESKeyStruct;

typedef struct
{
    ulong Hash <format=hex, bgcolor=0xffff55>;
    ulong BdtSize <format=hex>;
    quad BdtOffset <format=hex>;
    quad SHAHashOffset <format=hex, bgcolor=0x22aaff>;   //Sometimes 0 (some, not all, unencrypted & uncompressed entries)
    quad AesKeyOffset <format=hex, bgcolor=0x77aaff>;       //Sometimes 0 (not encrypted)
    quad DataSize <format=hex>;                             //Sometimes 0 (DCX compressed)

    local ulong oldPos = FTell();
    if (SHAHashOffset != 0)
    {
        FSeek(SHAHashOffset);
        SHAHashStruct SHAHash;
    }
    if (AesKeyOffset != 0)
    {
        FSeek(AesKeyOffset);
        AESKeyStruct AESKey;
    }
    FSeek(oldPos);
} EntryStruct <read=ReadEntryStruct>;
string ReadEntryStruct(EntryStruct &es)
{
    if (es.AesKeyOffset != 0)
    {
        if (es.DataSize == 0)
            return "Encrypted, Compressed";
        else
            return "Encrypted";
    }
    else
    {
        if (es.DataSize == 0)
            return "                   Compressed";
    }
    return "";
}

```


I'm holding off on releasing my GUI-based archive tool until we've created a filename dictionary, but at that time, I'll release DS3Explore for those who are command line averse
## Post #26
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-28T02:00:29+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Just updating in what I found now that the files are a little more structured:
TPF texture files are, like previous Dark Souls games, DDS files with a TPF header. This time around, however, they use DX10 compression which is used for PBR shaders (previous games had DXT1 and DXT5). This makes the conversion process a bit harder, but it's a matter of opening the files in a Hex Editor -> deleting anything before the phrase "DDS |" -> saving the file and changing the extension to DDS -> open the file with Noesis and export it.
I'm working on a program to get around this, just have to analyze more textures so it can be batch done.

FLVER model files are still in effect, except they are read incorrectly with tons of mesh errors with the current plugins. I have no idea how to get around this at the time, but I ca at least make out what I'm looking at. Some of the files just plainly don't open with the Noesis plugin, too.



This is the model for the Reanimated Corpse from the Cathedral of the Deep graveyard, you can see the model is really screwed. The issue is pretty much the same thing I came across when working with Dark Souls 2: Scholar of the First Sin models, which I'm assuming is because SotFS and Dark Souls 3 are both 64bit and thus have 64bit modeling format / compression.

Update: I also can't seem to find any texture maps aside from the Albedo (diffuse). It may be BinderTool's dictionary isn't complete, or the other maps are hidden away somewhere in the jumbled folder structure.
## Post #27
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-28T05:48:07+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I can take a look at .flver and .tpf files if you'll send me a sample. It shouldn't be hard to edit current script for Dark Souls 2 or make Noesis plugin for textures

EDIT: As I though, format almost not changed from previous games, thanks a lot to HunterAP for sample.  So if anyone willing to upload pack of models (characters/monsters) and their .hkx files we will get models with bones and weights pretty soon. I hope lol
## Post #28
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-28T22:18:03+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I'm packing up all the characters and their HKX files now lol. I'll PM you with it in a few minutes, can't wait to get the models working.

EDIT: Sent the files over.
## Post #29
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-04-29T00:21:51+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Thanks for the hard work peoples! Cant wait!
## Post #30
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-04-29T06:47:30+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

sorry, but you can also get the original skeletons with skin models?
## Post #31
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-29T12:28:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Okay so I have tried using Noesis to access some of the models but just as HunterAP said, some of them aren't accessible and the models are super bugged...But how did you get all of the /chr files all together?
Also Zaramot i have noticed that you were able to access them from 3DSmax. Are you using a script?
## Post #32
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-29T12:36:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from BloatheadSorcerer
>
> Okay so I have tried using Noesis to access some of the models but just as HunterAP said, some of them aren't accessible and the models are super bugged...But how did you get all of the /chr files all together?
Also Zaramot i have noticed that you were able to access them from 3DSmax. Are you using a script?

As I explained, the Noesis plugins for DSI and DSII do not owkr on DSIII FLVER. I sent Zaramot many, many DSIII files o that he can write an importer/converter for those files.

As for how I got all the files, I made a batch script that used BinderTool to go through all the folders, first unpacking the BHD/BDT files, then the DCX files, then the BND files. From there I used a program (and another batch script) I made to convert all TPF files to DDS.
## Post #33
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-29T13:08:23+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from HunterAP
>
> BloatheadSorcerer wrote:Okay so I have tried using Noesis to access some of the models but just as HunterAP said, some of them aren't accessible and the models are super bugged...But how did you get all of the /chr files all together?
Also Zaramot i have noticed that you were able to access them from 3DSmax. Are you using a script?

As I explained, the Noesis plugins for DSI and DSII do not owkr on DSIII FLVER. I sent Zaramot many, many DSIII files o that he can write an importer/converter for those files.

As for how I got all the files, I made a batch script that used BinderTool to go through all the folders, first unpacking the BHD/BDT files, then the DCX files, then the BND files. From there I used a program (and another batch script) I made to convert all TPF files to DDS.

Oh this is a great improvement on what we had before! If you can implement the batch script you mentioned with the release of BinderTool itself and the dictionary, everything would work flawlessly!
## Post #34
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-29T17:37:07+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from dibe91
>
> sorry, but you can also get the original skeletons with skin models?

Well, yes I have bones and weights now. Though, there are some issues I'm trying to solve. I can provide "alpha" script for geometry right now. Maybe even with weights, but better I'll take a look more closer
## Post #35
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-04-29T18:31:36+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from zaramot
>
> dibe91 wrote:sorry, but you can also get the original skeletons with skin models?

Well, yes I have bones and weights now. Though, there are some issues I'm trying to solve. I can provide "alpha" script for geometry right now. Maybe even with weights, but better I'll take a look more closer

good. I hope we can sort it out as soon as possible!

P.S .: if you can even arrange demon souls do me a great favor ...
## Post #36
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-04-29T19:32:23+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from zaramot
>
> dibe91 wrote:sorry, but you can also get the original skeletons with skin models?

Well, yes I have bones and weights now. Though, there are some issues I'm trying to solve. I can provide "alpha" script for geometry right now. Maybe even with weights, but better I'll take a look more closer

If you can provide an alpha script it would be amazing. Also HunterAP, can you provide the batch script which you used to do the thing you said?
## Post #37
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-30T09:08:37+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from dibe91
>
> 
P.S .: if you can even arrange demon souls do me a great favor ...

Don't think I'm going to return to Demon's Souls, or Dark Souls I, model there are too outdated and in low quality, my most focus on DS 3 right now, and DS2 PC version but a bit less
## Post #38
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-05-01T18:18:13+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

[BinderTool v0.4](https://github.com/Atvaark/BinderTool/releases) is now available.
It now supports all the general DS III archive types, the regulation file and savegames.

Are there any scripts/tools that support splitting DS III tpf files?
## Post #39
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-01T20:18:29+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

-Never mind-

Got the release done early, [here's a link to the Github page](https://github.com/HunterAP23/TPF_To_DDS).
Please let me know if you run into any difficulties.
## Post #40
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-05-01T22:37:16+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from HunterAP
>
> -Never mind-

Got the release done early, here's a link to the Github page.
Please let me know if you run into any difficulties.
This doesn't handle tpf archives with multiple dds correctly and it doesn't even read the proper dds file names.

I've added tpf support to BinderTool since the format was pretty straightforward:
[https://github.com/Atvaark/BinderTool/c ... 9132fbe303](https://github.com/Atvaark/BinderTool/commit/4c7f23101687bcf8e5d2c71cf601389132fbe303)
## Post #41
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-05-02T00:13:33+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from HunterAP
>
> -Never mind-

Got the release done early, here's a link to the Github page.
Please let me know if you run into any difficulties.

I get a few errors when running this tool

ucrtbased.dll is missing
MSVCP140D.dll is missing
VCRUNTIME140D.dll is missing

Using windows 10
## Post #42
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-02T00:16:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Use Atvaark's BinderTool, it works better than my tool and even renames the files appropriately.
## Post #43
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-05-02T05:22:45+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from atvaark
>
> BinderTool v0.4 is now available.
It now supports all the general DS III archive types, the regulation file and savegames.

Are there any scripts/tools that support splitting DS III tpf files?

Mate, gonna also do rebuilder/repacker/packer please ? As far as i know it is not needed to encrypted files back, game should take also non-encrypted files, so it should be relatively easy to do it, of course if it is true..
## Post #44
- Username: rumpo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 19, 2015 2:04 am
- Post datetime: 2016-05-07T11:18:43+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Anyone had success converting sounds? I'm getting no headers with FSB extractor.
## Post #45
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-07T18:11:44+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

here are the models that you asked me Zaramot: [http://www.mediafire.com/download/88h32 ... 5w/chr.rar](http://www.mediafire.com/download/88h32za28n8565w/chr.rar)
## Post #46
- Username: Nodus Cursorius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 08, 2016 3:31 pm
- Post datetime: 2016-05-08T08:17:54+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from rumpo
>
> Anyone had success converting sounds? I'm getting no headers with FSB extractor.

FSB Extractor (many of them) will attempt to extract the unmodified .ogg file, which lacks a header due to using FMOD's library system to define things internally.

Luckily there's a way around that which essentially "records" the .ogg file into a PCM/WAV through sound emulation. The result is a playable .wav file with accuracy and multiple channel support.

You'll need both of these tools: [viewtopic.php?f=17&t=13615](http://forum.xentax.com/viewtopic.php?f=17&t=13615)

! NOTE: In order to use the tools, you will also need the library from [http://zenhax.com/viewtopic.php?t=1317&start=40#p7400](http://zenhax.com/viewtopic.php?t=1317&start=40#p7400) and the libraries from [viewtopic.php?p=112968#p112968](http://forum.xentax.com/viewtopic.php?p=112968#p112968)

Why two tools? Because fmod_extr.exe will handle the majority of the audio detection and extraction but seems to fail on multi-channel sounds. fsb_aud_extr.exe will handle those specific failure cases. Luckily for you (and others who find this post) I've done the hard work of identifying which files require which tool.

Batch file for the audio within Dark Souls III\Game\sound\ , which will also list the tool needed: [https://gist.github.com/NodusCursorius/ ... b51340aefd](https://gist.github.com/NodusCursorius/e356a7e48e1bd85028077bb51340aefd)

But wait, there's more!

Batch file for the audio within Dark Souls III\Data5.bdt\ , after you use Atvaark's BinderTool on \Data5.bdt: [https://gist.github.com/NodusCursorius/ ... c8dadf2ee0](https://gist.github.com/NodusCursorius/4d6156f8dcfb779205f074c8dadf2ee0)

Batch file for the audio within Dark Souls III\Data1.dbt\ , after you use Atvaark's BinderTool on \Data1.bdt: [https://gist.github.com/NodusCursorius/ ... cfdc207270](https://gist.github.com/NodusCursorius/59489aff96bf760e48d14ccfdc207270)

----

As a side note, to future Googlers, many of the .dds files that you extract with BinderTool (from the .tpf files) may appear as unreadable or undecodeable, depending upon your preferred image viewer. This seems to be due to how some of the images are not just in format DX1, 2, or 5, but some are using DX10 and DX11 format which is a completely different beast. Microsoft has a way to easily input these kinds of images and export them to a different format. Using their [DirectXTex](https://github.com/Microsoft/DirectXTex/) (DirectXTex texture processing library) converstion tool found here: [https://github.com/Microsoft/DirectXTex ... exconv.exe](https://github.com/Microsoft/DirectXTex/releases/download/apr2016/texconv.exe)

It's a command line executable, but iterating through everything is easy enough with this line, which will process all .dds in all sub-directories and create .png files alongside each .dds :

```
for /r . %T IN (*.DDS) do texconv.exe -ft PNG %T -o %~dpT
```

This fails on a small number of files but I lack the field knowledge to explain why. Ah well.

! NOTE: If you're batch scripting the above, don't forget to change %T to %%T in all three places Also, texconv does not work if your directory structure has spaces, even when quoted.

----

5/27/16 - Batch files and gist links updated to reflect improved ds3_Data5_sound_extract.bat (for newer names due to Atvaark's tool) and ds3_Data1_sound_extract.bat added for .. well, obvious reasons. Cheers, Sentuh, for leading me to check discrepancies with newly discovered names.
[ds3_sound_extract_batch.7z](https://xentaxbackup.github.io/file/10978_ds3_sound_extract_batch.7z)
## Post #47
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-08T10:20:20+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Hi. New here. Thanks for all this great info and tools! I'm into 3d-printing so having access to the models are great!

I don't know if this'll help someone but I made a script that'll use bindertool to extract all .bnd and .tpf and then use texconv to make .pngs. 
http://pastebin.com/Bibbczyi old script  http://pastebin.com/hcc4ecgQ

Just save that as a .vbs and use a command prompt to run cscript nameofscript.vbs

You'll need bindertool 0.4 and texconv and edit paths in the vbs before you save it, should be fairly straightforward.

Thanks

edit3: changed the script a bit- just point at one of the Data_.bdt files now and the script will unpack it and everything in it. 
You can then use windows explorer to search for "chr" and merge all those to one folder and you'll have all characters there.
## Post #48
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-05-10T20:22:11+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Martorias
>
> Hi. New here. Thanks for all this great info and tools! I'm into 3d-printing so having access to the models are great!

I don't know if this'll help someone but I made a script that'll use bindertool to extract all .bnd and .tpf and then use texconv to make .pngs. 
http://pastebin.com/Bibbczyi

Just save that as a .vbs and use a command prompt to run cscript nameofscript.vbs

You'll need bindertool and texconv and edit paths in the vbs before you save it, should be fairly straightforward.

Thanks

edit: It doesn't seem to work well when the path is the root game folder but if you do "DarkSoulsIII\Game\Data1" and then "DarkSoulsIII\Game\Data2" or so it seems to work.

edit2: wow amazing that the armor model for ornsteins helmet is the exact same as in dark souls 1.

Have you been able to get the firekeeper model yet?
## Post #49
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-11T18:52:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from pewposterous
>
> 
Have you been able to get the firekeeper model yet?

Yeah the chr/c1400? Textures seem a bit off but I think that's my fault.

[img.][http://i.imgur.com/7Tmr6v9.png](http://i.imgur.com/7Tmr6v9.png)[/img]
## Post #50
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-11T21:35:09+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

excuse you can make a list of the model numbers?
## Post #51
- Username: napoleonfd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 17, 2015 8:39 am
- Post datetime: 2016-05-11T23:20:37+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Hi everyone. First of all thanks for all this tools and information! I'm trying to translate the game, but I couldn't locate the text files myself. I found menu texts and some items in Data1 though (thanks to Atvaark for BinderTool), but fmg files have nulls between text and I don't know how to open them properly. And also I don't know how to repack edited files. I'm inexperienced in this kind of things so if anyone can help me it would be very appreciated.
## Post #52
- Username: drummer1249
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 04, 2015 9:20 am
- Post datetime: 2016-05-14T20:14:01+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

How are you viewing the meshes properly Martorias? Are you using a modified Noesis script to export the OBJ?
## Post #53
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-17T14:49:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from drummer1249
>
> How are you viewing the meshes properly Martorias? Are you using a modified Noesis script to export the OBJ?

Hi. I'm using Zaramots script for 3dsmax found in this thread: [viewtopic.php?f=16&t=14291&hilit=dark+souls](http://forum.xentax.com/viewtopic.php?f=16&t=14291&hilit=dark+souls)
## Post #54
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-18T14:18:07+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I'm trying to run Martorias' script but it doesn't seem to be working, if I leave \Data1 in I get a path not found on line 6, and if I remove it the script just doesn't seem to do anything. Anyone have some insight for me?

EDIT: that script aside, I am trying to view the Firekeeper, so c1400. I used BinderTools on the c1400.xxxbnd files, and I get the following:

C1400
>INTERROOT_win64
>>Action
>>>c1400
>>>>Export
>>>>>Behaviors
>>>>>>c1400.hkt
>>>>>>c1400.hkx
>>>>>Characters
>>>>>>c1400.hkt
>>>>>>c1400.hkx
>>chr
>>>c1400
>>>>hkx
>>>>>skeleton.hkx
>>>>tae
>>>>>c1400.tae

Where in there are the mesh and textures? Admittedly, I'm a newbie, but meshes are .flv and textures .tpf, correct?
## Post #55
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-18T15:30:13+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> I'm trying to run Martorias' script but it doesn't seem to be working, if I leave \Data1 in I get a path not found on line 6, and if I remove it the script just doesn't seem to do anything. Anyone have some insight for me?

EDIT: that script aside, I am trying to view the Firekeeper, so c1400. I used BinderTools on the c1400.xxxbnd files, and I get the following:

C1400
>INTERROOT_win64
>>Action
>>>c1400
>>>>Export
>>>>>Behaviors
>>>>>>c1400.hkt
>>>>>>c1400.hkx
>>>>>Characters
>>>>>>c1400.hkt
>>>>>>c1400.hkx
>>chr
>>>c1400
>>>>hkx
>>>>>skeleton.hkx
>>>>tae
>>>>>c1400.tae

Where in there are the mesh and textures? Admittedly, I'm a newbie, but meshes are .flv and textures .tpf, correct?

sorry I probably should mention you need to use bindertool on the main archive first to get the data2 folder for instance .
## Post #56
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-18T17:40:25+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Thanks, the script is running now, a ton of windows popped up, but it doesn't look like it's doing all that it's supposed to, it's stopping at the .xxxbnd level, and is just not unpacking those.

Also, I might just be dumb, but I don't know how get texconv to convert .tpf files into something I can read like dds or png.
## Post #57
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-18T19:00:37+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> Thanks, the script is running now, a ton of windows popped up, but it doesn't look like it's doing all that it's supposed to, it's stopping at the .xxxbnd level, and is just not unpacking those.

Also, I might just be dumb, but I don't know how get texconv to convert .tpf files into something I can read like dds or png.

Could you perhaps try now? I've updated the script ([http://pastebin.com/hcc4ecgQ](http://pastebin.com/hcc4ecgQ)) so just replace that and edit it. Point it to one file (Data3.bdt for instance) and it should unpack it all. When it's done (it'll take some time) use explorer to search for chr and merge all those folders to get all characters. Let me know if there's any issues.

edit: for the textures you need to use bindertool on the .tpf and then use texConv.exe -ft PNG inputfile.dds -o outputfolder
## Post #58
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-21T16:56:03+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Sorry for the delay, I tested it and it doesn't recognize LEFT (on line 3) as a valid argument.
## Post #59
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-22T06:02:41+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I have a question but it is possible to open the archives dark souls 2 files?I'm trying to open the archive of the models.
## Post #60
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-22T15:02:57+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from dibe91
>
> I have a question but it is possible to open the archives dark souls 2 files?I'm trying to open the archive of the models.
[https://github.com/Atvaark/BinderTool/tree/v0.3](https://github.com/Atvaark/BinderTool/tree/v0.3)
## Post #61
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-23T18:50:23+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> Sorry for the delay, I tested it and it doesn't recognize LEFT (on line 3) as a valid argument.

That's weird, that's like very basic code and it works fine here.. And you're starting it from a dos prompt with 
```
cscript scriptname.vbs
```
 and you're using this code [http://pastebin.com/hcc4ecgQ](http://pastebin.com/hcc4ecgQ) on a windows machine?
## Post #62
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-24T13:27:56+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Yes and yes :/
## Post #63
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-25T18:16:59+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> Yes and yes :/

Super weird. You could try replacing that code (since the left variable doesn't work for you? :S )

```
objStartFolder = LEFT(objStartFile, (LEN(objStartFile)-4))
```

to

```
objStartFolder = "D:\Games\DarkSoulsIII\Game\Data1"
```

since it's just a way to not having to write the path twice.
## Post #64
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-26T14:01:28+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Okay, now it seems to be working, but I made the mistake of running it directly instead of in the console and I'm getting a dialog box for every file it's unpacking >.<
## Post #65
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-05-30T18:09:17+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> Okay, now it seems to be working, but I made the mistake of running it directly instead of in the console and I'm getting a dialog box for every file it's unpacking >.<

It does spawn a whole lot of cmd boxes (one for each file, a lot!) but if you start it in a prompt you don't have to do anything, just sit back and wait  Let me know if it worked out
## Post #66
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-05-31T15:08:39+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Well, it seemed to be running for a while, but again it stops at the .xxxbnd level.
## Post #67
- Username: Martorias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 08, 2016 4:38 am
- Post datetime: 2016-06-02T16:31:08+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Emissaryofwind
>
> Well, it seemed to be running for a while, but again it stops at the .xxxbnd level.

Super weird. I'm not sure what's wrong then.. sorry  I could perhaps break it out to several small scripts to see what's wrong if you want?
## Post #68
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-06-02T18:47:40+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Martorias
>
> Emissaryofwind wrote:Well, it seemed to be running for a while, but again it stops at the .xxxbnd level.

Super weird. I'm not sure what's wrong then.. sorry  I could perhaps break it out to several small scripts to see what's wrong if you want?

If it's not too much of a bother.
## Post #69
- Username: 42tenthlick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 28, 2016 10:46 am
- Post datetime: 2016-06-08T19:32:40+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

So I've been spending a while trying to get Martorias' script to work on my machine, and I've gotten it close enough to work with Data4, which seems to have most of the models.  If you've been having problems with the .*bnd files or if your DS3 install folder has spaces in the path, then this will work for at least Data4.  

Here's my slightly modified version of Martorias' script [http://pastebin.com/gcf0XK9z](http://pastebin.com/gcf0XK9z)
 * If your install directory has spaces in the path (ex. Program files) then follow the new guides at the top of the script.  You will need to put the script in the DarksoulsIII/game folder.

 * If you had problems with the .bnd files, just set it up again.  (I've just added some Or statements to fix it because I don't know VBS   )

Also I've got some questions hopefully someone can answer.  Is there any documentation of where each model is located?  If not, I could set up a google doc and invite some people to start documenting it.  Secondly, is there any way to import models that don't have a skeleton?  I've been using Zaramot's 3DS importer, but I'm pretty sure it only works with models that have skeletons.

EDIT: [I've started my documentation.](https://docs.google.com/spreadsheets/d/1aqa9Q2xKLIiAuvvNLAEq1oZrwduTL7BpGOxMxAkodSQ/edit?usp=sharing) If anyone wants to help with this, shoot me a PM and I can add you.
## Post #70
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-06-08T19:57:04+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I'll try that new script tomorrow, the files are on my other computer.

> Reply from 42tenthlick
>
> Secondly, is there any way to import models that don't have a skeleton?  I've been using Zaramot's 3DS importer, but I'm pretty sure it only works with models that have skeletons.

I think he's working on it, but he needs more samples of objects without skeletons so you should hop over to [his topic](http://forum.xentax.com/viewtopic.php?f=16&t=14291&p=119291#p119291) and ask him.
## Post #71
- Username: Somalia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2016 11:05 pm
- Post datetime: 2016-06-09T19:31:42+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from 42tenthlick
>
> Secondly, is there any way to import models that don't have a skeleton?  I've been using Zaramot's 3DS importer, but I'm pretty sure it only works with models that have skeletons.
Yes, of course. It doesn't matter which DS3 Skeleton file you use.

Here, today I did some documentation of armor, weapons and shields:

[https://docs.google.com/document/d/1ttC ... sp=sharing](https://docs.google.com/document/d/1ttCdWmdto5DnSmdgNgGu5tzE2dzxE4LSn2PJU4SqZ4A/edit?usp=sharing)

(incomplete at the moment and some wrong or missing names but it's something I suppose)
## Post #72
- Username: longnguchicken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 14, 2016 7:44 pm
- Post datetime: 2016-06-14T11:50:58+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Sr but is there anyone here kind enough to give me the textures of Gotthard Twinswords, Warden Twinblades and Farron Greatsword? I want to their models for cinema 4D but giving the current situation, I think I should create the models myself
## Post #73
- Username: zaijie508
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 22, 2016 8:22 am
- Post datetime: 2016-06-22T01:39:20+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Martorias
>
> pewposterous wrote:
Have you been able to get the firekeeper model yet?

Yeah the chr/c1400? Textures seem a bit off but I think that's my fault.

[img.]http://i.imgur.com/7Tmr6v9.png[/img]

Could you share the firekeeper file with me, 3ds or obj would be prefered~Thanks a lot!
## Post #74
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2016-10-25T20:03:09+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I had to release a small update to support the DLC archives:
[https://github.com/Atvaark/BinderTool/releases](https://github.com/Atvaark/BinderTool/releases)
## Post #75
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2016-12-02T13:10:42+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

For extract to bdt bhd etc. everythings OK. And, what will we do with them? how do we these files transfer back to the game? you, what are you doing with these files, as not use them in game?

How to make repack, import, inject or mod pack to these files for see them in the game? Will put them to our ass? 


For instance, all of us are not english, french, or german. we want to translate our languages to this game and DS2 SOTFS. but we can't. because most of all guides or tools about texture, sound extraction, change hair-clothes-items... there is information about unpacking, for repacking or something provide transfer to the game there isn't, anything.

swuforce, made a tool for DS2, but not working to SOTFS or DS3.

Xentax, modders, coders... They are doing something for us. But just programmers using them, we are not using. We always find some open source codes, and sometimes find a tool but if it some of them works. If only in there publishing guides and tools for will be source to these projects.


Anyway... hey atvaark, please help us! these extracted files -especially .fmg files- how to edit and import or repack to the game?
## Post #76
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2016-12-16T11:27:18+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Please help to get an encryption key from the file for Data1.bhd Data1.bdt file

In fact it has already decoded the archive where the scattered key .bdt as AES ECB 128

And I do not need to extract the files from it I just need to decrypt it!

[](http://fastpic.ru/)

Or you can just packer
## Post #77
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2016-12-17T02:36:13+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Been trying to extract the files as mentioned but I cant seem to be able to produce a proper command line with Bindertool. Can anyone shed some light so I can at least extract these?

PS C:\Users\user\Desktop\BinderTool> ./BinderTool.exe Data2.bdt
                                                           ./BinderTool.exe C:\Users\user\Desktop\BinderTool\data2.bdt C:\Users\user\Desktop\BinderTool\extract

Unhandled Exception: System.ApplicationException: Missing decryption key for file 'data2.bhd'
   at BinderTool.Program.DecryptBhdFile(String filePath)
   at BinderTool.Program.UnpackBdtFile(Options options)
   at BinderTool.Program.Main(String[] args)

I cant seem to be able to decrypt the file. No idea where to find the command or the perm.

PS: Ok managed that!
## Post #78
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2017-03-27T21:08:28+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

New BinderTool release with the DLC2 decryption key:
[https://github.com/Atvaark/BinderTool/releases](https://github.com/Atvaark/BinderTool/releases)

I couldn't test it yet as the DLC will unlock tomorrow for me.

Edit:
The key works as expected.
## Post #79
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2017-03-28T14:29:08+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Does anyone know what happened with the .FSB files? They seem to have encrypted them somehow.
They used to start with FSB5 but now it is .èHâ
Does anyone know how to decrypt them?
## Post #80
- Username: Averuncus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 28, 2017 11:48 pm
- Post datetime: 2017-03-28T16:00:36+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from BloatheadSorcerer
>
> Does anyone know what happened with the .FSB files? They seem to have encrypted them somehow.
They used to start with FSB5 but now it is .èHâ
Does anyone know how to decrypt them?

For the fsb files in DARK SOULS III\Game\sound the encryption key is: FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg
You can use decfsb.exe to decrypt it: [http://hcs64.com/files/guessfsb03.zip](http://hcs64.com/files/guessfsb03.zip)

I extracted Data1.bdt (bindertool) to replace a soundfile but I have no idea on how to repack it. Can somebody help me?

Edit: In case repacking is currently not possible, is there a alternative?

Edit2: I found a alternative [https://www.reddit.com/r/DarkSoulsMods/ ... bdt_files/](https://www.reddit.com/r/DarkSoulsMods/comments/5adndh/dark_souls_3_load_files_outside_of_dataxbdt_files/) (Might cause a softban)
## Post #81
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2017-03-29T17:07:02+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Averuncus
>
> BloatheadSorcerer wrote:Does anyone know what happened with the .FSB files? They seem to have encrypted them somehow.
They used to start with FSB5 but now it is .èHâ
Does anyone know how to decrypt them?

For the fsb files in DARK SOULS III\Game\sound the encryption key is: FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg
You can use decfsb.exe to decrypt it: http://hcs64.com/files/guessfsb03.zip

I extracted Data1.bdt (bindertool) to replace a soundfile but I have no idea on how to repack it. Can somebody help me?

Edit: In case repacking is currently not possible, is there a alternative?

Edit2: I found a alternative https://www.reddit.com/r/DarkSoulsMods/ ... bdt_files/ (Might cause a softban)

I like that alternative method! However I can't seem to load custom string files in it (item_dlc1 and menu_dlc1, for example). Anyone had any luck with this?

EDIT: Okay, I've used Procmon to see what files the game tries to open, and it seems it's looking for said files, but with a .dcx format (like menu_dlc1.msgbnd.dcx), but Bindertool extracts the files as .msgbnd files (menu_dlc1.msgbnd).

Any ideas with this (or how can I make a .dcx format from my modified .msgbnd file)?
## Post #82
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-05-14T16:02:45+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Binder no work with Ringed City (DLC2). All other work fine.

EDIT: now work - just was a bug
## Post #83
- Username: Knight Artorias
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 19, 2017 6:19 am
- Post datetime: 2017-05-18T22:37:06+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Binder tool, Data1 Folder, Data1.bdt. how to repack back. please help.

I don't know how to repack edited .fmg files to .msgbnd

Sorry for the bad english

[http://share.pho.to/AhVx3](http://share.pho.to/AhVx3)

[http://www.hizliresimyukle.com/image/2JuWj](http://www.hizliresimyukle.com/image/2JuWj)
## Post #84
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2017-12-20T22:34:59+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Hi guys, I digged into the Data 3/chr folder and here are my findings for all characters I found there, yeah that means I checked all CHRBND files lol took me some time:
OBS: Some of them I didn't remember the proper name so I named whatever name & sorry for my non sense english because sometimes you will find something weird to read but I hope you get the basic idea.
If you wanna do a quick search the main tags: glitched, fixed, boss, pet, NPC
unknown c0000
unknown c0100
unknown c1000
mob unknown glitched c1070
mob transformed undead c1090
mob undead with crossbow c1100
mob undead with crossbow c1101
mob undead with crossbow c1102
mob undead with big axe c1105
mob undead with big axe c1106
mob slug c1130
mob with 2 swords c1170
mob with twin daggers c1180
mob steel knight c1190
mob tiny with wizard hat c1200
mob from swamp glitched c1210
mob from swamp c1211
unknown goop mob c1220
mob big fat witch c1230
mob with big fork c1240
unknown mob c1241
mob from pontiff's place c1250
mob big chains and cage c1260
mob knight c1280
mob knight c1281
mob knight c1282
mob fat armored flying c1290
mob black knight c1300
cool armor set i forgot the name c1310
wizard savage boss with ball c1320
wizard savage boss c1321
mob from grand archives c1340
unknown mob c1350
mob with cross c1360
mob with tree c1370
unknown mob with whip c1380
mob snake c1390
mob with chains and axe c1391
NPC Firekeeper c1400
mob silver knight c1410
mob pyromancer c1430
mob pyromancer c1440
mob pyromancer c1441
NPC wizard c1442
mob undead big axe c1445
mob wizard c1446
mob gnome NPC c1450
mob spinner skull c1470
cool armor set i dont remember the name c1480
dancer boss c1490
dog glitched c2020
dog glitched c2021
mob from pontiff's place c2030
unknown crazy dog glitched c2040
mob jelly goop c2060
unknown dog glitched c2070
dog glitched c2080
unscaled baby dragon boss c2090
unknown mob c2100
mob rat glitched c2110
mob mimic c2120
unknown pieces from some mob c2130
unknown pieces from some mob c2131
unknown pieces from some mob c2132
mob basilisk frog c2140
mob crystal lizard c2150
old witch NPC c2160
unknown NPC c2170
mob goop c2180
mob gargoyle fixed c2190
mob gargoyle glitched c2191
unknown glitched c2200
mob raven glitched c2210
mob witch with horseshoe fire c2230
valdrit dog boss c2240
unknown dragon glitched c2250
artillery crossbows c2260
mob big crag glitched c2270
mob big crag c2271
mob big rat c2280
dog glitched c2290
mob giant from cathedral with ball c3020
mob giant from cathedral c3021
the abyss watcher boss c3040
fire demon boss fixed c3050
fire demon boss c3060
mob from swamp i guess c3070
unknown c3071
ornstein's pet phoenix c3080
weird abyss watchers c3090
unknown mob too much glitched c3100
mob big spider c3110
mob from swamp c3120
dragon from prince's place c3140
dragon from prince's place c3141
ornstein boss c3160
mob darkwraith c3170
blacksmith c3190
old oracle with eyes band c3200
mob bug c3210
baby dragon c3220
fire fat dragon statue c3230
old oracle c3250
nameless boss c5010
nameless pet c5030
transformed undead c5110
yorn the giant boss glitched c5140
aldrich boss form anorlondo glitched c5150
big skull king boss c5160
big tree boss c5180
fire demon boss glitched c5200
princess c5210
pope boss c5220
mob fat pope fixed c5221
mob pope fixed c5222
mob pope fixed c5223
mob fat pope c5225
mob pope c5226
mob pope c5227
mob fire staff from pontiffs place c5240
prince boss c5250
yorn the giant boss c5260
mob from pontiffs place c5270

***I also have DS1 Data/chr name list for all characters, let me know if you want me to share that.***
## Post #85
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-01T10:20:35+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Hello people, i could extract all dark souls 1 & 3 sounds, but i got a bunch of wav files which would take a lot of time to check one by one, I'm looking for walk/running and hammer sounds, anyone could find it?
## Post #86
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-04T05:25:43+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

I found the walk/running/attacking/rolling most of the character main sounds from Dark Souls PTDE at dvdbnd1.bdt data in its sound folder there's a file named frpg_main.fsb. Just extract it using the fmod_extr.exe.

Now I need the Estus Flask model & its textures, anyone could find it?
## Post #87
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2018-01-14T15:49:58+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

[https://forum.donanimhaber.com/dark-sou ... -129097924](https://forum.donanimhaber.com/dark-souls-iii-the-fire-fades-edition-turkce-yama-yayimlandi--129097924)

[https://www.youtube.com/watch?v=XW-LNUL83HI](https://www.youtube.com/watch?v=XW-LNUL83HI)




As we are a group of game translation, released to new language pack. We managed to repack dds texts(80_language.tpf.dcx) and strings texts(msgbnd.dcx), so translated to Dark souls 3. Contact me if you are thinks that translate this game. But we do not thinks that free share the our tool, because we spend some money for make a translation tool.
## Post #88
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-02-27T14:54:49+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Hi, guys!
Have any updates for Elden ring?
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-03-06T14:25:16+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from TokiChan ↑Sun Feb 27, 2022 10:54 pm at Sun Feb 27, 2022 10:54 pm
>
> 
Hi, guys!
Have any updates for Elden ring?
[viewtopic.php?p=182655#p182655](https://forum.xentax.com/viewtopic.php?p=182655#p182655)
## Post #90
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T19:57:26+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

Does anyone know how to backtrack data find where the SOURCE of a ring would come from?
Trying to find Companion Jar and what rewards it through the data files, but a good way would see how they do it in other games like DS3

If it is a drop from a mob what data files would I be looking for for a drop loot table?
If it is a quest reward is there a data string that shows steps or quest reward for the item/source?
Is there a source data file and what extensions? Thanks!
## Post #91
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-03-10T11:25:59+00:00
- Post Title: Re: Dark Souls 3 *.bdt and *.bhd Files

> Reply from Warpavp2 ↑Thu Mar 10, 2022 3:57 am at Thu Mar 10, 2022 3:57 am
>
> 
Does anyone know how to backtrack data find where the SOURCE of a ring would come from?
regulation.bin contains binary data tables.
