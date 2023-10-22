## Post #1
- Username: cristyro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 09, 2020 6:55 am
- Post datetime: 2020-05-13T14:15:05+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

Can anyone please help me with extracting Persona 2 PS1 .BIN files? I have tried many times with QuickBMS but I always get errors, due to my lack of knowledge using it properly. 

These sample files appear to have readable text using hex editors, most commonly near the end of the file: [https://www.dropbox.com/s/l8ix9pno6tk08 ... es.7z?dl=1](https://www.dropbox.com/s/l8ix9pno6tk08l3/text_samples.7z?dl=1)
The hex sequence 01 11 36 11 20 appears to be a new line trigger ( \n or {0A} ) as far as I can see.
Later Persona games use BMD, BF, PM1 and MSG file formats for text, it's pretty much the Atlus standard, but I've no idea about this game. 

These files have the magic identifiers pqes/pbav inside them so I guess they are/contain seq files that have audio in them (pgconv is able to find midi files inside and play them): [https://www.dropbox.com/s/34pwgplo9ngdo ... es.7z?dl=1](https://www.dropbox.com/s/34pwgplo9ngdoib/audio%20samples.7z?dl=1)

This file has character portrait images inside (I was able to extract 266 png files from it with jpsxdec): [https://www.dropbox.com/s/e0v67mjmkshkk ... le.7z?dl=1](https://www.dropbox.com/s/e0v67mjmkshkkhr/unknownfile.7z?dl=1)
However, I don't recall how I got it, it might've been altered by an incorrect extraction with quickbms, so if there are issues with it, that's probably why.

When I tried to extract F0000.bin with quickbms, I got an incorrectly extracted, empty file with this filename: mi\src\m_mvivw.c , although I'm not sure if it's really inside the archive or the script was just wrong. This is a much smaller file. Here it is:  [https://www.dropbox.com/s/l7chjh2jw5cc75j/F0000.7z?dl=1](https://www.dropbox.com/s/l7chjh2jw5cc75j/F0000.7z?dl=1)

There might be .dat or .mde files inside, but I was unable to extract any. If you need more sample files, I can provide them.

Thank you for taking the time to read this!
## Post #2
- Username: cristyro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 09, 2020 6:55 am
- Post datetime: 2020-12-17T09:32:08+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

Anyone?
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-17T10:01:29+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

It doesn't look like archive file.
And what quickbms script are you using?
## Post #4
- Username: cristyro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 09, 2020 6:55 am
- Post datetime: 2020-12-17T12:29:12+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

> Reply from ikskoks ↑Thu Dec 17, 2020 6:01 pm at Thu Dec 17, 2020 6:01 pm
>
> 
It doesn't look like archive file.
And what quickbms script are you using?

I've been trying with many scripts, first I've tried with all available Persona related scripts, including the Persona 2 BIN extractor (which is meant for the PSP version so it doesn't work).
## Post #5
- Username: cristyro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 09, 2020 6:55 am
- Post datetime: 2021-03-10T09:07:02+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

Can anyone help please?
## Post #6
- Username: eiowlta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 22, 2021 8:47 pm
- Post datetime: 2021-06-22T13:32:29+00:00
- Post Title: Persona 2 Eternal Punishment PS1 (.BIN)

I'm working with P2EP, but I can tell you that some of the .bin files are actually code, even if they contain some strings in them.  I can detail the format for you if you'd like, but in short the files are generally either RLE or LZSS encoded.  The format is notably different than later games, though you can clearly tell the later ones are an evolution of these.  I'm working on some extraction/insertion tools and once they're done I intend to put them up on github.  

01 11 is newline, 36 11 indicates the start of a string.  0x20 is just a space character.  2e 11 xx xx is for setting the color and so on.  The commands are actually 16bit LE integers, ab cc where a=1 indicates a command, b indicates the length of the command in 16 bit words and cc is the command.
