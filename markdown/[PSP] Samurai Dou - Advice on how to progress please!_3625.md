## Post #1
- Username: wigifer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 03, 2009 5:46 pm
- Post datetime: 2009-08-03T10:09:35+00:00
- Post Title: [PSP] Samurai Dou - Advice on how to progress please!

Hi, new here and to the game archive research scene, thought I'd hit the ground running by enquiring regarding something I've been working on thanks to DGTEFF...

I've so far been working on extracting the files from volume.dat in a PSP game entitled Samurai Dou, determined where the relevant data is and worked from there. Simple enough:

```

<Unknown data at start of archive>

<Anywhere between 25-50 bytes of blank data>
<File contents>
<File directory structure/name>
```


The files themselves can be extracted in their entirity by just creating the file from the hex, so definitely uncompressed file contents as a "chunked archive". The problem is finding at the start of the document how it's defining where the data IS. The format which I would assume points out where the files are is divided up as follows:

00 00 00 <Specified HEX>

The Specified HEX doesn't actually match up to a point in data or anything however, nor is it anything incremental as far as I can see. I've got as far as I can go with the DGTEFF, but I think I've been reading it so much it now confuses me as to what I should be looking for (I'm probably looking for the wrong thing!). Anyone got any tips for signs as to what I should be looking for, any examples from similar chunked archives?... I don't want to feel guilty by getting someone else to do the work for me, plus this seems like a good place to start myself before moving on to more advanced archives with other games. Seeing as I'm curious and want to have a look.

Cheers guys!
