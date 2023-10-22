## Post #1
- Username: ProphMicha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 02, 2021 10:08 pm
- Post datetime: 2021-11-02T17:18:08+00:00
- Post Title: FSB Syncpoints

A few months back I was deep-diving into FSB creation as I wanted to manually create them instead of requiring an outdated FMOD Designer that has basically had its existence scrubbed from the FMOD website. The one thing I was absolutely never able to figure out is how syncpoints are created and how to figure out what time point they signify. I have dug up an image I made to point out what was what in an FSB syncpoint and the only part I cannot understand is the part marked Frame?. 


(note: Since making this image, I have figured out that syncpoint name and the unknown 246 bytes are part of the same thing, adding to a total of 256 bytes, though the 256th byte appears to be a 0x00 spacer, as a wave file with a 256 character cuepoint crashes FMOD Designer)
