## Post #1
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-08T05:06:22+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-13T22:24:43+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

Hi,

Just an update, I have discovered a CRC checksum (see yellow in pic) in the SPK file. Green is the file size (4 bytes x2). Am unsure of what the 4 pink bytes are representing.

[](http://img690.imageshack.us/i/checksumq.jpg/)

I have uploaded the file '096.MDL', available [here](http://rapidshare.com/files/418896815/096.rar). If someone could please take a look at this and try to figure out what the 4 pink bytes are representing that would be much appreciated.

Thanks,
Robert
## Post #3
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-13T23:28:42+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

Some more files to help with the possible checksum - [QFG5_mdl_095_100.rar](http://rapidshare.com/files/418903879/QFG5_mdl_095_100.rar)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-14T02:04:53+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

the spk file looks like a zip format, though i dont understand the pointer values - like the central directory pointer - which is wrong. finding the actual pointer can be done searching for the first instance of 504b0103 (PK\x01\x03)

the central directory record varies in size due to the filenames, but the first record shows the unknown checksum is 0. next record shows 20723, which is only slightly larger than the size (?) - of 20644.

so from a glance, it looks like the value is the sum of all the uncompressed data size so far. so changing "mdl/095.MDL" (record #1621) would effect the other (few!) header values.

hope this can help.
## Post #5
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-14T03:54:31+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

> Reply from WRS
>
> the spk file looks like a zip format, though i dont understand the pointer values - like the central directory pointer - which is wrong. finding the actual pointer can be done searching for the first instance of 504b0103 (PK\x01\x03)

the central directory record varies in size due to the filenames, but the first record shows the unknown checksum is 0. next record shows 20723, which is only slightly larger than the size (?) - of 20644.

so from a glance, it looks like the value is the sum of all the uncompressed data size so far. so changing "mdl/095.MDL" (record #1621) would effect the other (few!) header values.

hope this can help.

Hey,

Thanks for the help with this. It looks like you are correct with those values being the total file size, have checked this a few times and it seems to sum up.

Any ideas on the 4 pink bytes I have highlighted on the first screen?

Also, heres what the files in the header look like (example is 096.MDL):
[](http://img842.imageshack.us/i/header096mdl.jpg/)

Thanks,
Robert
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-14T14:34:30+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

as with the zip format, those values are the last modified time:

```
DOSDATE HDate; // 16-bit

```


ex: mdl/096.MDL was last modified 05/23/1998 at 11:36:36
## Post #7
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-14T22:40:35+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

> Reply from WRS
>
> as with the zip format, those values are the last modified time:
Code: Select allDOSTIME HTime; // 16-bit
DOSDATE HDate; // 16-bit


ex: mdl/096.MDL was last modified 05/23/1998 at 11:36:36

Awesome work dude. Would you be willing to write a plugin to create and modify these archives for a small fee? Otherwise might have to bug Watto again to upgrade his plugin, heh.
## Post #8
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-10-02T21:30:28+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

Bump. Looking for someone to write a plugin to create and modify these archives for a fee.
## Post #9
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-11-03T09:22:04+00:00
- Post Title: [Request] Quest for Glory 5 (SPK)

The contents of this post was deleted because of possible forum rules violation.
