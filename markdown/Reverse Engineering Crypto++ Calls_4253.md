## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-03-23T23:32:06+00:00
- Post Title: Reverse Engineering Crypto++ Calls

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-16T15:53:43+00:00
- Post Title: Reverse Engineering Crypto++ Calls

sincerely all this thing doesn't have a sense maybe because I don't understand it.
anyway all the calls to aes setkey seem to have a key made of 32 zeroes.
the rest is that sort of obfuscation I showed you via pm
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-16T17:12:46+00:00
- Post Title: Reverse Engineering Crypto++ Calls

the result is totally unrecognizable.
im expecting a zlib compression on the xml format, not the obfuscation from the zip container

---

wish i had some idea how to continue. here are some thoughts.

using [http://www.cryptopp.com/docs/ref/cryptl ... ource.html](http://www.cryptopp.com/docs/ref/cryptlib_8cpp-source.html)

Algorithm::Algorithm(bool checkSelfTestStatus) is called way too many times
FilterWithBufferedInput::FilterWithBufferedInput ?
StringStore::StoreInitialize?

the 32-byte signature is used as some sort of key (with the 5 null padding bytes, its a valid aes key, but no hope atm)

was missing a header value in my first post. clearly:

char signature[32]
int32 usize
int32 other

total of 40 byte header. some references to other, but no idea what it could be.

breakpointing on functions made before i see the dump is finally visible in memory.
i can do this as files are dumped into a memory space i can predict.

data isn't there until this is called

00542A9C  |> 50             PUSH EAX                                 ; /Arg3 = 02C84680
00542A9D  |. 6A 01          PUSH 1                                   ; |Arg2 = 00000001
00542A9F  |. 8D55 B4        LEA EDX,DWORD PTR SS:[EBP-4C]            ; |
00542AA2  |. 52             PUSH EDX                                 ; |Arg1
00542AA3  |. 8D8D ACFDFFFF  LEA ECX,DWORD PTR SS:[EBP-254]           ; |
00542AA9  |. C645 FC 0A     MOV BYTE PTR SS:[EBP-4],0A               ; |
00542AAD  |. E8 2EFCFFFF    CALL 005426E0                   ; \005426E0

there are some huge switch statements.

first function accessing the dumped memory location is at 00609070
some references to "Inflator"

size_t Inflator::Put2(const byte *inString, size_t length, int messageEnd, bool blocking) ????

looks like i've missed the aes part and skipped to the unzipping


total dead end. help!
