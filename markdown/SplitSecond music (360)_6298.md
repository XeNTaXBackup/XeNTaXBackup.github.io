## Post #1
- Username: Tatsh
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 25, 2011 10:50 am
- Post datetime: 2011-03-26T01:47:53+00:00
- Post Title: Split/Second music (360)

I wanted the highest quality I can get for this game. 360 has the audio in 48 KHz XMA2. PSP has the audio (already decodable) in a lower quality.

Notes:

The OST is terrible! Do not waste your time with that.
FFShrine had a link to these files in XMA format already done but that link is dead.

Either way, this is how I did it (based on some information at [viewtopic.php?f=17&t=3020&p=33639](http://forum.xentax.com/viewtopic.php?f=17&t=3020&p=33639)):
1. I extracted the game's ISO. Any extractor can work.
2. Used fsbext to get the audio files out. They are not encrypted in any way. The file for general game music is at DEFERRED/AUDIO/SUBMISSION/MUSIC. You only need the FSB file.
3. Get the XMA2 header. [http://hcs64.com/files/xma_header.zip](http://hcs64.com/files/xma_header.zip)
3. Now for each file prepend the XMA2 header. I use Linux and Bash, so I put each XMA file (they end in .wav) in a directory named xmawav. Then I made another directory alongside named xma.

```
$ for i in *.wav; do cat ../header2 > ../xma/"${i%.*}.xma" && cat "$i" >> "../xma/${i%.*}.xma"; done

```

4. Use towav to convert the new '.xma' files. This works in Wine if you want to use that. Test!!

```
$ wine towav.exe *.xma
$ rm *.xma
$ mplayer *.wav # test

```


Enjoy.

Now off to figure out how to construct a good soundtrack from these loops. Something that actually feels like the game unlike the OST!
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-26T19:17:20+00:00
- Post Title: Split/Second music (360)

Or you can just drop the fsb file into towav and it will convert all the tracks for you.
