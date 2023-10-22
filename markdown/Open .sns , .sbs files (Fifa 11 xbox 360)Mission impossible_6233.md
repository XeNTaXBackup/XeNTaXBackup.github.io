## Post #1
- Username: Jura88
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 18, 2011 10:42 pm
- Post datetime: 2011-03-18T15:04:19+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

Hi, sorry for my english. I have these two files : the first one , 1.sns , is certainly a song that is compressed in this strange archive . I've done tons of researches concerning this format but it seems no one on earth could open it. The second one , reaction.sbs, contains chants,commentary and other audio stuff. I also tried the quickbms method but here's what my hex editor shows 


I tried following the guides to create my own script but I don't know where to start. 
Here the two files : [http://www.2shared.com/file/xU8N77N-/file_xbox360.html](http://www.2shared.com/file/xU8N77N-/file_xbox360.html)

I will appreciate any help, thank you.
## Post #2
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-03-19T11:36:05+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

For sns files, you can use [this tool](http://www.box.net/shared/v018s6v1dn).
This tool is consist of :
1. quickbms.exe
2. towav.exe
3. ea_multi_xma.exe
4. xma_test.exe
5. addXMARIFFheader.bms
6. and Start.bat

For canverting sns files of FIFA 11, just click on Start.bat .
## Post #3
- Username: Jura88
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 18, 2011 10:42 pm
- Post datetime: 2011-03-19T16:00:53+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

Thank you! It works! Were the hell did you find this?  So it remains only the .sbs now. Please help me just a little more!
## Post #4
- Username: Jura88
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 18, 2011 10:42 pm
- Post datetime: 2011-03-21T14:29:36+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

Help me !
## Post #5
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-07T08:45:45+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

does anyone require the actual files to be uploaded in order to verify if they can be decompressed?
## Post #6
- Username: Jura88
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 18, 2011 10:42 pm
- Post datetime: 2011-04-07T21:56:44+00:00
- Post Title: Open .sns , .sbs files (Fifa 11 xbox 360)Mission impossible?

Hi , I have news.

Rinaldo says :

I guess I need the help of some expert in audio coding. I have been able to understand the structure of .sbr files, they are just a kind of descriptor for locating the actual sounds that are in the .sbs file (e.g. ita_it.sbs) It is also possible to recognize in .sbs some chunks of data starting with a 2 bytes chunk descriptor followed by the size of the chunk in 2 bytes. I found 3 type of chunks: 
data starting with 0x48 0x00 describe the sampling rate and other parameters and it is always the first chunk of each sound. 
data starting with 0x45 0x00 are just the sound terminator. 
data starting with 0x44 0x00 are the actual audio data but they are compressed in a form I cannot figure out. 

Opening a .sbs file with an hex editor I think you can easily recognize the chunk identifiers. The question is: which is the format used by 0x44 0x00 chunks to encode audio data ?
