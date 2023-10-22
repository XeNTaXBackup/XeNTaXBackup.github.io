## Post #1
- Username: Artnej
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 16, 2018 2:51 am
- Post datetime: 2018-11-05T22:06:20+00:00
- Post Title: XBN format (from XSI)

Hello,

i'm looking for some help with .xbn format. 
I know that the files were created by SOFTIMAGE XSI 4.2  but unfortunately I can't open them with it.

Do you know any easy way to edit this file?
I tried converters, different versions of the program but nothing.
One of them is a 3d Object Converter but I also get a message of unknown format. (Archangel got .xbn (same studio were creators)).

Meh! I am counting on any help, thank you in advance 

Kind regards.

PS i attached the file
[model.rar](https://xentaxbackup.github.io/file/15135_model.rar)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-05T22:40:19+00:00
- Post Title: XBN format (from XSI)

Looks like an easy format. Vertex and face count in the beginning of the file. Here using hex2obj :
## Post #3
- Username: Artnej
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 16, 2018 2:51 am
- Post datetime: 2018-11-05T22:58:27+00:00
- Post Title: XBN format (from XSI)

Yeah, you're great!

Is there any other option to open format like this?
Or just the one right way is to learn h2o?

BR
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-05T23:30:07+00:00
- Post Title: XBN format (from XSI)

It would be easy to write a program for it. The question is : does anyone want to do it? 

You can use hex2obj or similar tools until someone codes something for this format. You also gain experience that you can apply in future formats, so it is never a waste of time imo. Maybe write your own program in the end.
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-11-06T17:04:35+00:00
- Post Title: XBN format (from XSI)

> Reply from Artnej
>
> Hello,

i'm looking for some help with .xbn format.

The model.rar file has the ~PM_Numerek_01-382.xsi file. Why are you talking about the .xbn format?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-06T18:52:07+00:00
- Post Title: XBN format (from XSI)

> Reply from Artnej
>
> Is there any other option to open format like this?
Or just the one right way is to learn h2o?It's not a matter of learning h2o, it's a matter of understanding formats.

This format is simple as akderebur stated, and if you know 'C' you could pick up the make_obj project (with source) in the tutorials thread.
You get the startaddresses (except the first one) very easy by adding vertexcount*datasize, i.e.
startofuvs = 0x19 +528x32 (dec.), datasize (fvf) = 32
startoffaceindices =0x4219 + 528x8 (dec.), datasize (uvs) = 8
