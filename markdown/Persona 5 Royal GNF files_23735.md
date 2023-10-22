## Post #1
- Username: Xnictax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 12, 2021 2:15 am
- Post datetime: 2021-04-11T18:24:31+00:00
- Post Title: Persona 5 Royal GNF files

I'm trying to modify some P5R GNF files but I'm stuck.

P5R stores its .gnf files in .bin files. A program called Amicitia can open the .bin files to export the .gnf files. It can also import the same .gnf files back. Noesis can open the extracted .gnf files and export it to many different file types. The part where I'm stuck is that once I've exported a .gnf file in Noesis to any other file type, I don't now how to revert that file back to .gnf. 

Does anybody know how to convert another file type to this .gnf file?

Here are samples of the files I'd like to edit: [https://www.mediafire.com/file/s0o3rj86 ... e.rar/file](https://www.mediafire.com/file/s0o3rj866vti7ne/P5R_GNF_file_sample.rar/file)
## Post #2
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2021-04-11T18:51:55+00:00
- Post Title: Persona 5 Royal GNF files

Here
[b004_400_00-Test.7z](https://xentaxbackup.github.io/file/19902_b004_400_00-Test.7z)
## Post #3
- Username: Xnictax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 12, 2021 2:15 am
- Post datetime: 2021-04-11T21:54:01+00:00
- Post Title: Persona 5 Royal GNF files

Yes it works perfectly. I can import the file without any errors and I can load it in the game. It shows with the letters 'TEST' above her head.

How did you manage to get it to work? I'm very impressed by the speed you were able to do this.
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-04-11T23:10:21+00:00
- Post Title: Persona 5 Royal GNF files

@Xnictax: gnf textures can be created either with PS4 SDK tools (like in case with Fallout 4 texture converter), or third-party implementations like [image2gnf](https://github.com/D3fau4/image2gnf). Also, I remember some Persona 5 mod tools exists, like [GFD-Studio](https://github.com/TGEnigma/GFD-Studio), but judging from Amicitia, you're already aware of it.
## Post #5
- Username: Xnictax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 12, 2021 2:15 am
- Post datetime: 2021-04-12T00:43:04+00:00
- Post Title: Persona 5 Royal GNF files

Yeah I'm using GFD-Studio as well but it can only read and export gnf files, not convert a .dds file to .gnf. Some of Persona 5 Royal's files are a bit different so not all Persona 5 tools work on it. P5R even has some files with the same extension that work P5 modding tools either can't open or save.

To get back to the gnf subject, I've tried to convert an exported .dds file back to .gnf with image2gnf. It doesn't give me a gnf file that's usable for P5R.
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-04-12T01:49:32+00:00
- Post Title: Persona 5 Royal GNF files

@Xnictax: Well, that image2gnf was just an example, I never used it by myself. Native tool from SDK is producing proper result though, just checked it with the sample above and Fallout 4 texture converter as GUI.
## Post #7
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2021-04-12T02:44:03+00:00
- Post Title: Persona 5 Royal GNF files

> Reply from Xnictax ↑Mon Apr 12, 2021 5:54 am at Mon Apr 12, 2021 5:54 am
>
> 
Yes it works perfectly. I can import the file without any errors and I can load it in the game. It shows with the letters 'TEST' above her head.

How did you manage to get it to work? I'm very impressed by the speed you were able to do this.

To create .gnf I used the tool  image2gnf
## Post #8
- Username: Xnictax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 12, 2021 2:15 am
- Post datetime: 2021-04-12T09:16:20+00:00
- Post Title: Persona 5 Royal GNF files

@Spiritovod After using image2gnf a bit more I just couldn't get P5R to accept created .gnf files. 

So I switched to Fallout 4 texture converter like you mentioned and that worked.

In a P5 modding community I was mostly told that there was no way to edit the .gnf files but you guys made it so simple. Thanks for all your help you guys really helped me out.
## Post #9
- Username: Ziemann
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 24, 2021 1:33 pm
- Post datetime: 2021-04-24T05:34:21+00:00
- Post Title: Persona 5 Royal GNF files

Thanks for sharing this! Next year I’m looking forward to working more on the menu and doing anything else that I can to streamline the modding process. I’m glad to see it worked out for you





[OneVanilla](https://www.onevanilla.run/)
## Post #10
- Username: forwarded
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 28, 2023 1:56 am
- Post datetime: 2023-06-30T03:10:47+00:00
- Post Title: Persona 5 Royal GNF files

> Reply from vadim ↑Mon Apr 12, 2021 10:44 am at Mon Apr 12, 2021 10:44 am
>
> 
Xnictax wrote: ↑Mon Apr 12, 2021 5:54 am
Yes it works perfectly. I can import the file without any errors and I can load it in the game. It shows with the letters 'TEST' above her head.

How did you manage to get it to work? I'm very impressed by the speed you were able to do this.


To create .gnf I used the tool  image2gnf

How do you use image2gnf? All I get is the command prompt popping out quickly then disappearing trying to start the exe file for it.
