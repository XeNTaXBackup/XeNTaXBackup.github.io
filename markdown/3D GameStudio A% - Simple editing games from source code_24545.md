## Post #1
- Username: iseeeva
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 19, 2021 10:04 am
- Post datetime: 2021-09-30T05:56:32+00:00
- Post Title: 3D GameStudio A% - Simple editing games from source code

Requirements
OllyDbg or x32dbg
3D GameStudio script: [http://aluigi.org/papers/bms/gamestudio.bms](http://aluigi.org/papers/bms/gamestudio.bms) (reference for the archive creator)

Removing limitations (Reference for A6 Engine)
1. Find "- script modified" comment and go to first call

2. 


The first function is an exe protector. If the game files have a changes this function triggered for crash.

The second function is an source code (*.wdl) protector. If a source code have a changes this function triggered for crash.

Creating new WRS Archive
I can not share the creator but 
WRS Archive consists of only 3 parts.



1. [Red] Archive header: Just a header "WRS<version>".
2. [Green] File header: Encrypted with xor key, repeated for each file and also includes the encrypted and unencrypted size of the file. (continuously 40 bytes).
2.1 [Purple] File size: its a encrypted(lzss) and unencrypted file size, can be read or edit by converting from hex to decimal. (shifts to the left as the size increases)
3. [Blue] File content: Encrypted with lzss.

If you're getting ready to try out an archive creator, i recommend bypassing the "first function" above first.
