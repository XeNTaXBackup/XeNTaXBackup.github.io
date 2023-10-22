## Post #1
- Username: sEri
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 26, 2009 8:02 pm
- Post datetime: 2012-08-16T07:30:03+00:00
- Post Title: [solved]The Dark Eye - Chains of Satinav, *.vis file

recently i've being studying the vis data file of the game "The Dark Eye - Chains of Satinav"

I found some png files in those archives. 
But in the header chunk(IHDR) of the pngs, those bytes that should be the width and height of the picture came out to be bytes like "0x31 0x34 0x32 0x93","0x35,0x64,0x61,0xf2"
it's odd, seems those bytes have been encrypted

the data structure of the vis file I figured out so far is like that:

Length : 0x0E   header of the file
Length : 0x10 * N   some data of N files in this archive, each have 16 bytes
Others: packed data, pngs, etc.

I think the 16 bytes data of each file may be the "key" to solve the width/height encryption, but i can't figure out why
Any one helps? Thx in advance

there's a sample uploaded, which contains two files. One has only one png packed, while another vis have several file paced.


 characters.zip
(146.23 KiB) Downloaded 42 times
## Post #2
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-10-03T12:15:38+00:00
- Post Title: [solved]The Dark Eye - Chains of Satinav, *.vis file

Solved.. How??
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-10-03T12:53:51+00:00
- Post Title: [solved]The Dark Eye - Chains of Satinav, *.vis file

> Reply from jioc01
>
> Solved.. How??This game use Visonaire Studio Adventure Game Engine: http://www.visionaire-studio.net/news/a ... f-satinav/
You can extract *.vis files with two methods:
XpoZed's Unpakke (Recommended): http://www.nullsecurity.org/unpakke

```
unpakke upkk_vis3.dll unpack file.vis Folder
```
or
QuickBMS: [http://aluigi.org/papers/bms/visionaire.bms](http://aluigi.org/papers/bms/visionaire.bms)

```
quickbms -w visionaire.bms file.vis Folder
```
[/b]
## Post #4
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-03T20:00:18+00:00
- Post Title: [solved]The Dark Eye - Chains of Satinav, *.vis file

> Reply from delutto
>
> jioc01 wrote:Solved.. How??This game use Visonaire Studio Adventure Game Engine: http://www.visionaire-studio.net/news/a ... f-satinav/
You can extract *.vis files with two methods:
XpoZed's Unpakke (Recommended): http://www.nullsecurity.org/unpakke
Code: Select allunpakke upkk_vis3.dll unpack file.vis Folderor
QuickBMS: http://aluigi.org/papers/bms/visionaire.bms
Code: Select allquickbms -w visionaire.bms file.vis Folder[/b]

Wonder if there's a repacker as well for it. The game looks interesting.

Update: I've tried unpacking data.vis with unpakke, but it returned only with az unending series of "Unknown type: 65F81000" messages - after it created more than 1400 zero-byte sized files I interrupted it.

Oezmen's VISExt has managed to extract sounds and other assets, including a seemingly randomly named .xml, but since I have game translation in mind, I don't know if the files extracted with VISExt can be repacked by unpakke. Is it possible, or if not, what am I doing wrong? I used both programs in Win7 x64 with the GoG version.
