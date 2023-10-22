## Post #1
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-07-03T07:04:21+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

unpack help~



texture file: file-G1T
[http://www.mediafire.com/?ywfw7e4wu7a4k43](http://www.mediafire.com/?ywfw7e4wu7a4k43)


character modeling file: file-elixir(ez)
[http://www.mediafire.com/?7q6eb4ufuaq24em](http://www.mediafire.com/?7q6eb4ufuaq24em)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-03T07:58:23+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

here is just an unpacker for the game; thank you for the samples (despite being against the rules you brave soul). place atelier_unpack.exe and the zlib.dll files in the game's root directory and run. the program will scan the program directory and all subdirectories of it for GZ files. GZ is just a simple list of zlib streams. i only tested it on your samples and if it doesn't work on any GZ file, please PM it to me.

looks like they moved from PhyreEngine to the Dynasty Warriors engine. whoever does the models you can look at my previous one piece code or chrrox's dynasty warriors maxscript to pick up on this game if you so choose. you can also try loading the G1M and G1T files in noesis, maybe they might work as well. speaking of which, was anyone ever able to figure out the cloth for these Dynasty Warriors game? i remember once trying to reverse-engineer the HLSL shaders from the DW7 PC game but it was a major headache lol. i never want to look at D3D HLSL again .

thank you
[atelier_unpack.7z](https://xentaxbackup.github.io/file/6496_atelier_unpack.7z)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-03T08:19:28+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

by tomorrow i'll have the elixirs unpacked as well. do all elixir files start with EARC?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-03T09:04:56+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

updated second post with unpacker that also unpacks the .elixir files in the provided samples down to G1M, G1T, G1A, etc.

if anything doesn't work, PM me the file that doesn't work.

BTW, hi Runa, i seeeee youuuu hehehehehe.
## Post #5
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-07-04T05:54:45+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

Thanks,      ~~  


 By the way  ~ g1t.file unpack    ->  offzip?


offzip ? I do not know how to use
## Post #6
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-07-04T05:58:28+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

> Reply from howfie
>
> by tomorrow i'll have the elixirs unpacked as well. do all elixir files start with EARC?

yes~  all  EARC(gz) file
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-04T06:30:59+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

so, does it extract everything? i won't be able to get my hands on the game for another week or two.
## Post #8
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-04T10:26:03+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

it did work  thanks howfie,just got problem with the masking, 
and chrox script didn't really extract all the texture (some are missing though)

are you planning make a batch for these model ?
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-04T18:00:32+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

Maybe, I don't know. The fact that it's a Dynasty Warriors engine game means all those lovely skirts will be missing. There are these huge vertex buffer formats with multiple position semantics that even chrrox and Mr. Adults couldn't figure out what to do with them. And if they can't figure it out, I usually don't even bother trying.

Did you try Noesis too? I believe it had DW7 G1M and G1T export.
## Post #10
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-07-04T19:23:49+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

Your unpacking script works fine for the game.
Chrrox's script work somewhat. Well it doesn't convert some textures but it imports the model into max with skirts and everything but it has no UV map.
Also your one piece ripper converts all the textures perfectly but not the models.
So its just a matter of the UV map really
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-04T20:10:21+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

oh ok, then it shall be done (eventually hehehe). in the meantime, until my little japanese shop here can get the game, i will copy and paste my one piece texture code into the unpacker. also, can you send me maybe a dozen or so character model files so i can get started ?

thankies!
## Post #12
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-04T21:18:55+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

hmm weird,howfie one piece ripper exe didn't work for me,i already try with different computer but no result   
well,good luck howfie   

btw here is some sample


[http://www.mediafire.com/download/khz3d ... SAMPLE.zip](http://www.mediafire.com/download/khz3d65huzisbv4/Escha_SAMPLE.zip)
## Post #13
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-07-04T23:09:02+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

> Reply from howfie
>
> oh ok, then it shall be done (eventually hehehe). in the meantime, until my little japanese shop here can get the game, i will copy and paste my one piece texture code into the unpacker. also, can you send me maybe a dozen or so character model files so i can get started ?

thankies!






Please e-mail us ~ I'll send the file.
## Post #14
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-07-05T15:19:21+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

Ignore evrything I just said Howfie, your One Piece ripper converts the models too.
You have to change the version number tho in the file from G1M_0035 and G1MF0022 to G1M_0034 and G1MF0021 and it rips the model perfectly with a UV map so no need to make a completely new ripper xD
## Post #15
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-05T15:58:39+00:00
- Post Title: Escha & Logy Atelier (textur&model.file) unpack

> Reply from mikulover39
>
> Ignore evrything I just said Howfie, your One Piece ripper converts the models too.
You have to change the version number tho in the file from G1M_0035 and G1MF0022 to G1M_0034 and G1MF0021 and it rips the model perfectly with a UV map so no need to make a completely new ripper xD
 thank you so much,i will try  

i still dont get it,why one piece ripper.exe doesn't work,i put it in the same folder with g1m and g1t and it's said no files found in current directory or subdirectories
## Post #16
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-07-05T16:32:58+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

The ripper will make a folder called ONEPIECE you put the g1m files in there and run the ripper again and it should work
## Post #17
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-05T17:58:42+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

> Reply from mikulover39
>
> The ripper will make a folder called ONEPIECE you put the g1m files in there and run the ripper again and it should work
thank you so much
## Post #18
- Username: ativsp
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 16, 2012 5:48 pm
- Post datetime: 2013-07-06T16:47:42+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

> Reply from mikulover39
>
> Ignore evrything I just said Howfie, your One Piece ripper converts the models too.
You have to change the version number tho in the file from G1M_0035 and G1MF0022 to G1M_0034 and G1MF0021 and it rips the model perfectly with a UV map so no need to make a completely new ripper xD

I still need new ripper.
'cause I can't find how to change the version number.
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-06T21:46:59+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

one is coming, but i have switched from lightwave to blender so it might take a little time
## Post #20
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-07-07T11:13:46+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

> Reply from howfie
>
> oh ok, then it shall be done (eventually hehehe). in the meantime, until my little japanese shop here can get the game, i will copy and paste my one piece texture code into the unpacker. also, can you send me maybe a dozen or so character model files so i can get started ?

thankies!

g1t.file ~Conversion

Please tell us how to use
## Post #21
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-10T20:49:57+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

> Reply from ativsp
>
> I still need new ripper.
'cause I can't find how to change the version number.

You can always use HxD (Hex Editor) to do it. Just open the file the 2 numbers you need to change are in the first 2 lines ^^ Sorry if that didn't make much sense.
## Post #22
- Username: ativsp
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 16, 2012 5:48 pm
- Post datetime: 2013-07-14T08:03:02+00:00
- Post Title: Re: Escha & Logy Atelier (textur&model.file) unpack

> Reply from anime663
>
> 
You can always use HxD (Hex Editor) to do it. Just open the file the 2 numbers you need to change are in the first 2 lines ^^ Sorry if that didn't make much sense.

Thanks!
