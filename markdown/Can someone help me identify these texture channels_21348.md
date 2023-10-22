## Post #1
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2019-11-05T22:44:19+00:00
- Post Title: Can someone help me identify these texture channels?

Hi, so I got these textures from Ninja Ripper but I'm having so much trouble assigning these image textures to the correct/proper channel (especially the roughness, spec, metalic, etc)


Download: [https://www.mediafire.com/file/0v73akh5 ... e.rar/file](https://www.mediafire.com/file/0v73akh5xeez1cp/NinjaRipper_Texture_Name.rar/file)

Here's what I think these channels mean
1. Diffuse/Albedo/Color (Alpha)
2. Derivative Normal Maps 
3. Roughness? Spec?
4. Displacement? Height Map? Metalic? Spec?
5. Also kinda look like Spec?

I've tried them in Marmoset Toolbag 3 but it didn't seen to come out right... I also tried it on Blender 2.80 Eevee too but it just didn't display correctly like in the game.

So yeah, beside the first 2, I'm not sure about the rest, I've included the Obj and textures on the download link here so if any of you can help me identify these, I'll really appreciate it.
Download: [https://www.mediafire.com/file/0v73akh5 ... e.rar/file](https://www.mediafire.com/file/0v73akh5xeez1cp/NinjaRipper_Texture_Name.rar/file)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-11-06T07:20:15+00:00
- Post Title: Can someone help me identify these texture channels?

1. Diffuse/Albedo/Color + Alpha
2. Normal map, though it looks like one of the channels is inverted, possibly B, or could be missing entirely.
3. Looks like a roughness map.
4. This looks like specular highlights, so I'd say a specular map.
5. Looks like a mask, potentially a color tint mask if I had to guess.

How does the character/object look ingame?
Are they really shiny? as if they're really shiny then its possibly theres a metallic map instead of a specular map.
Do they get wet?
Just from the textures alone its a bit difficult to be completely sure.
## Post #3
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-11-08T14:24:04+00:00
- Post Title: Can someone help me identify these texture channels?

hard to tell how the roughness is intended to look.

1) diffuse
2) normal - depending on the tangent space you gotta invert the green channel - and ofc add or compute the blue channel
3) roughness - you choice if you wanna roughen the crystals on it - i inverted it to make them less rough aka shiny
4) specularity or general gloss or metal or whatever - shinyness
5) potentially specular color on the decoration pattern

[https://i.imgur.com/XFrJ4PS.jpg](https://i.imgur.com/XFrJ4PS.jpg)
