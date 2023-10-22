## Post #1
- Username: Meth0d
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2016 1:29 am
- Post datetime: 2020-02-03T01:13:26+00:00
- Post Title: Image Raw Data to DDS (But without colors)

Hello guys, so, I was trying to get an image from the Batman Vengeance game and I used Raw Texture Cook to get it...
Well, the program generated a DDS from the raw texture, but there is one problem, it does not contain colors, it's pure black and white.

I'm providing a ZIP that contains the raw data of the image and the generated DDS from the texture cooker.

I belive there is something wrong with the DDS header.. So i'm asking your help to solve the color problem.

The generated image:


Thanks!
[DDSColorProblem.zip](https://xentaxbackup.github.io/file/17448_DDSColorProblem.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-03-24T06:44:51+00:00
- Post Title: Image Raw Data to DDS (But without colors)

which platform did your samples come from? 
google says this game was released on GameCube, 
Game Boy Advance, PlayStation 2, Microsoft Windows and Xbox.   
looks like there might be a color palette at the end of the file.
do you have more samples to compare against?

edit
here is Noesis python script to open your one sample.  


 tex_BatmanVengeance_bvt.zip
(580 Bytes) Downloaded 22 times


supports rgba5551 with shuffled 4-bit palette

give your sample the 'bvt' extension and open the sample,
the script is hardcoded to this one sample, will likely not
work with any other samples.
