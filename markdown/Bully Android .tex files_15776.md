## Post #1
- Username: Drawken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 20, 2015 5:33 am
- Post datetime: 2017-01-22T23:24:44+00:00
- Post Title: Bully Android .tex files

I was wondering if anyone can take a look into the file format used in the .tex files for the game Bully on Android.
For the first sample, 1stradar100.tex, I was successful in replacing the header (I replaced the first 26 lines in a hex editor, and with the 27th line I replaced up to 4 spaces after the } bracket) with that of a DXT1 .dds file.
But for the font_sabon.tex file, I can't seem to find the correct DDS header. (If it is in fact dds.)

Not sure if this is helpful, but each .tex file has a list of these properties at the top.
Contents of font_sabon.tex.:

```
{width=1024,height=1024,mode=tm_distancefield,nomips=false,compressondisk=false,addressmodeu=tam_wrap,addressmodev=tam_wrap,samplerstate={minfilter=tfm_linear,magfilter=tfm_linear,mipfilter=tfm_linear},df_params={fieldscale=2,pixeldistance=0},pp_params={extrabrightness=0.000000,extracontrast=0.000000,gammamod=0.000000},importfilepath="D:\BullyMobile\Middleware\FontStuff\font_sabon.png"}
```

[http://www.mediafire.com/file/6h02n6kyu ... amples.zip](http://www.mediafire.com/file/6h02n6kyuuxbiff/BullyAndroidTextureSamples.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-24T02:34:28+00:00
- Post Title: Bully Android .tex files

here is Noesis python script to open your samples  


 tex_Bully_Android_tex.zip
(779 Bytes) Downloaded 45 times



supports dxt1 and alpha 1/8
## Post #3
- Username: Drawken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 20, 2015 5:33 am
- Post datetime: 2017-01-24T08:40:50+00:00
- Post Title: Bully Android .tex files

Thanks so much for putting in the time to do this! 
Unfortunately it doesn't open up all the .tex files. 
But that's alright.  I was able to figure out how to use NinjaRipper to extract the textures from Bluestacks.
(Too bad the fonts don't seem to be texture files like they are for the PC version. I was hoping to replace the font for the PC version with a higher res texture. Oh, well.)
Thanks again!
