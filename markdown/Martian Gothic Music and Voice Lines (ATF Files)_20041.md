## Post #1
- Username: BornVillain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 26, 2015 9:47 pm
- Post datetime: 2019-04-17T02:43:22+00:00
- Post Title: Martian Gothic: Music and Voice Lines (ATF Files)

Hello everyone!  

I have a bit of a troubling challenge, I've been playing my favorite PC game "Martian Gothic: Unification" recently and I had a project in mind to compile all the audio logs in a series of events, as well as the text documents.

When I looked in the game directory, there was these .ATF files. Most likely archives by the size of them, and they're all supposedly in english. I am not entirely sure what the suffixes at the end are, my first guess was per actor but there's more voice actors on the roster than that.

Has anyone had any experience with this file format? I'll be willing to post a sample of the file if requested. Below is the screenshot of the sound file directory structure.
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-04-19T00:46:36+00:00
- Post Title: Martian Gothic: Music and Voice Lines (ATF Files)

Definitely please upload some samples!
## Post #3
- Username: BornVillain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 26, 2015 9:47 pm
- Post datetime: 2019-04-19T18:25:14+00:00
- Post Title: Martian Gothic: Music and Voice Lines (ATF Files)

[http://s000.tinyupload.com/?file_id=060 ... 2431486590](http://s000.tinyupload.com/?file_id=06091943312431486590) Here you go!
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-06T18:27:17+00:00
- Post Title: Martian Gothic: Music and Voice Lines (ATF Files)

If you still looking for info, I looked at this one a while, so here's my information on it:

The .ath files are indexes, and the .atf files are archives that contain dialogue text and audio data, referenced from the relevant .ath file.

The files within these archives don't have filenames, but the audio is stored as .wav files, so you can extract them with any extractor, such as Dragon Unpacker.


For the .ath files:

The index contains a table of 12 bytes per entry (3 DWORDS).  The number of entries is stored at offset 4 in the .ath file as a WORD value, and the actual table starts at offset 84.

The format for each entry is as follows:

DWORD - offset to text data block for this entry (a value of $FFFFFFFF seems to indicate an invalid entry ...)
DWORD - offset to audio data for this entry (WAVE file)
DWORD - size of audio data for this entry


For the .atf files:

Text entries have their own structure.  Each line of text consists of 8 bytes of data followed by a null-terminated string as follows:

DWORD - not sure what it represents exactly, but a value of $FFFFFFFF means there are no more lines of text in this particular block, otherwise a text string is present.
WORD - unknown
WORD - unknown
Text - null-terminated string

The above repeats until the $FFFFFFFF identifier is reached.  Each text block can have as many text entries as required.


Hope that helps.  Let me know if you need any more information.
