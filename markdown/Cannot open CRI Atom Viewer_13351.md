## Post #1
- Username: Filo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 07, 2011 11:01 pm
- Post datetime: 2015-09-21T18:34:16+00:00
- Post Title: Cannot open CRI Atom Viewer

I managed to extract .awb file from .cpk and I'm trying to open it in AtomViewer. But when I'm trying to open CRI Atom Viewer or Craft I get this error:
[http://i.imgur.com/cyfNo8q.png](http://i.imgur.com/cyfNo8q.png)
I reinstalled .NET Framework several times, but it still doesn't work.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-22T09:55:05+00:00
- Post Title: Cannot open CRI Atom Viewer

Can you upload the AWB file?
## Post #3
- Username: Filo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 07, 2011 11:01 pm
- Post datetime: 2015-09-22T10:00:08+00:00
- Post Title: Cannot open CRI Atom Viewer

Here's both .AWB and .ACB files:
[http://www.mediafire.com/download/4zbex ... 100100.rar](http://www.mediafire.com/download/4zbexk8216svooq/100100.rar)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-22T10:59:11+00:00
- Post Title: Cannot open CRI Atom Viewer

Seems to be a new thing that's happening recently. CRI's started XORing the HCA headers. Not sure if its just the strings that are being XOR'd however.
## Post #5
- Username: Filo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 07, 2011 11:01 pm
- Post datetime: 2015-09-22T11:33:05+00:00
- Post Title: Cannot open CRI Atom Viewer

Do you know a way to fix my problem with CRI Atom Viewer? I tried using it on my other PC and it still gives the same error.
It should be possible to at least listen to these sound files there. I found YouTube video with voice of character that isn't available currently in game, but the uplouder only said in description 'CRI ADX2 & Android SDK'.
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-22T11:46:30+00:00
- Post Title: Cannot open CRI Atom Viewer

Sorry, my programming knowledge is quite limited.

The problem is that atom viewer can't read the HCA audio files because the headers have been manipulated.

The interesting thing is that the entire file isn't XOR'ed.

From what I can tell, only the strings in the header like "HCA" "fmt" "comp" "pad" have been. The sample rate and channels have been left untouched.

To even listen to the sound files you would need to first reverse the XOR on the AWB file (which is 0x80)
