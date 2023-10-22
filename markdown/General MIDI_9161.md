## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-27T21:14:49+00:00
- Post Title: General MIDI

I've got a file from a DOS game that contains data with the following string:

"General MIDI (Roland MPU-401 interface or 100% compatible)"

Are there any specs for this format or something that can play it?

Files in question:
[data.7z](https://xentaxbackup.github.io/file/5521_data.7z)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-27T21:30:01+00:00
- Post Title: General MIDI

those aren't midi files; midi files have track chunks and other types of chunks. there are no identifiable midi chunks in your files at all.

i think it's related to this: [http://www.radgametools.com/miles.htm](http://www.radgametools.com/miles.htm).
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-27T21:36:33+00:00
- Post Title: General MIDI

Well, it's a DOS game so maybe it's an older format? lol
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-27T21:47:40+00:00
- Post Title: General MIDI

midi hasn't changed in a very long time. the note on event on channel 0 begins with an 0x90. in a typical midi file, you will typically find something like this:

```

```


note off on channel 0 is 0x80 so typically you will see a stream of 0x90 + 3 bytes mixed in with 0x80 + 3 bytes somewhere in the file. though many software vendors don't use note off at all (since note on duration takes care of that), so you typically see a stream of 0x90XXXXXX - 0x9FXXXXXX values somewhere in a midi file.
## Post #5
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-09-16T14:13:29+00:00
- Post Title: General MIDI

I think those files are some sort of "drivers" for different types of sound cards.
