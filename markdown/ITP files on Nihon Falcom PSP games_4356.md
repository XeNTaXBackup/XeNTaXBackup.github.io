## Post #1
- Username: DarthVaderXentax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 19, 2010 2:10 am
- Post datetime: 2010-04-20T07:46:04+00:00
- Post Title: ITP files on Nihon Falcom PSP games

Hi everybody,

I'm interested in viewing the picture files in the recent Nihon Falcom PSP games. I already searched for some informations regarding the format:

The sample itp files are in the itp.rar. These are from Sora no Kiseki 3rd.

I came across a japanese site who claimed to have decoded the files but I can't find the site any longer but I downloaded the ZIP there. This could be the decrypted files but I'm not sure of it. What concern me the most is the file size of white_itp.png. It's smaller than the original ITP!, anyways the "decoded" PNG files are in the png.rar

I'm not sure about that but I found clues about the ITP files that these are "deflate" compressed, so it seems I need some "inflate" decompressor but I could not find a generic decompressor, furthermore I do not know if the output files of these "decompression" are really PNG files or not.

So I ask for the help of someone who is more qualified in this matter. Hopefully someone will help me. I can't provide any links to a demo version because it's a PSP game and it seems the only executable file is the BOOT.BIN (it's a ELF file)
[samples.rar](https://xentaxbackup.github.io/file/2958_samples.rar)
## Post #2
- Username: DarthVaderXentax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 19, 2010 2:10 am
- Post datetime: 2010-04-21T13:14:34+00:00
- Post Title: ITP files on Nihon Falcom PSP games

> Reply from DarthVaderXentax
>
> Hi everybody,

I'm interested in viewing the picture files in the recent Nihon Falcom PSP games. I already searched for some informations regarding the format:

The sample itp files are in the itp.rar. These are from Sora no Kiseki 3rd.

I came across a japanese site who claimed to have decoded the files but I can't find the site any longer but I downloaded the ZIP there. This could be the decrypted files but I'm not sure of it. What concern me the most is the file size of white_itp.png. It's smaller than the original ITP!, anyways the "decoded" PNG files are in the png.rar

I'm not sure about that but I found clues about the ITP files that these are "deflate" compressed, so it seems I need some "inflate" decompressor but I could not find a generic decompressor, furthermore I do not know if the output files of these "decompression" are really PNG files or not.

So I ask for the help of someone who is more qualified in this matter. Hopefully someone will help me. I can't provide any links to a demo version because it's a PSP game and it seems the only executable file is the BOOT.BIN (it's a ELF file)

I found a solution: There is a converter for all kind of Nihon Falcom games, it's called Falcom データアーカイブ 変換ツール (Falcom data archive conversion tool) and can be found here: [http://www.geocities.jp/pokan_chan/](http://www.geocities.jp/pokan_chan/)

The funny thing is: You can't convert the ITP files directly, you have to choose the ISO files of the PSP games to output the converted ITP files!
