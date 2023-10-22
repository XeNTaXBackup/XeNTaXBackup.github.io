## Post #1
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-19T14:34:38+00:00
- Post Title: Recettear compression

Alright, this one's driving me nuts, and it's "only" compressed text.
The game stores all data that isn't music/sound/models in one large file (which is, for some reason, split into 12 smaller files)
There is a file called lnkdatas.bin which contains the whole folder/file structure, using it I was able to isolate specific files, but I'm having a hard time decompressing them (mostly because, well, I have no clue about compression)

I've attached a file which is called enemylist.txt by the game and I'm assuming it only contains text when decompressed. (I'll be using ? for any bytes that don't translate into alphanumerical characters.)

The first enemy in that list is the Wisp, which seems to be called "wisp1" in the file, alright so far. That  enemy drops the items Natural Heater and Salamander Scale and maybe other things.

At offset 0x52, you see the string "Natur?al He??er" which obviously, when decompressed, is Natural Heater. The first thing I don't get is why Natur and al are even split up (by 0x04). The ?? in Heater is probably the compression at work (..replacing two bytes by two other bytes, but there are also cases where three or more bytes are reduced to 2, so whatever)

The really confusing thing is at 0x6A. The string says "S??am?and?? Sc???e" and with a bit of imagination, that's Salamander Scale.
Taking a look at the first ?? (in "S??am"), they are represented by 0x0112 (Big Endian) and should be "al" deconverted. However, the second ?? (in "and??"), which should be "er", is ALSO represented by 0x0112
The only explanation is that the single ? (represented by 0x08) does something funky, but what and how?

My guess is that the first entry would look something like this after decompression:

```
1: <some item name?>
2: <some item name?>
3:Natural Heater
4: <some item name?>
5:Salamander Scale
```


There's absolutely no trace of what the first/second/4th item could be, would that mean there's a large dictionary somewhere?

Another strange thing is that there are sometimes ASCII-character thrown in where there shouldn't be any, like the string "WorTn" that appears at 0xAC, which is "Worn Sword". Any ideas how the game could know that this T must be interpreted as something else?

So yeah, a bit of a lengthy post. If you have any idea what this compression (or even encryption?) algorithm could be or saw something similar somewhere else, do tell.

Edit: Uploaded the proper enemylist.txt
[enemylist.rar](https://xentaxbackup.github.io/file/3458_enemylist.rar)
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-19T16:52:23+00:00
- Post Title: Recettear compression

it looks like standrd LZS. I'll do some tests

ok, it's defintely LZS but not standard (ah and your unpacker is bugged )
## Post #3
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-19T17:16:11+00:00
- Post Title: Recettear compression

Thanks a lot, at least now I have something to go on.

And what do you mean, bugged? I'm fairly sure the file came out alright (although I didn't write any tools yet and got it out manually)
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-19T17:20:19+00:00
- Post Title: Recettear compression

nope, you were missing a byte at the beginning. Anyway I'm writing an unpacker. I'll use it to study the compression better
## Post #5
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-19T17:37:47+00:00
- Post Title: Recettear compression

Err, you're right, actually <_<
The byte at the beginning is 0 and there's one less byte at the end (making the overall size the same).
What does the initial byte say anyway? Even bmps have one before the magic number.
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-19T17:56:58+00:00
- Post Title: Recettear compression

every file has it. It's a flag for the compression. I'm studying the algo right now.

If you need it here you are the unpacker without the decompression feature.

[http://www.tbhreloaded.it/Vash/Recettar ... .v.0.9.rar](http://www.tbhreloaded.it/Vash/Recettar.Unpacker.by.Vash.v.0.9.rar)

edit, almost done. I need to understand special cases
## Post #7
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-19T21:01:29+00:00
- Post Title: Recettear compression

I think I understand the basics around that, but I'm still not getting anywhere.

There's a control code at 0x62 in the enemylist which is 0xA2 = 1010 0010 in bin.
So I'm reading two bytes as a reference, one literal, one reference, three literals, one reference and one literal again (3 * 2 + 5 = 11 bytes till next control code). The first three work out fine, but then I'm supposed to read 0x04 as a literal, and everything starts to fall apart. There's also 12 bytes till the next control code and even if I ignore the 0x04, it ends up garbled. What the hell.
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-19T23:50:33+00:00
- Post Title: Recettear compression

I almost finished. This algorythm has many variants and I need to find them all.
## Post #9
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-20T12:08:26+00:00
- Post Title: Recettear compression

Alright, looks like I finally got it working (at least text files, images still don't work, although they weren't really my priority).
Tabs seem to be messed up, but eh.
Again, thanks a lot.
[enemylist_decompressed.rar](https://xentaxbackup.github.io/file/3459_enemylist_decompressed.rar)
## Post #10
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-20T12:54:17+00:00
- Post Title: Recettear compression

I made it..here you are, the unpacker with decompression algorythm included. It's a bit sloppy but it's working.

[http://www.tbhreloaded.it/Vash/Recettar ... .v.1.0.rar](http://www.tbhreloaded.it/Vash/Recettar.Unpacker.by.Vash.v.1.0.rar)

I didn't try but the game should read the files from outside. I'm in a hurry now but I'll make some tests whe I'll be back home.

P.S. the algorythm for this compression is the stupidiest EVER, it has no sense, standard LZSS compresses lot more!
## Post #11
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-09-20T13:14:28+00:00
- Post Title: Recettear compression

Yeah, it does seem like they took the normal LZS algorithm and changed it only for the sake of changing it.

By the way, mind posting your decompression routine?
I only covered 2 special cases (the one I described a few posts ago and one where the alg attempts to read more bytes than there are available) and it works for text files. Other files seem to have other special cases, what are they?
## Post #12
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-09-20T14:53:32+00:00
- Post Title: Recettear compression

I'm out now, I'll post it as soon as possible but I'm warning you...the code is a mess xD

```
{
flag=fgetc(bin);  
 
for (w=0;w<8;w++)
{
bit[w]=(flag>>(7-w))&0x1;
}    
times=realsize[i]-ftell(ext); 
if (times >= 8)
times=8; 
for (w=0;w<times;w++)
{
if (bit[w] == 0)
{
if  (ftell(bin)< pointer[i]+size[i]) 
{
if (ftell(ext)<realsize[i])
{    
byte=fgetc(bin);
fputc(byte,ext);    
}else{
w=times;    
}
}
}

if (bit[w] == 1)
{
if (ftell(ext)<realsize[i])
{     
if  (ftell(bin)< pointer[i]+size[i]) 
{    
recover=fgetc(bin); 
if (recover >= 0x10)
{
    
nib1=recover/0x10;
nib2=recover-(nib1*0x10);
recover=nib1+1;
jump=fgetc(bin);
tmp2=jump;
jump=(nib2*0x100)+tmp2;

if ((nib1==ftell(ext)/0x100 || ftell(ext)/0x100) && (nib1 != nib2))
{
tmp=nib2;
nib2=nib1;
nib1=tmp;
recover=nib1+1;
jump=(nib2*0x100)+tmp2;        
}

}else{
jump=fgetc(bin);
recover=recover+1;    
} 
if (recover == 1)
{
tmp=fgetc(bin);
recover=tmp+0x10+1;    
}
if (jump >= recover)
{
fseek(ext,-jump,SEEK_CUR);
fread(buffer,recover,1,ext);
fseek(ext,0x00,SEEK_END);
fwrite(buffer,recover,1,ext);
}else{
fseek(ext,-jump,SEEK_CUR);
fread(buffer,jump,1,ext); 
fseek(ext,0x00,SEEK_END);
y=0; 
for (z=0;z<recover;z++)
{
  
fputc(buffer[y],ext);
y++;
if (y>=jump)
{y=0;}
 
} //else

} //for  
}
}else{
w=times;    
}
}
}//for
}

```
## Post #13
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-11-27T17:12:43+00:00
- Post Title: Recettear compression

Hi Vash 

i use your unpacker but all files unpacked are 0bytes, do you made another unpacker ?
## Post #14
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-11-27T17:36:22+00:00
- Post Title: Recettear compression

nope. It works as it is. If i recall correctly you need to have lnkdatas.bin in the same directory and unite every dataXXX.bin in one file. 
The tool should do that for you but if it doesn't work, use this command:

```
copy /b data000.bin + data001.bin + data002.bin + data003.bin + data004.bin + data005.bin + data006.bin + data007.bin + data008.bin + data009.bin + data010.bin + data011.bin data.bin
```
## Post #15
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-11-28T10:57:36+00:00
- Post Title: Recettear compression

Ah oki, thx works now...

- Game can start like this ( i want make a french translation of this game ) ?
## Post #16
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-11-28T13:21:27+00:00
- Post Title: Re: Recettear compression

yes it works. You have to move the extracted directories in the root if I recall correctly
## Post #17
- Username: ecmanaut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 29, 2011 7:42 pm
- Post datetime: 2011-08-29T11:50:05+00:00
- Post Title: Re: Recettear compression

> Reply from Vash
>
> nope. It works as it is. If i recall correctly you need to have lnkdatas.bin in the same directory and unite every dataXXX.bin in one file. 
The tool should do that for you but if it doesn't work, use this command:
Code: Select allcopy /b data000.bin + data001.bin + data002.bin + data003.bin + data004.bin + data005.bin + data006.bin + data007.bin + data008.bin + data009.bin + data010.bin + data011.bin data.bin

Thanks for both the tool and this description that made the tool work right. I've started to excavate and play with visualizing the item data in ways I missed while playing the game at the most and probably would have lost interest before coming to the fun part of doing stuff with the data, had I had to do crack open the binary formats from scratch. 

[http://johan.github.com/d3/ex/recettear.html](http://johan.github.com/d3/ex/recettear.html) if anyone wants to play (change log at [https://github.com/johan/d3/commits/gh-pages](https://github.com/johan/d3/commits/gh-pages)).
## Post #18
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-22T16:35:16+00:00
- Post Title: Re: Recettear compression

Hey there!

I'm translating the game, but I can't seem to extract the fonts from the game, and I'd need it to put unicode characters in it. Any chance someone could help?
## Post #19
- Username: nekomiko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 14, 2016 11:15 am
- Post datetime: 2016-12-14T03:20:08+00:00
- Post Title: Re: Recettear compression

> Reply from TheReaperCooL
>
> Hey there!

I'm translating the game, but I can't seem to extract the fonts from the game, and I'd need it to put unicode characters in it. Any chance someone could help?
I noticed your post and decided to publish sources of my old unpacker. It is also able to unpack font bmps from fontdata.bin as you need. 
Sources: [https://github.com/nekomiko/recetunpack](https://github.com/nekomiko/recetunpack)
Windows version: [https://github.com/nekomiko/recetunpack ... unpack.zip](https://github.com/nekomiko/recetunpack/releases/download/0.1/recetunpack.zip)
## Post #20
- Username: cvnm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 29, 2019 11:43 pm
- Post datetime: 2019-04-29T15:45:27+00:00
- Post Title: Re: Recettear compression

Hi

Does anyone know how to use the posted application on the Japanese version of the bin files?

Thank you in advanced.
