## Post #1
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-03-20T19:53:07+00:00
- Post Title: Harry Potter and the Chamber of Secrets - .uax speech files

Hi,

I'm looking into the AllDialog.uax file for Harry Potter and the Chamber of Secrets PC and I'm struggling to decode the speech files that are inside. I've managed to extract everything via an Unreal extraction tool but the format of the resulting files doesn't seem to be recognised by any media player or any of the more specialised game audio playing tools. The files come out with a ".sound" extension but don't have any recognisable header to me - when I open them as raw in Audacity I can here some barely discernible speech in amongst lots of noise. They're not XAs (that's what I asumed at first) and the sx.exe that comes with the game doesn't recognise them either.

I'm assuming the files are compressed audio? Oddly, if I use Dragon's HyperRipper I can pull out some genuine wave files from the UAX file but these seem to be separate from the files that are spat out after extraction, and they're much fewer in number.

The longest of the files I've put up here: [https://www.dropbox.com/s/mwmr1ulpyxeu1 ... Sound?dl=0](https://www.dropbox.com/s/mwmr1ulpyxeu1g2/PC_AsG_DracoNotHeir_22.Sound?dl=0) The first 4 bytes, "00 01 84 01", are the same between all files, but again they don't match any header I've researched as they're not even ASCII. Would anyone be able to shed some light on this?

Thanks.
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2015-03-21T09:12:35+00:00
- Post Title: Harry Potter and the Chamber of Secrets - .uax speech files

Had a quick look, it looks like header runs about 26 or 24 bytes long, specifying the file as 22khz and mono (?)
In any case, the silent parts sure seem hint familiarly that its EA's XA ADPCM (not sure which variant of all of them made)

Not much help to you given custom header that no converter supports, would need someone more educated on EA ADPCM variants to take a look.
## Post #3
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-03-21T09:18:35+00:00
- Post Title: Harry Potter and the Chamber of Secrets - .uax speech files

Interesting. What's the standard XA header? I might try manually writing it in and seeing if I can get the supplied sx.exe to work its magic.
## Post #4
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-03-24T06:30:06+00:00
- Post Title: Harry Potter and the Chamber of Secrets - .uax speech files

You can use Dragon UnPACker if I remember.
## Post #5
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-03-24T06:41:44+00:00
- Post Title: Harry Potter and the Chamber of Secrets - .uax speech files

I was specifically looking for the narration by Stephen Fry, which AFAIK isn't present on the console versions of the game. :c
