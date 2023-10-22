## Post #1
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-18T19:55:53+00:00
- Post Title: DXGI ASTC .dds?

So. Ive been trying to convert some DDS textures from Mario + Rabbids: Kingdom Battle But the majority of the textures seem to use a rather obscure format.
[http://www.voidcn.com/article/p-kbbvdkbn-yg.html](http://www.voidcn.com/article/p-kbbvdkbn-yg.html)
The only mention i could find of the format is here.

The official ARM ASTC tools don't work with the files either.
Presumably because its not a "true" ASTC file.

Ive provided a sample file archive with some of the textures.
[cursor.zip](https://xentaxbackup.github.io/file/14761_cursor.zip)
## Post #2
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-18T20:04:47+00:00
- Post Title: DXGI ASTC .dds?

Note one of the files i included has no header. I should have added it before sending it...
The one that does not end in _e does have a header though.
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-19T02:36:41+00:00
- Post Title: DXGI ASTC .dds?

I don't understand where the enum is supposed to occur. If it's the first byte then it is BC5, because that's what lines up with the provided enumeration structure.
## Post #4
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-19T16:52:05+00:00
- Post Title: DXGI ASTC .dds?

My bad. I didn't include headers at all it seems.

Heres a DDS with the correct header added.
[cursorheader.zip](https://xentaxbackup.github.io/file/14763_cursorheader.zip)
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-19T16:57:36+00:00
- Post Title: DXGI ASTC .dds?

Using [Noesis](https://richwhitehouse.com/index.php?content=inc_projects.php) opens up the image, but it appears to be just white.
## Post #6
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-19T19:21:29+00:00
- Post Title: DXGI ASTC .dds?

Thats...odd.
Are you sure noesis supports the DXGI format it seemingly uses?
It shouldn't be just white.
## Post #7
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-20T02:41:39+00:00
- Post Title: DXGI ASTC .dds?

You appended the header to use DXT10. Noesis should support this.
## Post #8
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-20T10:16:24+00:00
- Post Title: DXGI ASTC .dds?

I tried the same file with a program called "Renderdoc" and it gave me the "Unsupported DXGI Format "174" error.

Perhaps the file is corrupted?...

EDIT: Wait...does it not say DX10? It says that for me.
Maybe I'm thinking of a different texture
## Post #9
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-08-20T11:06:05+00:00
- Post Title: DXGI ASTC .dds?

maybe noesis doesn't support the astc compression in dds files. this enum on this website is not official from microsoft either. i think i heard that astc was added to dx11 or dx12 but their specs and docs are lacking a lot of updates. sure

i'm certain you could move the block data into another file format container and use noesis to open the stuff by fiile handler. i've seen somebody do that with some files.
## Post #10
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-20T11:44:33+00:00
- Post Title: DXGI ASTC .dds?

Yeah i just checked with some actual ASTC textures from Super Mario Odyssey.
Noesis can't open them.

Probably gets tripped up by it being a DDS in the case of M+R.
## Post #11
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-29T21:46:09+00:00
- Post Title: DXGI ASTC .dds?

anyone looked at this more?
still can't figure it out
