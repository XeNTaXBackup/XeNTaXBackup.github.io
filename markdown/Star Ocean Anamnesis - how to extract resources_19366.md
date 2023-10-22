## Post #1
- Username: seiyria
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 22, 2019 1:40 pm
- Post datetime: 2019-01-22T06:15:55+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Hey! I'm new here and I've been browsing between here and zenhax, trying to cobble something together to extract all of the SOA assets. I have all of the files from SOA (the aif, asf, csf, etc files) and I have a handful of bms scripts, as well as SOADec and SOAImgEx. I should add, I'm not interested in the models, I'm just looking to extract all of the images (sprites, UI, portraits, etc).

What I've managed to do: 

- run SOADec on some directories, which gives me some _unpack files.
- run SOAImgEx on those files to get some files labeled in the format texX - resXxresY - ETC2-RGBA.dat (ex: tex1 - 512x128 - ETC2RGBA.dat)
- I also ran a script that I found which was slzxor on the above files which gave me _dec.dat files.

I've tried at every step to run the other slz scripts but I never got any results from it. I am not sure how the bms tool works, I just was trying out the scripts. I'll attach what I have. I have to omit the x86 folder from SOAImgEx which has libzstd.dll in it but that should be easy to find on google.

I've also tried a tool called Exeinfo PE to try to rip the image data out but to no avail.

Thanks in advance! I hope I've gotten somewhere with this, or that it will help someone else out. Any help getting the images out of this would be appreciated!
[SOA ex test.7z](https://xentaxbackup.github.io/file/15541_SOA ex test.7z)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-22T09:32:11+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Download the latest version of SOAImgEx : [http://www.mediafire.com/file/6126nmb4w ... SOATex.rar](http://www.mediafire.com/file/6126nmb4wmc5y6h/SOATex.rar) Drag and drop the ".aif" file on it and it will give you a ".ktx" file, which you can open with PVRTexTool or Mali Texture Compression tool.

Btw you could have asked this question here : [viewtopic.php?f=16&t=18692](http://forum.xentax.com/viewtopic.php?f=16&t=18692) No need to open a new thread for it.
## Post #3
- Username: seiyria
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 22, 2019 1:40 pm
- Post datetime: 2019-01-22T13:51:42+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Thank you! I wasn't sure what the policy on thread necros was so I figured I should play it safe and just make a new one with what I've tried. Also, thanks for the tips! Looks like this will finally work.
## Post #4
- Username: seiyria
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 22, 2019 1:40 pm
- Post datetime: 2019-01-23T14:54:51+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Hm. So, I've been able to extract pretty much everything I want. Now I want to write a script to do it all for me. My main problem, SOADec and SOAImgEx don't seem to have any CLI args that support input/output. If possible I would like to specify input/output and file names. Is this possible, or is it just something I'm going to have to work around?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-23T15:03:46+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

> Reply from seiyria
>
> SOADec and SOAImgEx don't seem to have any CLI args that support input/output.
First argument is input for both. Like this :

>SOAImgEx test.aif
>SOADec foldername

There is no argument for specifying the output name.
## Post #6
- Username: seiyria
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 22, 2019 1:40 pm
- Post datetime: 2019-01-23T15:34:22+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Cool, thank you! I also noticed some files don't seem to work with SOADec. Is there an updated version of that as well? For example, this one isn't working, but the other ones are.

Sorry, I'm probably going to have more questions but I hope that's not too bothersome. Just trying to figure them out as I go. Thanks for your help, it's really helping me make good progress!
[rare3.7z](https://xentaxbackup.github.io/file/15552_rare3.7z)
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-23T15:43:51+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Works fine for me. Make sure you download the latest version of every tool from the thread I linked above.
## Post #8
- Username: seiyria
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 22, 2019 1:40 pm
- Post datetime: 2019-01-25T18:56:42+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

Just wanted to say thanks. I finished and polished up my tool: [https://github.com/seiyria/soanamnesis-extract](https://github.com/seiyria/soanamnesis-extract)

Really happy with the result and wouldn't've got there without the help, thanks so much!
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-25T19:10:37+00:00
- Post Title: Star Ocean Anamnesis - how to extract resources?

> Reply from seiyria
>
> I finished and polished up my tool: https://github.com/seiyria/soanamnesis-extract
Nice guide and automation. I will include the link in my SOA thread. It should answer some of the questions people have been asking.
