## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2016-01-29T15:16:07+00:00
- Post Title: Games with hidden file tables?

Various PS2 games, such as Ratchet and Clank, and Sly Cooper (besides the third) have an oddity that makes it so no data files show up, and only the SYSTEM.CNF and SCUS files do. Has there ever been a fix for this?
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2016-02-03T16:32:17+00:00
- Post Title: Games with hidden file tables?

There can't be a general fix, those ghost TOC (Table of Content) are custom made. I made a tool to extract stuff from Kingdom Hearts <something> ISO but it will never work for another game, as the algo used for it is specific for the logic used to create that image.
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2016-02-03T22:58:31+00:00
- Post Title: Games with hidden file tables?

I assumed it'd be different for each game, but how did you manage to do it? I'm assuming you ran it through a debugger or something? And have you ever considered looking at the first Sly game, and possibly making your Kingdom Hearts tool work with it? If not, i can understand since, well, they are on different engines and are probably implemented entirely different.
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2016-02-04T09:06:29+00:00
- Post Title: Games with hidden file tables?

I actually just looked at the iso sectors in an hex editor, found the TOC with pointers, filesizes and filenames and wrote a tool that work with the ISO. It's very very basic

```
#include <stdio.h>
#include <windows.h>

BYTE buffer[2048];

int main(int argc, char *argv[])
{
    FILE *iso,*ext;
    long long unsigned int pointer;
    unsigned long int i,c,times,len,off=0x00;
    unsigned char name[16];

    if (argc < 2) printf("Kingdom Hearts Chain Of Memories Hidden Files Extractor by Vash v0.9 -www.romhacking.it-\n\nisoext file.iso\n\n");
      else{
      iso=fopen64(argv[1],"r+b");
      mkdir("ISO");
      chdir("ISO");
      for (i=0;i<144;i++)
      {
          fseek(iso,0x122800+off,SEEK_SET);
          fread(name,16,1,iso);
          ext=fopen(name,"w+b");
          fread(&pointer,4,1,iso);
          pointer=pointer*0x800;
          fread(&len,4,1,iso);
          len=len*0x800;
          fseeko64(iso,pointer,SEEK_SET);
          times=len/0x800;
          printf("Extracting %s\n",name);
          for (c=0;c<times;c++)
          {
            fread(buffer,0x800,1,iso);
            fwrite(buffer,0x800,1,ext);
            }
      fclose(ext);
      off=off+0x20;
      }
      
      }
      }

```
## Post #5
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2016-02-04T09:27:19+00:00
- Post Title: Games with hidden file tables?

Wow! that was unexpected. Though is there any way you could upload a compiled EXE? and also, do you know if it would be possible to reimport a modified version of the game archive the game uses using this?
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2016-02-04T09:36:44+00:00
- Post Title: Games with hidden file tables?

Sure, here you are, attached.

With this, you can only extract the files and that's it, it was more of a POC than a will to work on this specific game.

I included some other tools I made for the game (extract dat files and dump text from bin/ctd files) but don't ask to keep on working on them, I don't have time anymore
[kh_com_ps2_tools.rar](https://xentaxbackup.github.io/file/10420_kh_com_ps2_tools.rar)
## Post #7
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2016-02-04T09:39:28+00:00
- Post Title: Games with hidden file tables?

Regardless. Thank you very much, though it came off as a surprise that it was a fairly simple thing. Thanks for taking the time to do this!
## Post #8
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2016-02-04T15:02:17+00:00
- Post Title: Games with hidden file tables?

Strange. I tried it on my ISO, and it gave me 28 files, totaling 24.8 GB before I stopped it from making any more big files. I wonder why? I'm assuming it's either my ISO is a bit different than yours (mine is the original, black label edition and not the Greatest Hits version, though I doubt it's any different in any way) or I used it improperly. I dragged the ISO file to the isoextr.exe file if that's how you're supposed to do it. But it isn't out of the question for the files to be that big since somebody got a Ratchet & Clank demo WAD to extract, and it had totaled around 10 GB.
## Post #9
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2016-02-04T16:35:57+00:00
- Post Title: Games with hidden file tables?

well, this tool was very specific for the ISO I owned at the time (don't really remember which one). In this particular case the ghost TOC starts at 0x122800 (sector 0x245), you should either adjust the code or the ISO. That's if the exe file (the slus) has the same size and the logic behind the ghost TOC is the same.

Oh and I never tried drag&droppin files onto my tools, you should just write a batch file

isoext file.iso
pause
## Post #10
- Username: fileGates71
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 23, 2019 3:12 am
- Post datetime: 2019-04-13T01:21:22+00:00
- Post Title: Games with hidden file tables?

Hello, all. I am looking into ripping the voices and music from the Sly Cooper series. So far, I can't get the hidden files to show up. I have tried using whatever tools are here, but at best, I extract oddly named files without filenames. And looking at them in a hex editor doesn't help. Is there a method to show the hidden files with the tools, or is there a more recent, streamlined method?
## Post #11
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-08-11T02:40:42+00:00
- Post Title: Games with hidden file tables?

could you do the ps2 sly games
## Post #12
- Username: koken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 23, 2020 7:41 am
- Post datetime: 2020-10-22T23:48:42+00:00
- Post Title: Games with hidden file tables?

> Reply from Vash ↑Thu Feb 04, 2016 5:36 pm at Thu Feb 04, 2016 5:36 pm
>
> 
Sure, here you are, attached.

With this, you can only extract the files and that's it, it was more of a POC than a will to work on this specific game.

I included some other tools I made for the game (extract dat files and dump text from bin/ctd files) but don't ask to keep on working on them, I don't have time anymore

Hi!

Thanks for this! (a few years later haha). Is there any way to reduce the size of the .iso of this game? I've reduced the size of lots of them but this one is different from the others and it's really heavy! 

Thanks
