## Post #1
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-03-22T12:58:49+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

Hello, I am writing here in order to ask for help regarding an encrypted text format for later versions of the mobile game Cookie Run (and because the game has a very messy history with multiple versions to boot, the specific versions it was introduced in include 4.22 for Kakao, 2.0 for LINE, and 1.0.2 for QQ), the .djb text files.

Back in November of last year, I posted about having the .dxj files ( [viewtopic.php?f=21&t=24779](https://forum.xentax.com/viewtopic.php?f=21&t=24779) ), which essentially served as the predecessor to the .djb format. After some digging and help from the Discord server, it was discovered that the encryption used for the .dxj files was Xor using the password "dev!Wkwkdwhgdk!sisters@#$" under Base64. I'm thankful that it was able to be reverse engineered that way.

However, the format was later changed, and as of now has not been cracked (some users have found that editing the libgame.so file occasionally works for modding, but having full control over the text files would break open a much wider door) for almost 8 years since it's inception. However, I have found multiple leads over the past few months and I believe that we may have enough leads to possibly have a breakthrough. I'll link all of the resources I've found at the end of this for investigation.

If you look at a raw .djb file in a text editor like Notepad, the header starts with "DJBF". We'll get into that later.

As stated previously, April 2014 saw the introduction of the .djb format, replacing the .dxj format that a Tistory blog had documented how to decrypt openly. Despite some workarounds by the fandom, the full text, and therefore full control over the game has not been broken. However, I and a friend of mine have found multiple oddities within the numerous versions and revisions of the game that just don't check out.

My friend, whom I will be refering to as Seanoo from here on out, uploaded every version of Cookie Run for Kakao for Android to archive.org, where some observations, such as when .dxj files were phased out. However, when we started to look for versions of the elusive Tencent QQ localization of Cookie Run, things got weird.

The Tencent QQ versions of the game are quite mysterious and even a little sloppy in some ways, some rather interesting pieces of info are left in. In the 1.0.2 .apk of the game, it can be discovered that it simultaneously uses both .dxj and .djb formats, which no other vserion of the game does. However, the next version, 2.0, would prove to be very interesting. In the assets/egame folder is a .jar file, which made us suspicious that the game may have used Java in a way. We tried to unzip the file, though to no avail. If one takes a look in the assets/kakaoBC_BalanceData folder (yes, we're still talking about the Chinese version of the game), it can be noticed that several of the .djb files have accompanying .bin files with partially encoded text.

An additional discovery by Seanoo was that of a Tistory blog that details a script for Javadoc on how to encode a string or file through Java's encryption ( [https://cofs.tistory.com/334](https://cofs.tistory.com/334) ) and then through Base64, and came up with the theory that ".djb" and by extension "DJBF" stands for JavaDoc Java Binary. However, this could also be a red herring.

I unfortunately do not have any more leads to share, but I am linking all of the resources that I have found for investigation.

All Cookie Run for Kakao .apks (Version 4.22 (65) is the first version to use .djb encryption): [https://archive.org/download/cookierun-for-kakao-apk](https://archive.org/download/cookierun-for-kakao-apk)

Cookie Run for QQ 1.0.2 (plus some LINE versions): [https://drive.google.com/drive/folders/ ... 8cUD63bdPd](https://drive.google.com/drive/folders/1b91kvZsy-H63IyY9Rba3ov8cUD63bdPd)

Cookie Run for QQ 2.0: [https://drive.google.com/file/d/1rYdcGq ... sp=sharing](https://drive.google.com/file/d/1rYdcGqvM4yl1mpAzgplsUvmu1CU3iJ_v/view?usp=sharing)

Thank you for reading and I promise that any help given will be given my gratitude. *bow*
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-27T20:47:17+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

Not sure if this is still required but I've documented the structure and encryption + compression used by this format.

The structure below is based on 4.22 (65) and 9.22 (217) versions of the game. Depending on the version of the file, the data will be either AES-256 ECB or AES-256 CBC encrypted and/or [FastLZ](https://github.com/ariya/FastLZ) compressed. The Key and base IV are documented below too and appear to have stayed the same since 4.22 (65). For each file the IV is [salted](https://gist.github.com/barncastle/3c96cec175bb65c2381a7887272614b9#file-cookierundjbf-cs-L124) with the first byte of the checksum.

```
{
   uint Magic;     // "DJBF"
   ushort Version; // big endian
   ushort Reserved;
   uint Checksum;  // CRC32
   int DataSizeLo; // once decompressed
   int DataSizeHi;
   Flags Flags;
   byte DataSuffix[0xF];
   byte DataSuffixSize;
   byte Data[x];   // to EOF
}

enum Flags : byte
{
   AES_ECB = 0x1,
   AES_CBC = 0x2, // ≥ version 0x0102
   FastLZ = 0x80, // ≥ version 0x0101
}

byte[] Key = new byte[]
{
   0xC0, 0x01, 0xC1, 0xE1, 0x26, 0x11, 0x10, 0xDA, 
   0x90, 0x90, 0x35, 0x81, 0xFE, 0xBA, 0xA9, 0x7F, 
   0xA1, 0x45, 0x1C, 0x4F, 0x97, 0x88, 0x71, 0xFA, 
   0xC3, 0xF1, 0xF8, 0x29, 0x3D, 0xDE, 0xE2, 0xB3
}

byte[] IV = new byte[]
{
   0x58, 0xA8, 0xB9, 0xDD, 0x13, 0x61, 0x62, 0xAA,
   0x99, 0x88, 0x7A, 0x1F, 0xF2, 0x3F, 0x7C, 0x91
}

```


One quirk of the format is that the data is intentionally split between the Data and DataSuffix fields. AES requires 128-bit aligned blocks and Data is (almost) always misaligned. The game concatenates Data and the first DataSuffixSize bytes of DataSuffix before decrypting. Do note that version 0x0100 Data CAN be aligned, but when this occurs DataSuffixSize will have an invalid value (> 0xF) so is easily detected.

A few things to note:
 - The game does support unencrypted and uncompressed DJB files. If the Flags and DataSuffixSize fields are zeroed then the game will simply read  the Data as is which makes modding pretty trivial.
 - 9.22 (217) supports reading all DJB versions.
 - The files switched format at some point from JSON strings to a binary format.
 - Flags are not explicit e.g. version 0x0100 will use a value 0xFF despite only supporting 0x1. Because of this the game checks both version and Flags to ensure it loads old files correctly.

I've written C# code and compiled it into a tool which is available [here](https://gist.github.com/barncastle/3c96cec175bb65c2381a7887272614b9). I've attempted to make this cross-version compatible and have tested it against all files in versions 4.22 (65) and 9.22 (217) but there may be issues with certain other versions.
## Post #3
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-07-09T02:51:20+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

Wow, I'm sorry I'm late, I forgot my account password. This is monumental! I'm very thankful for your help. Decrypting the files will be helpful, but is it possible to create a script or program to re-encode text so the game can read it? Thank you for any and all help!
## Post #4
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-07-09T12:11:57+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

I've noticed that whenever I try to decrypt any .djb files from the QQ (Chinese) versions of the game, the program says an exception has occured. I'm under the impression that it uses another format of encryption.
## Post #5
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-13T13:53:27+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

> Reply from ProbPeriPlum ↑Sat Jul 09, 2022 10:51 am at Sat Jul 09, 2022 10:51 am
>
> 
is it possible to create a script or program to re-encode text so the game can read it?

There should be enough information documented here for someone to fully reverse the decryption process but as I said you might not need to. The game should happily load unencrypted + uncompressed Data as-is provided the Flags and DataSuffixSize fields are both are set to 0 - albeit with the correct DataSizeLo and Checksum values set. Using the below as a template, append the unencrypted data to the end and update the red + green coloured bytes.

[](https://ibb.co/5n3Nx5X)

> Reply from ProbPeriPlum ↑Sat Jul 09, 2022 8:11 pm at Sat Jul 09, 2022 8:11 pm
>
> 
I've noticed that whenever I try to decrypt any .djb files from the QQ (Chinese) versions of the game, the program says an exception has occured. I'm under the impression that it uses another format of encryption.

QQ 2.0 uses a different encryption Key and IV - I've not checked the others.

```
{
    0xC0, 0x29, 0xC1, 0xE1, 0x26, 0x88, 0x71, 0xFA,
    0xA1, 0x45, 0x1C, 0x4F, 0x97, 0xDE, 0xD2, 0xB3,
    0x90, 0x94, 0x35, 0x81, 0xFE, 0xBA, 0xA9, 0x7F,
    0xC3, 0xF1, 0xF8, 0x29, 0x3D, 0x11, 0x10, 0xFA,
};

byte[] IV = new byte[]
{
    0x13, 0x61, 0x62, 0xAA, 0x38, 0xA8, 0xB9, 0xDD,
    0x99, 0x6F, 0xF2, 0x3F, 0x7C, 0x91, 0x88, 0x7A
};

```
## Post #6
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-07-14T03:12:03+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

Forgive my ineptitude and general tomfoolery, but regarding readding the DJBF header to a .djb file, I've tried copying the "DJBF" alongside the blank bits (00000000) and I've added them both to the start and end of a decrypted .djb gile and the game rejects them. For reference, I am specifically using version 4.41 of Kakao for Android and the hex editor of choice for me is HxD 2.5.0.0 (x86-64) for Windows. You mentioned that you had a template for a header, is it possible to publish it to GitHub so it would otherwise be easier to insert? If I made amy mistakes (which of I probably made several), please let me know. You are a very helpful and kind person and I'd like to let you know that I'm not the only person here who apprecoates this.
## Post #7
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-07-14T12:58:35+00:00
- Post Title: Cookie Run Encrypted Text File (.djb)

Okay, with the help of a friend, I was able to figure out the text passage to copy as a header, but the game is tripped and the anti-cheat is activated, which is moreso an issue with the game itself than the text. [https://media.discordapp.net/attachment ... 085401.png](https://media.discordapp.net/attachments/933916544046620713/997123873919221760/Screenshot_20220714-085401.png) (And yes, I was trying to play the game via Guest Mode as it's the only way to do it offline.

Perhaps after all we'll probably need to engineer a re-encoder, or something with the game itself. I'm not entirely sure if that is within your expertise, but if you are still willing to help out and troubleshoot, please let me know.
