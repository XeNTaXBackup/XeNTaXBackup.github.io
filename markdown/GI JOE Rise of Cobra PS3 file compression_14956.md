## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-28T02:17:48+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Hey guys, hoping someone can take a look at this file format for me... I'm certain I've managed to find where the models themselves are, but I'm at a loss as to what sort of compression method's been used here. Anyone care to take a look? Snake-Eyes sample attached (I'm pretty sure): 

[SAMPLE](https://mega.nz/#!zFIAyDiA!CLQ4q2Z4oHk55_M578WFv8d9rY3WD35wUeTxDyAb6A0)
## Post #2
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-30T07:43:22+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Just giving this a bump -- hopefully someone might be able to help! Luxox managed to get the model and textures out pretty quickly this afternoon, but doesn't know enough about bones/rigging to know what else is in there... any chance anyone else can take a look? Here's how one of the Scarlett's came up!



scarlett.jpg (50.71 KiB) Viewed 213 times


[Here is a link to her files...](https://mega.nz/#!GBpTTJjR!bg8xmY4mpBZLVZwDwg4vE-a0ACLp2uWmp5S-S3hK_3I)
And one other possibly related file I'm unsure of... [something with the extension ".gbr_9_be"](https://mega.nz/#!eEhXmBrQ!9v-59SQRGqPxSYHPLPC1iqtgT3bbIb4ukb4RfmUtFfs).
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-30T12:24:58+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Both the provided files in the main post aren't compressed, SNAKEEYESCMDO.LVL_740 looks like a 3D model file.

Topic has been moved and your newer one is locked.

Cheers.
## Post #4
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-30T15:29:18+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Sorry about that! Surely it'd be some form of compression though, considering the textures and model were all contained in significantly smaller files than what Luxox sent me...

Anyway, if anyone could take a look and see whether or not there's a way to look at these in NOESIS, I (and I know a few other people) would be tremendously appreciative of it!
## Post #5
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-08-31T22:56:54+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Someone please help figure this out! I would love to have Snake Eyes myself.
## Post #6
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-09-01T11:43:08+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

SCARLETTCLASSIC.LVL_740 is definate Archive!
you see a list of files on 1640.

eg: 
ShinySX3TextureStreamEntryTables
\joe\textures\actors\characters\common\nanite_mask.tfo
\joe\materials\actors\weapons\w_scarlet_crossbow\scarlett_weapon02.lmt

tfo is dds file no header
I think lmt is model

But I am a beginner
that what I found now.
[Cobra.jpg](https://xentaxbackup.github.io/file/11645_Cobra.jpg)
## Post #7
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-01T12:05:05+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

I have no idea what any of that means, but it LOOKS like progress! Cheers Shine!! Fingers crossed you can make something out of it!
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-01T23:05:58+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Yes *.LVL_740 is uncompressed archives (like Gh0stBlade said) with several file types 
where you can hand pick the data but it would be better to make a bms script to split
it into the separate files to get many of these files quickly from the game's assets.
the main table starts at 0x80 and it looks like there might be more tables with each of those.

the tfo sections have texture data with brief headers but there is also dxt info for each 
texture stored in another place in the archive.

here is a generic tfo texture splitter bms script and a Noesis python script to open those split textures  


 GIJoeRoC_PS3_tfo_scripts.zip
(1.2 KiB) Downloaded 25 times


after you use the bms script just copy out the tfo files from each folder created
and put them in just one folder and use Noesis to open them
## Post #9
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-02T02:58:42+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Nice! Hopefully now we can get the models and rigs exportable! Thanks Ace!
## Post #10
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-09-02T11:33:26+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

With the help from my friend, I can extract the files correct.


 GIJoe_ROC.rar
extract bms (864 Bytes) Downloaded 33 times



here the model form ActorModel_scarletclassic__{C6397402-E1EA-457B-93E8-E5B8A09F52A7}
but I cannot make it right?
no uv, not float value?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-02T12:58:50+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

uvs are not in the FVF block - search for the first 000000FF after the vertex block; behind it the uv block starts:
(other model of Scarlett):



Scarlett_hi_dcn.jpg (221.65 KiB) Viewed 129 times



btw: your friend is world famous Fatduck?
## Post #12
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-09-02T13:13:54+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

Cool model !
Did Animation planned ?
## Post #13
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-09-03T10:05:46+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

shakotay2, help please.

I load ActorModel_scarletclassic__{C6397402-E1EA-457B-93E8-E5B8A09F52A7}

the verts look correct, but face not!
I search for vert block start 7a04c and end to first 000000ff uv block, 5994 verts


face from 6e040 - 7a04c , press go1 button get 3457 vert only?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-03T11:07:29+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

I don't have that model but it looks like this formats uses relative face indices (FIs) for its submeshes (SMs).

So you'll have to find out where the face indices for the next SM start (0x68BF4, other model!).
Then you need to calculate the vertices start address for the next submesh:



ActorModel_scarlet_hi.dcn__{053404DB-C6C8-41FE-B197-7BDA4724AF28}.jpg (238.77 KiB) Viewed 89 times



There's a support for relative FIs in Ride, but it's not for floats.
hex2obj is a helper tool for simple models or for quickly getting the first SM of more complex ones.

If you need more then you're suggested to solve it programmatically (maxscript, Noesis or plain C).

Using plain C (in CodeBlocks/MinGW for example) is the most simple approach imho but my Make_H2O project
 is not very popular. (Maybe I'll "evolve" it to a Make_obj project some day but for many people coding in "C"
seems to be a big hurdle.)
## Post #15
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-03T13:24:09+00:00
- Post Title: GI JOE: Rise of Cobra PS3 file compression?

If either of you guys need access to any more of the files, just shout and I'll hook you up!
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-09-03T18:14:50+00:00
- Post Title: Re: GI JOE: Rise of Cobra PS3 file compression?

For those who ineterested bones are in ShinyPatchModelHeaders files, weights and bone indices are lowest section of data in model file (4 bytes for bone indices and 4 bytes for weights )
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-08T13:41:39+00:00
- Post Title: Re: GI JOE: Rise of Cobra PS3 file compression?

> Reply from Shine
>
> With the help from my friend, I can extract the files correct.
The attachment GIJoe_ROC.rar is no longer available

i have updated the tfo Noesis python script to open the textures extracted
by fatduck's bms scripts in this post [viewtopic.php?p=122179#p122179](http://forum.xentax.com/viewtopic.php?p=122179#p122179) 


 tex_GIJoeRiseofCobra_tfo.zip
(819 Bytes) Downloaded 21 times



supports dxt1, dxt5 and what might be dxt3
