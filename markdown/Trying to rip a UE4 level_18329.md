## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2018-07-07T11:35:21+00:00
- Post Title: Trying to rip a UE4 level

I'm trying to rip some old fanmade UE4 levels so I can convert them into Launch Environments for SteamVR.

Map1 (UE 4.12)

```
https://mega.nz/#!JpczkZQL!HpMHmUtcxoQZWsom6mLtocq8clKZVbJ5mIrfvDrLMec
```


Map 2 (UE 4.17)

```
https://drive.google.com/file/d/0BzY0iE-8FLJeQ2xWLWw3RTQ3OGc/view
```


I've unpacked them with QuickBMS, and on the first one I had to change some filenames from garbled unicode back to their original Chinese, but when trying to open them with their respective versions of UE4 editor, both crash.

Map 1 tries to allocate 286GB of RAM to D:\ (have changed UE4 install to my D:\ but still same error). Map 2 says its .umap is an asset and not a map (indication of corruption).

Tried capturing them with Ninjaripper but they only run with the DX11 wrapper and nothing happens when I press the different capture keys.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-07-08T04:21:42+00:00
- Post Title: Trying to rip a UE4 level

> Reply from zzz
>
> 
I've unpacked them with QuickBMS, and on the first one I had to change some filenames from garbled unicode back to their original Chinese, but when trying to open them with their respective versions of UE4 editor, both crash.

Map 1 tries to allocate 286GB of RAM to D:\ (have changed UE4 install to my D:\ but still same error). Map 2 says its .umap is an asset and not a map (indication of corruption).

There is no corruption, you're using packaged files, a shipped .umap file is **not** the same as an editor version at all, thats why it doesn't work.

What you're attempting to do is effectively attempting to placing sushi back in the ocean and waiting for it to swim.

The extension is similar, thats largely where the similarities end.

Maps in unreal are counted as 'assets' they're just maps, everything in unreal is an asset, regardless of what it is or what its for.

Additionally simply opening a .umap file on its own wouldn't work, umap files contain references to the object files and paths, along with the texture references etc, you'd still need to have all the actual uasset files in order to correctly open a map, otherwise it'd just be a blank map that can't find any references.
## Post #3
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2018-07-08T18:26:28+00:00
- Post Title: Trying to rip a UE4 level

You're right, that umap file was nothing but lightmaps. Doing some more research has got umodel spitting out static mesh files. thanks.
