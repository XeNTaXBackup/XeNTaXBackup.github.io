## Post #1
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-26T18:15:41+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Hi. I've been trying to extract/convert/view .tex files from the ps2 version of the legend of spyro a new beginning (develpoed by Krome) with very little luck. After trying out numerous .tex file handling pieces of software only Raw texture cooker was able to make something out of the file, more specifically a colourful mess of pixels in .dds.
   As far as searching the XeNTaX forums go, it seems that Noesis should be able to handle cases such as mine, given it has the right script(s) to work with. Script(s) that I do not have and am unable to find. At least other people seemed to have successes using Noesis to deal with some other .tex files developed by Krome.
   So if you could point me to the direction of scripts and/or programs capable dealing with this, it would make my day.

Thanks in advance.
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-26T23:23:45+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

you got some file samples?
## Post #3
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-27T10:37:06+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

[https://mega.nz/#!UGYnwQxR!n25PMLan1Ivm ... wSk-zoZeQ4](https://mega.nz/#!UGYnwQxR!n25PMLan1Ivmwn2SQUzvLmKVbbGTRiAp7wSk-zoZeQ4)
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-27T11:36:19+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

well. have a noesis plugin. it extracts only this texture right now. if it needs more formats, like 4-bit or swizzled, i need more samples.

btw... voxels and spyro? i could make a wrong guess here, who you are. 
[tex_Spyro_tex.rar](https://xentaxbackup.github.io/file/16657_tex_Spyro_tex.rar)
## Post #5
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-27T17:41:02+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Thanks episoder, you're super. It seems this script is able to decipher most/all of the skins for the characters, so that's something. Then again it runs into problems handling some other .tex files. Take this for example:
[https://mega.nz/#!dOAxQICK!qxd1pIQyGpyW ... l8086UL2Zc](https://mega.nz/#!dOAxQICK!qxd1pIQyGpyWgmJxSuTbtqgcAZjPynkXTl8086UL2Zc)

It always weirdly manages to put together a different picture, sometimes it looks somewhat sensible, sometimes pretty much nothing at all. I am quessing this is to do with the formats, bits and whatnots you mentioned.
Before asking other people to do all the heavy lifting for me is there any easy enough way for me to know and/or deal with formats, swizzles and stuff myself for example by modifying the noesis plugin you gave me. I say "easy enough" for I am not a code whiz at all, (though I read the hexadecimal thingy for beginners from Discord) but I think I could manage if it was about changing some words in the script as long as I know what to change them to.

And as to guessing my identity I just picked a random name that came to mind. It doesn't have anything in particular to do with Spyro.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-28T00:30:06+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

wait what? no... i will not try to explain ps2 hex formats. that's madness. i will check the new sample file tmr (need for sleep) tho.
## Post #7
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-28T11:13:01+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

It's that complicated a matter? Well that's a shame, I wish I could have been some use. Thanks for looking into these files and making scripts, I hope it's not too much of a headache.
## Post #8
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-28T12:38:10+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

well it's not very complicated if you know what to search for and do. like *cough* depuzzling the bitplanes, cause noesis' 4-bit decoder doesn't do it. *cough* there's also the cross pointer dance to do to resort the ps2 palette. this format being straight bitplanes is rather easy too. the swizzled formats are a tad more complicated to detect and figure out. there are other formats with chunks all over the place out there, that make you go crazy. i still haven't managed to decode the dmc backgrounds yet, for example. capcom is pretty nuts when it comes to complications.

anyway, v2.
[tex_Spyro_tex.rar](https://xentaxbackup.github.io/file/16662_tex_Spyro_tex.rar)
## Post #9
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-28T17:52:31+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Not very complicated huh? If you say so.
Okay, after converting the textures it seems we're about two thirds through. Here would be the next case previous scripts were unable to solve:
[https://mega.nz/#!cCICVSga!UfdXgUCNFzmu ... KbWeT9_ptk](https://mega.nz/#!cCICVSga!UfdXgUCNFzmuHaj13XHlw98h8RpPRnO8yKbWeT9_ptk)
## Post #10
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-28T21:16:50+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

alright. v3. i got the format byte wrong and it's using the 'internal' format enum. in case you come across rgba32 textures, it should do those too. 16 bit flat memory textures are pretty rare. i'm not fuzzed to include those rn.
[tex_Spyro_tex.rar](https://xentaxbackup.github.io/file/16663_tex_Spyro_tex.rar)
## Post #11
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-29T09:42:36+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Looking good, now the script can manage the entire .tex library without running into errors when using Noesis' batch process. However a couple hiccups remain. Take this for example:
[https://mega.nz/#!4DYjRSwJ!ega96aw_Xi5R ... LawvCVVbcY](https://mega.nz/#!4DYjRSwJ!ega96aw_Xi5RTLze6sjHjUQv_FMTpge_YLawvCVVbcY)

And some of the results look rather weird, but not unreasonably so. I'll let you be the judge of if these are "translated" correctly:
[https://mega.nz/#F!FDAHiY7Y!UiIu-N3SX_3yv29iNbdvpg](https://mega.nz/#F!FDAHiY7Y!UiIu-N3SX_3yv29iNbdvpg)
## Post #12
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-29T10:16:47+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Looks correct to me. It's a lookup texture for ramp shaders. The rest like gradient textures used for fx like this. [https://imgur.com/a/6URo6Ht](https://imgur.com/a/6URo6Ht)
## Post #13
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-29T16:02:06+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

They're supposed to look like that? Okay. Here would be other curiosities I would like to have off my chest.
First up are... health- and shield potions? I have completed this game multiple times and as far as I know there aren't any potions in it. Then again there seems to be some texture files associated with Crash Bandicoot (Krome's previous project) or maybe some concepts that never came to be. Anyway these don't look like quite right to me:
[https://mega.nz/#!lCg3RaBY!KobLQ_BsTaXi ... pwg_awvv28](https://mega.nz/#!lCg3RaBY!KobLQ_BsTaXizun6EZpGM7W32EEtLkH2Tpwg_awvv28)
[https://mega.nz/#!dGoBhYAZ!uwp0rl3d2TyO ... q_dRev_luM](https://mega.nz/#!dGoBhYAZ!uwp0rl3d2TyO7o3RziXZm--mUGU-8jnWqq_dRev_luM)

These are text on a checkerboard and just a number:
[https://mega.nz/#!BO4nXCxD!m_p68WimvzvX ... L3U2ihkO_g](https://mega.nz/#!BO4nXCxD!m_p68WimvzvXI5i8E5TtwmH40UGNA9vZhL3U2ihkO_g)
[https://mega.nz/#!4P4RHahQ!qP7pMwSU19KR ... 6mlUuBYuwg](https://mega.nz/#!4P4RHahQ!qP7pMwSU19KRndPXNW0JfjZwl1QnbeWRF6mlUuBYuwg)

Last one is a smoke texture, but the converted version is full of holes (I can see why this could be the case, but I would rather be sure it's not some translation error):
[https://mega.nz/#!MboHnaSB!G8m5_hPkUD77 ... Bv8YeGz7bU](https://mega.nz/#!MboHnaSB!G8m5_hPkUD77rJ4LxHaB8xKyecSRWp6N9Bv8YeGz7bU)
## Post #14
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-29T18:46:24+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

woulda been smart to zip them up. and they all seem correct. i dunno if and where those textures are used. the env cloud looks just like a cloud with some dustmotes in it. the potion textures contains 8 parts of an animated particle in the lower portion. in case they are not used they just forgot to remove them from the build. the smack block is definetely an editor or debug texture they probably forgot to remove too. and the number is just a number. what's wrong with that? seems all good to me. 

we done here?
## Post #15
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-30T09:58:23+00:00
- Post Title: Extracting .tex textures from the legend of spyro a new beginning (ps2)

All right. Thanks for checking those out for me.
After I have made my edits in .png format I will need to change them back to .tex format. Can the noesis script be somehow reverse engineered to handle such task or is there another way?
## Post #16
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-30T12:05:28+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

reimport with this method is not possible. to reimport the data gotta be extracted into palette tga images and they gotta be edited in indexed mode that allows the palette transparency. or they gotta convert back into indexed mode and keep the correct transparency across the palette. i'm unsure if the ps2 blending unit needs alpha 0x80 to work correct, but i'd assume so. and gimp for example doesn't do that. i could write the exporter in bms but i can't get valid data to pack back into it. i'm not gonna get photoshop to try this. I'm lost here.
## Post #17
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-08-30T13:38:19+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Well that's too bad. And yea pretty much all image editors are practically useless when it comes to this. I guess it's back to roaming the internet for a solution. Thanks for everything thus far, it has been very useful.
## Post #18
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-09-03T10:59:33+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Okay, I am back.
So I found this:
[viewtopic.php?t=17583](https://forum.xentax.com/viewtopic.php?t=17583)

What I can gather from the last post it seems like TjVatio managed to pull it off (convert edited data back into .tex). So I followed suit and downloaded all the programs mentioned, but I can't quite replicate the results. Here are the steps as I understood them:
1. Use Noesis to convert .tex to some editable format.
2. Use OPTPiX iMageStudio to convert the data into .tm2.
3. Use Console Texture Explorer to convert .tm2 to .tex.

The problem I am having is I can't get Console Texture Explorer to import anything into .tex, or to display anything sensible for that matter. I am aware that there is a connection between .tex and .tm2, am I doing something wrong there? I can't figure out the graphics offset nor the palette offset for example. OPTPiX .tm2 saving screen looks like this:



OPTPiX iMageStudio for PS2.png (40.69 KiB) Viewed 128 times
## Post #19
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-09-04T10:57:57+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

well. that's not gonna work. if you wanted to export valid data for reimport you's need the 8-bit and 4-bit indexed image type with 32-bit clut. i don't even know what the difference of CSM1 or CSM2 is. that means you'd need to convert to indexed before you export the tim2 and then still gotta create a script to generate the tex file header from the tim2 file. even more complicated then natively exporting to tex directly. ugh.
## Post #20
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-09-06T10:30:38+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

I've been experimenting with the "to reimport the data gotta be extracted into palette tga images and they gotta be edited in indexed mode that allows the palette transparency" with GIMP a little. And so far so good it seems. My .png edits translate flawlessly to .tga and GIMP applies the alpha of some kind by default. After that just index the image and save. What I don't get is how the actual reimportation is supposed to be done. I presume that if the reimportation is successful the noesis script should be able preview it.
## Post #21
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-09-14T08:49:31+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Is this thread done for?
How do you perform the actual reimportation after having the .tga images indexed?
## Post #22
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-09-14T17:08:40+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

well. is it? i was bored enough to try and into it enough to get something done.

it exports native indexed tga. supports all sample formats. i dunnno about rgba linear mem. it 'only' supports 24 bit palettes with 16 or 256 indices. the 16 color index had to be extended. gimp didn't wanna open nor saves anything else but 8-bit index. it will 'crunch' on reimport tho, if you have a image setup with 16 colors.

you can edit the path in the batch to whereever your quickbms is. the folder structure should not be changed for wip edits. it is drag and drop setup. to reimport you drag the original on the reimport batch file. it needs the original header for testing and will assemble the file from the edited folder and move the result into reimported. i'm not sure if it could batch. wasn't a priority to get tested.

nvm me editing. forgot to do the rgb images. kinda odd it needs the bgr swap for the tga display but not for reimporting. just reconstructing. 
[spyro_tex2tga_v3.rar](https://xentaxbackup.github.io/file/16748_spyro_tex2tga_v3.rar)
## Post #23
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-09-15T10:55:09+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Thanks for the edit. I couldn't get the v2 working no matter what I did, but v3 seems to be my friend.
Can this reimportation method somehow bypass or circumvent the measurements of the image. When attempting the reimportation guickbms states that the lengths don't match or something. Truth to be told the edit is quite a bit larger than the original .tex image. So can this deal with that or would the size difference make significant changes to the header thus making it incompatible?
It's fine even if I can't use larger images, I just thought it would be nice if it was feasible.
## Post #24
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-09-15T13:53:50+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

i could do that, but that would potentially breach the technical limitations of the hardware and render engine design and texture cache. think about that 4 MB of video memory. if you load a 4 times larger texture, it will reduce space for other textures and framebuffers. depending on vram usage and cache reloading mechanic it could break the renderer or slow down the system significantly. i know some games use a core vram footprint and layout. messing that up is not a good idea.

also i dunno how you plan to inject this into the ps2 disc in the first place. i dunno the data format of this game. i will not look into. not sure if the file system would allow the different size without breaking things.

either way. the safe solution is just to use the same resolution and formats.
## Post #25
- Username: Voxelated
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 27, 2019 1:45 am
- Post datetime: 2019-09-15T15:28:36+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

The plan would be to use this with pcsx2 (playstation 2 emulator), not on the original hardware. Now normally I would resort to a simple injector (such as texmod), but the upcoming release of pcsx2 will ditch the dx9 support completely and with no reliable dx11 injector in sight (resorep seems to be the only one and didn't work with the emulator) I thought I might as well try to mod the texture archive directly. Now technically I could use the current release of pcsx2 with texmod and it should work, but I'd much rather not to have to chooce with better emulation and improved visuals if that's possible.

Could the code of the emulator, game engine or whatever else get in the way? Yea, there's a more than a good chance something doesn't work as intended. When it comes to sheer computing performance I should be covered as well as a consumer can at the moment. This is the first time I attempt something like this so I will try to push the limits. If it goes beyond playability with this method, so be it, I just have to be more moderate with my edits. At the moment my largest assets are 6x the original. In the end nothing ventured nothing gained. Guess I would have to wait that some clever bloke puts together a working dx11 injector or to emulator to support it natively.

As for the data format if you mean where did I get the textures in the first place, the game uses Krome's .rkv archiving for all of it's assets. This a bms script should handle both ways, if I have understood correctly. So simply put I open the archive, edit what I need and restore the archive with the edits. Will it work then? That's what I am trying to find out.
## Post #26
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-09-15T15:41:31+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

you should forget about that injecting mod thing with this file hack. this will never work. neither is pcsx2 capable of extending the limit of the hardware. it's still just emulating 4MB of vram. it is pretty exact and timing sensitive program. moving bigger resources will potentially just slow it down or plain break it. you will not get bigger textures in there either way. so, your only chance is...

if the rkv script aloows reimport you could try that. the files gotta be the exact same size tho, for this to work. hence why, use the same resolution and formats
## Post #27
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-11-12T03:20:28+00:00
- Post Title: Re: Extracting .tex textures from the legend of spyro a new beginning (ps2)

Hi, you're amazing
