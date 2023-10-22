## Post #1
- Username: sahawx2
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 23, 2011 8:54 pm
- Post datetime: 2016-06-22T01:59:05+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

i've been trying to retrieve models from the game using archive-based methods( ripping seems to be futile). i found the game uses dpk5 .dpk format to pack all its contents up and managed to unpack all of it. Textures are of dds format(having  "*png.texture" or "*.tga.texture" suffixes which should all be simply replaced by .dds). The final step which i still can't figure out is the model files. i thought they were simply just some modo lxo files but none of the softwares can recognise it as an lxo file. Sample is available here and can someone please give me a helping hand? thanks.

sample:[http://www.mediafire.com/download/j4rcr ... .lxo.model](http://www.mediafire.com/download/j4rcr15bza0pcyr/man_tgl.lxo.model)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-22T03:54:25+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

first submesh  



man_tgl_lxo_model.png (48.9 KiB) Viewed 166 times


go backward 8 bytes from each start address to see the face/UV/vertex count
## Post #3
- Username: sahawx2
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 23, 2011 8:54 pm
- Post datetime: 2016-06-22T07:00:28+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

> Reply from AceWell
>
> first submesh  
man_tgl_lxo_model.png
go backward 8 bytes from each start address to see the face/UV/vertex count
I got lost trying to figure out what progress can be made with this hex2obj. It's too complex for rookies like me. I need months to master this but I'm in urgent need for the model(s). As you said this is a file containing multiple submeshes, can you do me a favor to locate all of them? many thanks.

Or are there any scripts of Neosis or 3ds max for this format?
## Post #4
- Username: sahawx2
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 23, 2011 8:54 pm
- Post datetime: 2016-06-23T01:24:34+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

Can someone please help?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-23T04:51:19+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

> Reply from sahawx2
>
> I got lost trying to figure out what progress can be made with this hex2obj. It's too complex for rookies like me. I need months to master this but I'm in urgent need for the model(s).I've heard that "song" many times and I can't take it for serious, sry. (As you may know this is a research forum, not for leechers.)

Search for ".lxo" to find the vertex blocks of the submeshes -
then search for 000000000000000100000002 to get the start addresses of the face indices blocks.
## Post #6
- Username: sahawx2
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 23, 2011 8:54 pm
- Post datetime: 2016-06-23T05:38:09+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

On reading your posts of extracting models of other formats i have learnt your excellence on programming and hexadecimals while trying to find clues of correct usage of this expert execution. I understand you seem to be sick of hearing people excusing themselves for begging straightforward solutions because of the lack of knowledge. But it is indeed the truth that experts who can look into this extensively like you are scarce. different format of models needs differnt hexadecimal paths and formulae to be analysed which is too hardcore for wannabe-beginners like me and those who are still on thier way.
Yes, I know i just dumped speeches of illogical nonsense here. I'm sorry for acting like such a leecher. But i should say i'm actually trying to learn about this. But it still consumes considerable amount of time.

Anyway, I'm grateful that you have given a much more clear answer.

Edit:By some trials and failures, I finally managed to extract submeshes with proper UVs.
Thank you again, sincerely
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-23T16:18:14+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

> Reply from sahawx2
>
> Edit:By some trials and failures, I finally managed to extract submeshes with proper UVst-h-a-t i-s g-r-e-a-t!   
I'm really impressed. (I'll keep an eye on your progress.  )
## Post #8
- Username: sahawx2
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 23, 2011 8:54 pm
- Post datetime: 2016-06-24T01:58:16+00:00
- Post Title: CITYCONOMY Service for your City (*.lxo.model)

Nice to hear there are actually someone who are keeping their notice to this topic.
I extacted the complete drivable chassis of the man tgl truck yesterday, with all 12 submeshes.
Below are the pictures

> 

> 

Then I started extracting another model, man tgm, with 20 submeshes located in total, still in progress.

>
