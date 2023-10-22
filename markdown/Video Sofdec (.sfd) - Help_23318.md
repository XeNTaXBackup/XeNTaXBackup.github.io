## Post #1
- Username: noproblemxd
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 17, 2021 1:03 pm
- Post datetime: 2021-01-17T06:21:49+00:00
- Post Title: Video Sofdec (.sfd) - Help

Good day everyone  

How can I change the SFA audio inside an SFD file  

If someone could help me I appreciate it very much
## Post #2
- Username: FQRb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 17, 2021 10:05 pm
- Post datetime: 2021-01-17T20:27:26+00:00
- Post Title: Video Sofdec (.sfd) - Help

~ [http://andrewduncan.net/mpeg/mpeg-1.html](http://andrewduncan.net/mpeg/mpeg-1.html)
~ [https://en.wikipedia.org/wiki/ADX_(file_format)](https://en.wikipedia.org/wiki/ADX_%28file_format%29)
# MPEG-1 can be deconstructed and broken down to smaller packets.
# ADX usually starts with a 0x80, 0x00 sequence, and holds a relative offset to the string: "(c)CRI".

Here's what you're supposed to do:
1. Locate "(c)CRI" in the SFD file, and trace back to [0x000001BA] sequence: [https://i.imgur.com/ZKBqI0o.png](https://i.imgur.com/ZKBqI0o.png) .
2. Find the next [0x000001] sequence, the packet start-code prefix,.
3. The way you know it's the correct one, is by checking the next byte, for example: [0xC0] = 0b11000000 (110xxxxx: audio (correct), 1110xxxx: video).
5. Right after it is a 16-bit word, the first byte is not to be changed, since it is a relative-offset to the start of ADX. (In my case: 0x07E7)
6. Skip this word, and get the Offset of the byte you're selecting. (In my case: 0x2012)
If you add first byte of length(0x07) to it(0x2019) and jump there, you'll find the ADX header [0x8000].
If you add packet-length(0x07E7) to it(0x27F9), you'll end up in the next part of the MPEG-1 file.

Once you have where the length is located, where both start and end of the ADX are, you can simply modify them.
If you're stuck or you need more details, feel free to send a message.
## Post #3
- Username: noproblemxd
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 17, 2021 1:03 pm
- Post datetime: 2021-01-18T05:34:32+00:00
- Post Title: Video Sofdec (.sfd) - Help

Sorry, I don't understand much about encoding and decoding. But the file I want to modify looks simple.
## Post #4
- Username: FQRb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 17, 2021 10:05 pm
- Post datetime: 2021-01-18T20:43:45+00:00
- Post Title: Video Sofdec (.sfd) - Help

That's fine!
Seems like I can't send you any private messages, since you've disabled them, apparently.
Can you attach the 'to-be-modified' SFD file, and the ADX you want to merge therein?
I'll see what I can do about it :=)!
## Post #5
- Username: noproblemxd
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 17, 2021 1:03 pm
- Post datetime: 2021-01-19T05:15:19+00:00
- Post Title: Video Sofdec (.sfd) - Help

Done!. I wrote you by private message
## Post #6
- Username: FQRb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 17, 2021 10:05 pm
- Post datetime: 2021-01-19T22:38:30+00:00
- Post Title: Video Sofdec (.sfd) - Help

Here goes: [https://pastebin.com/2ikmDSCq](https://pastebin.com/2ikmDSCq)
I've sent the overwritten file, which seems perfectly in place, I'll wait and see how you find it to be.
## Post #7
- Username: noproblemxd
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 17, 2021 1:03 pm
- Post datetime: 2021-01-21T23:56:08+00:00
- Post Title: Video Sofdec (.sfd) - Help

Testing
## Post #8
- Username: noproblemxd
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 17, 2021 1:03 pm
- Post datetime: 2021-01-26T00:05:16+00:00
- Post Title: Video Sofdec (.sfd) - Help

Solving technical problems...

Edit 1:
The problem: The SFD video (Modified by FQRb) never ends.
It must be skipped manually with a button..

Edit 2:
The problem is because the audio file used was a "direct" ADX audio (and a little longer than the original) and not an SFA encoded audio [SFA (Sofdec Audio) files are used to create SFD files with sound] .

Edit 3:
The SFD file that I want to modify contains an SFA audio.

Edit 4:
  I am editing the file manually, it may take some time...

I'll come back later
