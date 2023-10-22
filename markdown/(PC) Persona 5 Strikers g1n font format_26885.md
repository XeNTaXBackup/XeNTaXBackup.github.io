## Post #1
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2023-06-21T02:02:14+00:00
- Post Title: (PC) Persona 5 Strikers g1n font format

Hey everyone,
I've been looking into the files of Persona 5 Strikers and apparently, it uses a bitmap font that's stored in a .g1n file. 
So far, while trying to map out g1n I found that the filesize is stored at 0x8h [as an int], and at 0x14h there's an int address that might(?) lead to the start of the texture data block inside the font file. 
I'm running into some issues trying to convert the texture into a readable format though. I've been messing with the file in hex, attempting to insert it into a g1t file [another proprietary Koei-Tecmo file that can actually be read by noesis], but no dice.

The furthest I've been able to get to is exporting a texture that seems to have the right size, but it looks incredibly fucked up.


I'm not too sure how to approach this cause I've never reverse-engineered a texture format before, but in case anyone with more experience here can help me, I'd really appreciate it.

I've attached two .g1n file examples in case anyone wants to look into them.
[https://cdn.discordapp.com/attachments/ ... _EFIGS.g1n](https://cdn.discordapp.com/attachments/744088482317860945/1120896333868445776/49071c1a_EFIGS.g1n)
[https://cdn.discordapp.com/attachments/ ... Korean.g1n](https://cdn.discordapp.com/attachments/744088482317860945/1120896334174617670/87e9cabf_Korean.g1n)
