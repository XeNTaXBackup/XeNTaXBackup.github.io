## Post #1
- Username: CaseyVGCx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 03, 2016 6:30 am
- Post datetime: 2016-04-03T00:04:54+00:00
- Post Title: Soul Worker OBT String Files (.res file)

Hello,

I'm currently trying to localize Soul Worker Online (F2P game) into English. I've gone so far as extracting the .v archives and obtaining the files that contains the strings to translate the game. I have uploaded a zip containing the string files.
I tried opening the .res file into Visual Studio, but I could not find the right encoding to edit the file in. 


[http://sharex.closershq.com/casey/Table.zip](http://sharex.closershq.com/casey/Table.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-03T00:25:16+00:00
- Post Title: Soul Worker OBT String Files (.res file)

> Reply from CaseyVGCx
>
> Hello,

I'm currently trying to localize Soul Worker Online (F2P game) into English. I've gone so far as extracting the .v archives and obtaining the files that contains the strings to translate the game. I have uploaded a zip containing the string files.
I tried opening the .res file into Visual Studio, but I could not find the right encoding to edit the file in. 


http://sharex.closershq.com/casey/Table.zip

been waiting for this game for years. could you upload the client please?
## Post #3
- Username: CaseyVGCx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 03, 2016 6:30 am
- Post datetime: 2016-04-03T00:47:51+00:00
- Post Title: Soul Worker OBT String Files (.res file)

The whole client is here. 
[https://drive.google.com/open?id=0B38PE ... nVTeTBfS2M](https://drive.google.com/open?id=0B38PE3kF9QHnNHo1anVTeTBfS2M)

If you prefer install / downloading the whole client from the official site, then here is that link.
[http://bit.ly/1qodrLR](http://bit.ly/1qodrLR)
## Post #4
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-03T11:01:34+00:00
- Post Title: Soul Worker OBT String Files (.res file)

Hello, i am trying to translate this game but i'm kind of stuck to the archive format of the data files, i'm pretty new to this

i'll try to explain what i got until now
someone brought me(we are more in the "mini-team") XOR extractor and we used that to unpack the files from *.v files but we got stuck at trying to find the archive format of the .res files
i think some of them have a different format from other ones

only worked around tb_Skill_Script.res
first 6 bytes are nothing?
then comes one long with the size of the string that follows
another 38 bytes of nothing?
then keeps repeating, one long(size) then japanese text string
after all data comes 22 bytes of nothing?
last 32 bytes might be an MD5 checksum, i used a website to "crack" the checksum and it got me a decimal, in no way i was able to find out how they calculate it

the problem is if i change something in the translation the game won't load the file but if i just swap bytes or insert bytes but then reduce the bytes from another place to keep the file intact the game loads
here is the whole data folder that we can't find the format to: [https://drive.google.com/file/d/0B1oLkd ... sp=sharing](https://drive.google.com/file/d/0B1oLkdHPWXFtVHdPNTB3dU1tbms/view?usp=sharing)

also there is someone who does many translations for games and also did one for Soul Worker Online, but all of them are with google/bing translate and it's really, really bad. we tried to ask him to help us but he asks us for 250$...
if the files he translated help, here they are: [https://drive.google.com/file/d/0B1oLkd ... sp=sharing](https://drive.google.com/file/d/0B1oLkdHPWXFtbDcyQkZYY0F1MWs/view?usp=sharing)

also if it's possible to know or explain how the *.v files were extracted? we used those files: [https://drive.google.com/file/d/0B1oLkd ... sp=sharing](https://drive.google.com/file/d/0B1oLkdHPWXFteU01eWNTdkZnaTA/view?usp=sharing)

Thank you very much for your time! i hope someone can help us
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-03T15:06:44+00:00
- Post Title: Soul Worker OBT String Files (.res file)

Dupe of [viewtopic.php?f=10&t=14177](http://forum.xentax.com/viewtopic.php?f=10&t=14177)

aaadn

> also there is someone who does many translations for games and also did one for Soul Worker Online, but all of them are with google/bing translate and it's really, really bad.

LOL
## Post #6
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-03T15:10:55+00:00
- Post Title: Soul Worker OBT String Files (.res file)

> Reply from WRS
>
> Dupe of viewtopic.php?f=10&t=14177

aaadn
also there is someone who does many translations for games and also did one for Soul Worker Online, but all of them are with google/bing translate and it's really, really bad.


LOL

not really a dup
my question is entirely different, i want at least a hint on how the check sum at the end is calculated or if it's a check sum or not
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-03T15:21:32+00:00
- Post Title: Soul Worker OBT String Files (.res file)

covers the same bases.

anyway, i think its a content hash as some files share the same contents and hash: 

tb_MazeReward_PartyValue.res
tb_MazeReward_Difficulty.res

still looking


edit 1

> Reply from Miyu
>
> also if it's possible to know or explain how the *.v files were extracted?

those .v files are just xor'ed by the value 0x55 - which are just zip files.

note: you need a decent zip extractor to get the language files, as the root folder name ".." does not show up on windows machines 


edit 2

its an md5 hash of a string value which i'm still investigating:

```
unknown value: 4669786877
md5("4669786877") == 37BA4A9FFBFE982FD83265FDB4A70CB8


tb_Achievement_begin
unknown value: 244201444
md5("244201444") == 3D3BE6A70FBDC4D6648A808844B57C45

```


note: you can easily patch the game to ignore invalid hash files:

```
01286EA2  |. 0F84 CA000000  JE SoulWork.01286F72

change to :

01286E9B     E9 D2000000    JMP SoulWork.01286F72
01286EA0     90             NOP
01286EA1     90             NOP

```
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-03T17:12:01+00:00
- Post Title: Soul Worker OBT String Files (.res file)

also, unfortunately each .res file has its own hardcoded parse routine.......

the generic template looks like this:

```
[.. data ..]
short hash_len; // should be 32
char hash[hash_len]; // md5 hash of the sum of the file contents (see below)

```


the achievements data is FIXED, and read like this:

```
{
  uint id;
  ubyte b1;
  ushort s1;
  ubyte b2;
  ushort s2;

  ushort len; wchar_t name[len];

  ushort s3;
  int i1;
  int i2;
  int i3;
  int i4;
  int i5;
  int i6;
  int i7;
  int i8;
  byte b3;
  byte b4;
  int i9;
  int i10;
  byte b5;
  byte b6;
};

// there are *count* numbers of archivements

```


for anyone following along, just label these functions:

```
012642A0 read_byte
01264320 read_short
0125E0C0 read_wstring_with_size

```


specific formats can then be ripped, although thats a real pain  


end

the checksum at the end is just the sum of each data member, converted to string, then md5 hashed.

i've written an example here: [https://gist.github.com/x1nixmzeng/3c13 ... 33254cbe34](https://gist.github.com/x1nixmzeng/3c1346d6abb5729598505533254cbe34)

which validates the achivement file:

> Parse total: 4669786877
>
> Expected hash: 37ba4a9ffbfe982fd83265fdb4a70cb8
>
> Read hash: 37ba4a9ffbfe982fd83265fdb4a70cb8
>
> -- SUCCESS--

remember that there is no "auto" serialization. the formats are fixed in the game executable.
## Post #9
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-03T19:44:40+00:00
- Post Title: Soul Worker OBT String Files (.res file)

thank you very much for the help!
i won't let your efforts go to waste
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-03T20:32:53+00:00
- Post Title: Soul Worker OBT String Files (.res file)

> Reply from Miyu
>
> thank you very much for the help!
i won't let your efforts go to waste
 

i've just extracted every single resource structure which saves manually extracting it all -->

[https://gist.github.com/x1nixmzeng/a4a5 ... tructs-txt](https://gist.github.com/x1nixmzeng/a4a5c419f1cd4bc72cba30d5e647bc4f#file-structs-txt)
## Post #11
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-03T21:04:54+00:00
- Post Title: Soul Worker OBT String Files (.res file)

> Reply from WRS
>
> Miyu wrote:thank you very much for the help!
i won't let your efforts go to waste
 

i've just extracted every single resource structure which saves manually extracting it all -->

https://gist.github.com/x1nixmzeng/a4a5 ... tructs-txt

wow, you did the formats for all of them, you're a god
but i don't really understand how to use it... i didn't use python before

i don't know why we need the the assembly offsets of... SoulWorker100.exe? i think
i'll use the file formats that you got and i'll try to make an extractor and a repacker
that way it will be easy to translate for our team

thank you so much for your help!
## Post #12
- Username: Chaiyapos72
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2016 9:32 am
- Post datetime: 2016-04-04T06:03:28+00:00
- Post Title: Soul Worker OBT String Files (.res file)

Oh , I can't use python
but thank you very much
## Post #13
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-04T12:11:01+00:00
- Post Title: Soul Worker OBT String Files (.res file)

for some reason for tb_Achievement_Script the MD5 is different, i used the structs you gave us
and i get

```
Expected hash: b6d99e9223245c7426d0c0d85aa2d15c
Read hash: 6d6d2e43af9fe67ae81a771f71a917ab
*ERROR Line 61: Assertion Failed: 
```


but running it on the translated(by Formica) tb_Achievement_Script it generates the same MD5

```
Expected hash: b0cb1cabe6a76d27d35dd26646352583
Read hash: b0cb1cabe6a76d27d35dd26646352583
-- SUCCESS--
```


both of the file are accepted by the game
if i try to replace on the original the MD5 that is expected to be with the one in there(not changing anything else) it fails to load
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-04T21:02:41+00:00
- Post Title: Soul Worker OBT String Files (.res file)

> Reply from Miyu
>
> for some reason for tb_Achievement_Script the MD5 is different, i used the structs you gave us
and i get
Code: Select allParse total: 1857985864
Expected hash: b6d99e9223245c7426d0c0d85aa2d15c
Read hash: 6d6d2e43af9fe67ae81a771f71a917ab
*ERROR Line 61: Assertion Failed:

ah sorry, that checksum is slightly wrong. wchar_t is actually hashed per-byte, not per character.

interestingly it worked on tb_achievement because it didn't use japanese text   

here is an update:

```
struct tb_Achievement_Script
{
	uint i1; read_sum += i1;
	ushort len1; read_sum += len1;

    ubyte str1[len1*2];
    for(j=0;j<len1*2;++j) read_sum += str1[j];

	ushort len2; read_sum += len2;

	ubyte str2[len2*2];
    for(j=0;j<len2*2;++j) read_sum += str2[j];
};

typedef tb_Achievement_Script Achievement;


```


which is correct

> Parse total: 1694900869
>
> Expected hash: 6d6d2e43af9fe67ae81a771f71a917ab
>
> Read hash: 6d6d2e43af9fe67ae81a771f71a917ab
>
> -- SUCCESS--
edit

just change the struct dumper to use ubyte[] instead of wchar_t[] if that helps

[https://gist.github.com/x1nixmzeng/a4a5 ... tructs-txt](https://gist.github.com/x1nixmzeng/a4a5c419f1cd4bc72cba30d5e647bc4f#file-structs-txt)
## Post #15
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2016-04-04T22:05:29+00:00
- Post Title: Soul Worker OBT String Files (.res file)

OH
that makes sense
thank you very much once again!
## Post #16
- Username: Nonstop
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 23, 2016 5:52 am
- Post datetime: 2017-02-07T05:08:49+00:00
- Post Title: Re: Soul Worker OBT String Files (.res file)

> Reply from WRS
>
> Miyu wrote:thank you very much for the help!
i won't let your efforts go to waste
 

i've just extracted every single resource structure which saves manually extracting it all -->

https://gist.github.com/x1nixmzeng/a4a5 ... tructs-txt

I noticed the structure seems to be missing something for certain files? Haven't made it through all the files yet but one that doesn't seem to work is tb_Skill.res. Even trying the file used when you made the script it seemed to fail.

So it seems like there was another call for those files and I just labeled it read_int2 and added that. No clue if it is correct or not but it was at the very least able to parse all the way through the files.
[ollydbg.png](https://xentaxbackup.github.io/file/12417_ollydbg.png)
## Post #17
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-02-09T21:54:05+00:00
- Post Title: Re: Soul Worker OBT String Files (.res file)

> Reply from Nonstop
>
> 
I noticed the structure seems to be missing something for certain files? Haven't made it through all the files yet but one that doesn't seem to work is tb_Skill.res. Even trying the file used when you made the script it seemed to fail.

So it seems like there was another call for those files and I just labeled it read_int2 and added that. No clue if it is correct or not but it was at 
the very least able to parse all the way through the files.
edit

just checked the latest exe, the addresses have changed which you need to label:

```
Label    Address                                 Disassembly                               Comment
<read_tb> 001370E0                               PUSH EBP
<read_wstring_and_len> 00137450                  PUSH EBP
<read_byte> 0013C9D0                             PUSH EBP
<read_short> 0013CA50                            PUSH EBP
<read_int> 0013CAD0                              PUSH EBP
<read and verify checksum> 00159B80              PUSH EBP
         001607DE                                PUSH EAX                                  (Initial CPU selection)

```


there are a few changes since i wrote this 

> struct tb_Skill
>
> {
>
> 	uint i1;
>
> 	ushort s1;
>
> 	uint i2;
>
> 	uint i3;
>
> 	ubyte b1;
>
> 	ubyte b2;
>
> 	ubyte b3;
>
> 	ubyte b4;
>
> 	ubyte b5;
>
> 	ubyte b6;
>
> 	ubyte b7;
>
> 	uint i4;
>
> 	uint i5;
>
> 	uint i6;
>
> 	uint i7;
>
> 	ubyte b8;
>
> 	ubyte b9;
>
> 	ubyte b10;
>
> 	ubyte b11;
>
> 	ushort s2;
>
> 	ubyte b12;
>
> 	ushort s3;
>
> 	ubyte b13;
>
> 	ubyte b14;
>
> 	ubyte b15;
>
> 	uint i8;
>
> 	ubyte b16;
>
> 	ubyte b17;
>
> 	ubyte b18;
>
> 	ubyte b19;
>
> 	ubyte b20;
>
> 	uint i9;
>
> 	uint i10;
>
> 	uint i11;
>
> 	uint i12;
>
> 	uint i13;
>
> 	uint i14;
>
> 	uint i15;
>
> 	ubyte b21;
>
> 	ushort s4;
>
> 	ushort s5;
>
> 	ubyte b22;
>
> 	ubyte b23;
>
> 	ubyte b24;
>
> 	ubyte b25;
>
> 	ubyte b26;
>
> 	uint i16;
>
> 	uint i17;
>
> 	uint i18;
>
> 	ubyte b27;
>
> 	ushort s6;
>
> 	ushort len1;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str1[len1*2];
>
> 	ushort s7;
>
> 	uint i19;
>
> 	ushort len2;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str2[len2*2];
>
> 	ushort len3;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str3[len3*2];
>
> 	ushort len4;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str4[len4*2];
>
> 	ushort len5;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str5[len5*2];
>
> 	ubyte b28;
>
> 	uint i20;
>
> 	ushort s8;
>
> 	ubyte b29;
>
> 	ubyte b30;
>
> 	ushort s9;
>
> 	ushort len6;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str6[len6*2];
>
> 	ushort len7;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str7[len7*2];
>
> 	ushort len8;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str8[len8*2];
>
> 	ubyte b31;
>
> 	ushort len9;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str9[len9*2];
>
> 	ushort len10;
>
> 	// note: strings are wchar_t types, but hashed as bytes
>
> 	ubyte str10[len10*2];
>
> 	ubyte b32;
>
> 	ubyte b33;
>
> 	ubyte b34;
>
> 	ubyte b35;
>
> };
