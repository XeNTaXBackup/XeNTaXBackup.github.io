## Post #1
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-07-15T23:21:02+00:00
- Post Title: SOA graphic assets

Hello there,

I'm trying to figure out how to read the image encoding used for Star Ocean Anamnesis graphic assets. I found out that it's a variant of ETC2 RGBA but I can't seem to display it properly with PVRTexTool.

Could I get some input on how to improve the rendering or how to determine the exact compression used? Thanks in advance!

A small sample is included in this post.
[sample2_unreadable.zip](https://xentaxbackup.github.io/file/14655_sample2_unreadable.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-07-22T07:52:06+00:00
- Post Title: SOA graphic assets

it is difficult to get accurate results from only one sample. what did your results look like?
i am not familiar with the graphics of this game, does this look correct to you?  



sample1.png (133.1 KiB) Viewed 342 times


i entered 512 wide by 1024 tall with ETC2 rgba and header size 768 bytes in PVRTextool to get that.
i scaled it down by 50 percent so it will fit in the attachment, 
it looks like some shuffling or something is needed to me to remove the scanlines.
## Post #3
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-07-22T08:25:58+00:00
- Post Title: SOA graphic assets

Hello Ace,

Thanks for offering your help again 
And yes, it does look good. That's the result I was able to get but I'm unable to remove the scanlines. I'm able to get all images after figuring out their size, but the scanlines are present in all of them.

How would one go about removing them?

I've included one more samples in case it can be of help to you.
[sample2.zip](https://xentaxbackup.github.io/file/14641_sample2.zip)
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-23T11:09:54+00:00
- Post Title: SOA graphic assets

Those scanline artifacts seem to be because of the decryption. I think the bms script for the slz files isn't perfect yet.

You need to xor every 5th byte of 8 byte iterations, with 0x20. I mean like read 4 bytes, xor the 5th with 0x20, and read 3 bytes. It seems to produce the correct result.



soa_test.png (232.67 KiB) Viewed 320 times



Edit :
@Sorans Can you post or pm me the unpacked version of the first image too? I mean the file before running the bms script on it.
## Post #5
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-07-23T13:15:58+00:00
- Post Title: SOA graphic assets

Hello akderebur, thanks for your help!

Here's the original file you requested (for the image above)

You're also right about the SLZ script, it's not 100% finished and also cannot read some ADLD types according to what aluigi told me. I will replace the sample in my first post with the unreadable type.

EDIT: Would it be viable to edit the SLZ script to do what you said above, instead of XORing the file afterwards? (I'm not very familiar with the syntax yet)
[sample.zip](https://xentaxbackup.github.io/file/14654_sample.zip)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-23T14:44:15+00:00
- Post Title: SOA graphic assets

> Reply from Sorans
>
> 
EDIT: Would it be viable to edit the SLZ script to do what you said above, instead of XORing the file afterwards? (I'm not very familiar with the syntax yet)
I am not very familiar with bms myself, but the attached script should do the trick. It xors the file before saving.
[slz_bms.rar](https://xentaxbackup.github.io/file/14656_slz_bms.rar)
## Post #7
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-07-23T14:50:01+00:00
- Post Title: SOA graphic assets

Thanks for your help!

Now that the old SLZ format can be decrypted correctly, I'll try looking into how to unpack the unknown type I mentioned above.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-25T14:51:31+00:00
- Post Title: SOA graphic assets

> Reply from Sorans
>
> 
Now that the old SLZ format can be decrypted correctly, I'll try looking into how to unpack the unknown type I mentioned above.
I am not sure if it will help at all with unpacking. The part I added xors the file after unpacking, so you still need to figure out the compression first.

Also I have noticed that Tri-Ace is changing more of the slz archives to type 7. Some model files that weren't type 7 before are now type 7. Mostly the character models. I hope someone can figure this out.
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-11T19:22:07+00:00
- Post Title: SOA graphic assets

Btw type 7 can be unpacked now. I have mostly used it for models, but might be useful for some texture files too. Check out this thread : [http://zenhax.com/viewtopic.php?f=9&t=7149](http://zenhax.com/viewtopic.php?f=9&t=7149)
## Post #10
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-08-11T19:25:12+00:00
- Post Title: SOA graphic assets

That's going to be very useful. Thanks for relaying the info here
## Post #11
- Username: Sorans
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-12T18:28:44+00:00
- Post Title: SOA graphic assets

Image Type 0x2F - ETC2-RGB
Image Type 0x31 - ETC2-RGBA
Image Type 0x32 - EAC-RG11
## Post #12
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-08-12T19:50:34+00:00
- Post Title: SOA graphic assets

That's in line with what I've found.

The only remaining thorn is that some of the encrypted files use different keys (different than even the one you helped me with on the other forum)
I've been trying to tweak the xor script to support those types too, without much success. (I've updated my post on the other forum)
