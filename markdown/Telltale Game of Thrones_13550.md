## Post #1
- Username: Korkofilaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 19, 2015 2:04 pm
- Post datetime: 2015-11-19T07:34:55+00:00
- Post Title: Telltale Game of Thrones

Hello, newbie here.  
I'm trying to see if I can translate the subtitles to greek for the GOT telltale episodes. I currently have the steam version.
As far as I have seen from looking around, first I need to unpack the files.
I got ttarchext (and ttgtools) and tried the command line to unpack the GameOfThrones_pc_GameOfThrones101_data.ttarch2 file.
The screen says it extracted everything (long list of files) but my output file is empty when I check.
Maybe I gave a wrong command? Can someone give me an example of correct command line?
*I have put all the files (extractor and .ttarch2) in C:\ttgtools and set the output to C:\temp in the command.
Also, I will probably need to replace english with a greek font. Can you tell me which files I will need to change?
## Post #2
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-11-24T22:26:06+00:00
- Post Title: Telltale Game of Thrones

> Reply from Korkofilaki
>
> Hello, newbie here.  
I'm trying to see if I can translate the subtitles to greek for the GOT telltale episodes. I currently have the steam version.
As far as I have seen from looking around, first I need to unpack the files.
I got ttarchext (and ttgtools) and tried the command line to unpack the GameOfThrones_pc_GameOfThrones101_data.ttarch2 file.
The screen says it extracted everything (long list of files) but my output file is empty when I check.
Maybe I gave a wrong command? Can someone give me an example of correct command line?
*I have put all the files (extractor and .ttarch2) in C:\ttgtools and set the output to C:\temp in the command.
Also, I will probably need to replace english with a greek font. Can you tell me which files I will need to change?

1) Unpack the all .ttarch2 files with TTG tools.
2) Find the all .landb files
[Landb files = subtitles files.]
3) Use the Landb tools and unpack the txt files.
4) Use the tools and back landb files.
5) put the all translate land files, game locatioan/archives/
Warning: Only your launch files translated. Exampe = ...english.landb.

Landb tools = [http://www.mediafire.com/download/2qwrr ... /landb.rar](http://www.mediafire.com/download/2qwrrdxbxqsc34q/landb.rar)
design the program: rengareng
## Post #3
- Username: Korkofilaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 19, 2015 2:04 pm
- Post datetime: 2015-11-27T01:26:00+00:00
- Post Title: Telltale Game of Thrones

> Reply from Taner038
>
> 
1) Unpack the all .ttarch2 files with TTG tools.
2) Find the all .landb files
[Landb files = subtitles files.]
3) Use the Landb tools and unpack the txt files.
4) Use the tools and back landb files.
5) put the all translate land files, game locatioan/archives/
Warning: Only your launch files translated. Exampe = ...english.landb.

Landb tools = http://www.mediafire.com/download/2qwrr ... /landb.rar
design the program: rengareng

Thank you for the answer!
But when I try to unpack the .ttarch2 files, I get an empty folder - ttarchext lists the files on screen but nothing seems to exist in the output folder in the end.
Can you give me an example of a correct ttarchext command line for extraction?
## Post #4
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-11-27T10:48:23+00:00
- Post Title: Telltale Game of Thrones

> Reply from Korkofilaki
>
> Taner038 wrote:
1) Unpack the all .ttarch2 files with TTG tools.
2) Find the all .landb files
[Landb files = subtitles files.]
3) Use the Landb tools and unpack the txt files.
4) Use the tools and back landb files.
5) put the all translate land files, game locatioan/archives/
Warning: Only your launch files translated. Exampe = ...english.landb.

Landb tools = http://www.mediafire.com/download/2qwrr ... /landb.rar
design the program: rengareng

Thank you for the answer!
But when I try to unpack the .ttarch2 files, I get an empty folder - ttarchext lists the files on screen but nothing seems to exist in the output folder in the end.
Can you give me an example of a correct ttarchext command line for extraction?

ttarchext.exe -k 86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893 0 "D:\1\GameOfThrones_pc_Boot_data.ttarch2" "D:\1\Unpack

1 = game ttarch2 files folder.
## Post #5
- Username: Korkofilaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 19, 2015 2:04 pm
- Post datetime: 2015-11-29T02:32:52+00:00
- Post Title: Telltale Game of Thrones

> Reply from Taner038
>
> 
ttarchext.exe -k 86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893 0 "D:\1\GameOfThrones_pc_Boot_data.ttarch2" "D:\1\Unpack

1 = game ttarch2 files folder.

Thank you, I managed to make it work with this.
landb tools worked with episode 1 landb files but not with other episodes, will it be ok if I convert those to txt with ttgtools?

Also, I suppose there will be no greek letter font support, so can you tell me where to find the subtitle font file and edit it?
