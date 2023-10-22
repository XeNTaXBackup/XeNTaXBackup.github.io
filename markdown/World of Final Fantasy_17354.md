## Post #1
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2017-12-03T01:44:21+00:00
- Post Title: World of Final Fantasy

There are some bosses in the game that have called my attention and would be pretty interesting to see up close. Especially, the Einhander, being one of them. I looked upon the files myself. It's not that easy to spot what is useful. Folders contain extensions such as .tex, .mdl, .mdc, .msqp, .msi, .mpk, .msq, .csh, .crv.
I attempted TEXTOOL, Milkshape, no dice. It's also challenging that this PC port is fairly recent.
Any help would be appreciated.
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-03T02:45:58+00:00
- Post Title: World of Final Fantasy

> Reply from Adrot
>
> There are some bosses in the game that have called my attention and would be pretty interesting to see up close. Especially, the Einhander, being one of them. I looked upon the files myself. It's not that easy to spot what is useful. Folders contain extensions such as .tex, .mdl, .mdc, .msqp, .msi, .mpk, .msq, .csh, .crv.
I attempted TEXTOOL, Milkshape, no dice. It's also challenging that this PC port is fairly recent.
Any help would be appreciated.
If you need help upload a sample of each in order to progress, then wait, be patient and who knows, it may happen, those who know this stuff will take a look if they want to.

cheers
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-12-03T09:36:51+00:00
- Post Title: World of Final Fantasy

A user over at vg-resource has made a maxscript and other tools for this games models and textures.

I'm not entirely sure if its ok to share another forum, so someone let me know if not, but it feels a little disingenuous to post someones tools without them saying its ok.

[https://www.vg-resource.com/thread-2983 ... #pid640356](https://www.vg-resource.com/thread-29836-post-640356.html#pid640356)

The maxscript had an issue for environments that has been rectified here: [https://www.vg-resource.com/thread-2983 ... #pid640433](https://www.vg-resource.com/thread-29836-post-640433.html#pid640433)
## Post #4
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2017-12-03T19:06:16+00:00
- Post Title: World of Final Fantasy

Thanks for the response, the tools are interesting, however, I don't have a good compatibility with these (could be due to very outdated hardware), and RTB (who's also in this forum) missed making a tool for another vital extension. I'll post the samples, better safe than sorry.

.tex: [https://mega.nz/#!9TR1TQDQ!OlR5pjO5rd2M ... ozPDMsB07A](https://mega.nz/#!9TR1TQDQ!OlR5pjO5rd2MYg7hLfitK-vkJKvim64FyozPDMsB07A)
.mdl: [https://mega.nz/#!xXB2Rb4Z!IqU1RXwzECOG ... rrJ9p-BTTM](https://mega.nz/#!xXB2Rb4Z!IqU1RXwzECOGZ4Fzp6H1PAC3UAQQQPDFErrJ9p-BTTM)
.mdc: [https://mega.nz/#!UTZ0zQhJ!MRMERC_evyRb ... M0fYCIY0DI](https://mega.nz/#!UTZ0zQhJ!MRMERC_evyRbvFbnzdNVS4uzfpLAmCvxsM0fYCIY0DI)
.csh: [https://mega.nz/#!lKJkhCYR!F1qUqIw9Oh8w ... X-vrYKu9_I](https://mega.nz/#!lKJkhCYR!F1qUqIw9Oh8wF_uWkjK7w_kfu0ZVQMyMzX-vrYKu9_I)
.crv: [https://mega.nz/#!RK4liZQR!AUPmNcpW7rJE ... f8JVWd4l4Q](https://mega.nz/#!RK4liZQR!AUPmNcpW7rJEp0O8s4qMYy1vzSFGUNrkBf8JVWd4l4Q)
.msq: [https://mega.nz/#!dLJWlapL!mCUvXW8SdsE9 ... w_QjnELPio](https://mega.nz/#!dLJWlapL!mCUvXW8SdsE9v42MWiemW8LxUal2gV3Sdw_QjnELPio)
.msi: [https://mega.nz/#!VS4yDIbZ!5FpSZjWU4XW_ ... 1opM4yVtL0](https://mega.nz/#!VS4yDIbZ!5FpSZjWU4XW_3LWZDv5Nkm6HTFx9bvDNZ1opM4yVtL0)
.mpk: [https://mega.nz/#!USpDUAxD!J0GY5IKiZ6E7 ... jcx9b6yrLM](https://mega.nz/#!USpDUAxD!J0GY5IKiZ6E7tDillXb0XWtgZQYZxaD1xjcx9b6yrLM)
.msqp: [https://mega.nz/#!cbREDJLY!_ti3C0Fv0zky ... b6AQyLLPZw](https://mega.nz/#!cbREDJLY!_ti3C0Fv0zkyJ46eIZ1Ni9qM-J9Iij8rpb6AQyLLPZw)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-03T21:28:17+00:00
- Post Title: World of Final Fantasy

> Reply from Adrot
>
> .tex: https://mega.nz/#!9TR1TQDQ!OlR5pjO5rd2M ... ozPDMsB07A
this bms script will decompress and add dxt1 header to your one tex sample  

```

endian big
idstring "\0xet"
get NAME basename
string NAME + .dds
goto 0x80
get BILZ long
get SIZE long
get ZSIZE long
clog memory_file1 0x90 ZSIZE SIZE
endian little
get WIDTH short memory_file1
get HEIGHT short memory_file1
xmath SIZE "WIDTH * HEIGHT / 2" //DXT1
set memory_file2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\x00\x00\xBB\xBB\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr memory_file2 0XC HEIGHT short
putVarChr memory_file2 0x10 WIDTH short
log NAME 0 0x80 memory_file2 
append
log NAME 0xc SIZE memory_file1 //writing largest mip only

```

it would be good if you can upload more tex samples
## Post #6
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-04T18:00:41+00:00
- Post Title: World of Final Fantasy

I've already got a TEX conversion script (which was also in the thread linked to above), which works with everything I've tried it on -- DXT1, DXT5, RGBA32, BC7, cubemaps, etc.

[https://mega.nz/#!PxQHELRY!qqlxOcyeIuwo ... LDvr7VE8lA](https://mega.nz/#!PxQHELRY!qqlxOcyeIuwowuHcKmG29AgEKcpckriOYLDvr7VE8lA)

Also, which "vital" format are you referring to, Adrot? The MDC files? I'm still trying to figure those out.
## Post #7
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2017-12-04T19:54:28+00:00
- Post Title: World of Final Fantasy

> Reply from RandomTBush
>
> I've already got a TEX conversion script (which was also in the thread linked to above), which works with everything I've tried it on -- DXT1, DXT5, RGBA32, BC7, cubemaps, etc.

Hi, RTB, I guess I should explain my comment, sorry about that. First, I tried your tool. However, on any texture I try, I get this error: 
Not sure if it's your code or my PC, doesn't work on either paint.net or GIMP, and I have tried with many of the monster textures. It would really been nice if it could read them all. AceWell's script works, and I'm grateful, however, being in its early stages, it decompresses around 400 out of 900 or so tex files from the characters folder, and most have glitched results, so, I'm not sure what to decide next (As in, whose script to rely the most).
In addition, using your MaxScript on a model crashes the software, still not sure if it's because I'm on a no-GPU card PC, with Max 2009.

> Reply from RandomTBush
>
> Also, which "vital" format are you referring to, Adrot? The MDC files? I'm still trying to figure those out.

Yeah, that file you mentioned. I may have exaggerated a bit on its importance, but as long as it could help on the data, the better.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-04T20:50:46+00:00
- Post Title: World of Final Fantasy

> Reply from Adrot
>
> being in its early stages, it decompresses around 400 out of 900 or so tex files from the characters folder, and most have glitched results
because it currently only supports dxt1, you need to upload more samples so i can expand functionality.   


> Reply from RandomTBush
>
> I've already got a TEX conversion script (which was also in the thread linked to above), which works with everything I've tried it on -- DXT1, DXT5, RGBA32, BC7, cubemaps, etc.
ah cool, i didn't even check that link, just grabbed the sample and ran with it, i'd still like more
tex samples though so i can make a Noesis python script to decompress and open on the fly.
## Post #9
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2017-12-04T22:22:12+00:00
- Post Title: World of Final Fantasy

Well, not sure what to say, but I like your determination, AceWell. While I still have to find the Einhander, here is a folder with 8 other samples that are mostly noteworthy.
[https://mega.nz/#F!VLASiRoT!sKl-4GVNauP8tlnjvtq4sQ](https://mega.nz/#F!VLASiRoT!sKl-4GVNauP8tlnjvtq4sQ) 
Truly, a multiple file converter would be most welcomed here. I would also add that the tex format covers not only 3d models, however, I'm not sure where if I can also discuss about that as well.
## Post #10
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-12-04T22:45:32+00:00
- Post Title: World of Final Fantasy

> Reply from Adrot
>
> Not sure if it's your code or my PC, doesn't work on either paint.net or GIMP, and I have tried with many of the monster textures.
Definitely your PC/programs or you're not using the tools correctly. I've used RTB's tools to play around with several models, edited textures in gimp and converted them from dds to png without issue in addition to applying to the models correctly. 

From your description it sounds like you didn't run the file decompressor on the files before loading/converting. I made that mistake at first and tried loading a mdl file in Max without running the decompressor first. It hung Max and I had to restart it. Once the decompressor had been used, the mdl loaded very quickly unless it was a larger model file (like 7MB and up in size) but was still fairly quick. 

Try running the decompressor script on the mdl file BEFORE loading it in 3DSMax. Same with the textures. Run the file decompressor and then the tex to dds convertor. It's a bit of work to do all that but it does work.
## Post #11
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-04T22:58:39+00:00
- Post Title: World of Final Fantasy

> Reply from ssringo
>
> I made that mistake at first and tried loading a mdl file in Max without running the decompressor first. It hung Max and I had to restart it. Once the decompressor had been used, the mdl loaded very quickly unless it was a larger model file (like 7MB and up in size) but was still fairly quick.Huh, that's odd, I was pretty sure I made my script check for whether it was compressed or not before importing (basically, checking for "BILZ" at offset 0x80 before attempting an import). Guess that must've happened before I had 3DS Max crash on me and I'd forgotten to save, so I'll be sure to implement that again in the next update (as well as MDC support, since that stores texture names and such).

But yeah, as ssringo said, check to make sure it's decompressed first. Either way I'll see what I can do about editing said script soon to work with either compressed or decompressed files.
## Post #12
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-05T02:46:30+00:00
- Post Title: World of Final Fantasy

Welp, turns out I'd also forgotten to add support for multiple UV mapping layers, too, so here's an update to the model-importing script that fixes both that and the issue above.
[https://mega.nz/#!fkwXlZYC!MywRK_sKlJrK ... zIKBO5bzik](https://mega.nz/#!fkwXlZYC!MywRK_sKlJrKAx-pTvrrNLmObxxAaMGl7zIKBO5bzik)
## Post #13
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2017-12-05T21:29:16+00:00
- Post Title: World of Final Fantasy

First off, thank you guys for explaining the decompressor, I was wondering what format was that script working. The models finally work on the 3DS Max. However, I still can't get the tex files to work with RTB's TEX script. I just do what I do with AceWell's script and other ones as well. Drag the script to QuickBMS. Select the tex file. Select the output folder. Drag the .dds file to paint.NET. Error. I'm not sure if it needs something else my PC can't give, but it doesn't make sense to me that one script that has little research works and the other one which could have more completion does not.
## Post #14
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-07T15:15:09+00:00
- Post Title: World of Final Fantasy

[https://mega.nz/#!PxQHELRY!qqlxOcyeIuwo ... LDvr7VE8lA](https://mega.nz/#!PxQHELRY!qqlxOcyeIuwowuHcKmG29AgEKcpckriOYLDvr7VE8lA)

I've updated the TEX-to-DDS converter script so now it works with either compressed or decompressed files instead of just the latter -- the result will be the same regardless. And if you're still finding textures that don't load properly, try using Noesis to convert them to PNG, as they're most likely the BC7 format I mentioned earlier which some programs can't open since it's a newer compression.
