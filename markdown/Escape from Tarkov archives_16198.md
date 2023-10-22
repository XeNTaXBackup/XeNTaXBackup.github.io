## Post #1
- Username: kishmish
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 25, 2017 7:12 pm
- Post datetime: 2017-04-25T11:38:21+00:00
- Post Title: Escape from Tarkov archives

Escape from Tarkov seems to be using encrypted archives, but only for weapon files.
I was able to open everything else using Unity Assets Bundle Extractor.
I'd be grateful if somebody helped me unpack them.
Here's a sample: [https://mega.nz/#!1YYn0D7C!gZVYq1g8YuS7 ... MlG1Nus2vE](https://mega.nz/#!1YYn0D7C!gZVYq1g8YuS7itq6u9zq71a2ZM6-nPdmpMlG1Nus2vE)
Thanks in advance.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-04-25T11:58:08+00:00
- Post Title: Escape from Tarkov archives

It's XORed with 0x47.
## Post #3
- Username: kishmish
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 25, 2017 7:12 pm
- Post datetime: 2017-04-25T12:57:09+00:00
- Post Title: Escape from Tarkov archives

> Reply from merlinsvk
>
> It's XORed with 0x47.
Thanks! Is there a way to decrypt it?
I know nothing about these things.
## Post #4
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-04-25T13:59:27+00:00
- Post Title: Escape from Tarkov archives

> Reply from kishmish
>
> 
Thanks! Is there a way to decrypt it?

Use this little BMS script on both files. And after extract with AssetsBundleExtractor.

```
get fSize Asize
get fName filename

log fName 0 fSize

```
## Post #5
- Username: kishmish
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 25, 2017 7:12 pm
- Post datetime: 2017-04-25T14:22:16+00:00
- Post Title: Escape from Tarkov archives

> Reply from devmode
>
> kishmish wrote:
Thanks! Is there a way to decrypt it?


Use this little BMS script on both files. And after extract with AssetsBundleExtractor.
Code: Select allencryption Xor "\x47"
get fSize Asize
get fName filename

log fName 0 fSize

Thank you.
## Post #6
- Username: analblaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 17, 2015 5:05 pm
- Post datetime: 2018-05-29T00:24:59+00:00
- Post Title: Escape from Tarkov archives

I'd rather necro this for the context than make a new thread; I'm no expert so I can't be sure but they seem to have switched around the encryption by now, inevitably. Isolated archives can't be opened anymore, has anyone nailed down what they changed?
## Post #7
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2021-06-22T10:26:53+00:00
- Post Title: Escape from Tarkov archives

I really hope someone will look into this topic even after so many years and help me!  
I tried to export the mesh "weapon_glock_glock_17_gen3_9x19_LOD0" using [AssetsBundleExtractor_2.2stableb](https://community.7daystodie.com/topic/1871-unity-assets-bundle-extractor/) and got the error "Unable to read the mesh asset! (Unknowing asset format)". It doesn't matter if I choose "Export to .dae" or "Export to .obl".
This problem occurs not only with the Glock 17 mesh, but also when exporting meshes of any other weapon. All weapon modules and all textures are exported without problems.
I would appreciate any advice on how to get the weapon mesh.

Here are the bundle files that contain the Glock 17 mesh - [https://mega.nz/folder/eZ4ghAhQ#Je0wKuxuuw9y0YDDTqC8rg](https://mega.nz/folder/eZ4ghAhQ#Je0wKuxuuw9y0YDDTqC8rg)
