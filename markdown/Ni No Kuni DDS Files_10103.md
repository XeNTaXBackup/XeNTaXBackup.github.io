## Post #1
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-01-31T15:39:11+00:00
- Post Title: Ni No Kuni DDS Files

I'm trying to extract some content from the game files and so far I've gotten right down to the DDS textures pulled from the p3igg and p3img files using chrrox's script from [viewtopic.php?f=10&t=5037](http://forum.xentax.com/viewtopic.php?f=10&t=5037). This pulls out two files: the grayscale texture and a color palette file.

    I had to do some tweaking to the resulting texture file as mentioned by dodther in that same thread, because Ni No Kuni dds files don't all seem to use DXT1. Following in dodther's footsteps leads me to the greyscale texture and the palette. For example, the texture looks like this:



    And the palette is a 256x1 line with random colors. I get the concept is that the grayscale is supposed to combine with the color palette when the game is being rendered, but I need to figure out how to do that and then save it to a usable image format. So far I haven't seen anything that can do this for me, or maybe I've pointed myself in the wrong direction. If anyone can help I'd appreciate it.

    If anyone requires a sample, please PM me. I will respond back as soon as I can.
## Post #2
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-02-05T22:39:25+00:00
- Post Title: Ni No Kuni DDS Files

Maybe the grayscale value in the image is also the index for the palette? So a grayscale pixel with the value 8 would use the eighth pixel from the palette image. Just need to figure out if it's the eighth from the left or from the right.
## Post #3
- Username: powoct
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 12, 2011 5:59 pm
- Post datetime: 2013-02-10T09:33:54+00:00
- Post Title: Ni No Kuni DDS Files

```
endian big
get NAME basename
set NAMEIMG NAME
set NAMEIGG NAME
string NAMEIMG += ".p3img"
string NAMEIGG += ".p3igg"
open FDSE NAMEIMG
idstring "img"
goto 0x10
get BASEOFF long
goto 0x28
get FILES long
goto 0x30
get SKIPOFF long
set STARTOFF BASEOFF
math STARTOFF += SKIPOFF
for i = 0 < FILES
endian big
goto STARTOFF
get NAMEOFF long
math NAMEOFF += BASEOFF
get OFFSET long
get SIZE long
get DUMMY long
get TYPE long
get FILENUM long
get WIDTH short
get HEIGHT short
getdstring USLS 0x14
savepos STARTOFF
if TYPE == 0xa1010200
set TWIDTH WIDTH
set THEIGHT HEIGHT
set TSIZE SIZE
set NAME1 NAME
set j i
math j / 2
string NAME1 += "_"
string NAME1 += j
callfunction logPIXEL
elif TYPE == 0xa5010200
set NAME2 NAME1
string NAME2 += ".plt"
set NAME3 NAME1
string NAME3 += ".dds"
callfunction logPALETTE
callfunction writeDDSpalette
endif
Open FDSE NAMEIMG
next i

startfunction logPIXEL
Open FDSE NAMEIGG
log NAME1 OFFSET SIZE
endfunction

startfunction logPALETTE
Open FDSE NAMEIGG
set COUNT 0x100
set OFF 0
goto OFFSET
for i = 0 < COUNT
get TMP1 byte
get TMP2 byte
get TMP3 byte
get TMP4 byte
putVarChr MEMORY_FILE OFF TMP2 byte
math OFF += 1
putVarChr MEMORY_FILE OFF TMP3 byte
math OFF += 1
putVarChr MEMORY_FILE OFF TMP4 byte
math OFF += 1
putVarChr MEMORY_FILE OFF TMP1 byte
math OFF += 1
next i
log NAME2 0 0x400 MEMORY_FILE
endfunction

startfunction writeDDSpalette
Open "." NAME2
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7c\x0\x0\x0\x7\x10\x8\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x20\x0\x0\x0\x20\x0\x0\x0\x0\x0\x0\x0\x8\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x10\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0\x0"
putVarChr MEMORY_FILE 0x10 TWIDTH long
putVarChr MEMORY_FILE 0xc THEIGHT long
putVarChr MEMORY_FILE 0x14 TSIZE long
append
log MEMORY_FILE 0 0x400
append
Open "." NAME1
get ASIZE asize
append
log MEMORY_FILE 0 ASIZE
append
math ASIZE += 0x80
log NAME3 0 ASIZE MEMORY_FILE
endfunction
```

Use this script for the palette type p3igg.It will create some additional files in order to make the script simple.You can delete them and just look in the dds.Or you can optimize the script.
Some p3igg contains more than one graphic.Exported dds will be named as xxx_0.dds xxx_1.dds xxx_2.dds etc.
PS:Sorry for my poor English bro
## Post #4
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-02-23T07:38:27+00:00
- Post Title: Ni No Kuni DDS Files

plt file 1024x1px  8  L   8 bpp | luminance
contain pallete for main image
groups 4px for ARGB color for 1px main image.
## Post #5
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-07-20T23:44:54+00:00
- Post Title: Ni No Kuni DDS Files

Does anyone know how to do what dodther has done in the post above mine?

I sent him a PM about it and he said he wrote a program to do it. Unfortunately he hasn't responded to my requests for a copy of said program.

Any ideas?
## Post #6
- Username: zanearn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2012 9:02 am
- Post datetime: 2013-08-01T04:10:57+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from neurotech
>
> Does anyone know how to do what dodther has done in the post above mine?

I sent him a PM about it and he said he wrote a program to do it. Unfortunately he hasn't responded to my requests for a copy of said program.

Any ideas?

I'll double this.

Somebody please help.

---after some searching---

In [THIS POST: (Ps3) White Knight Chronicles](http://forum.xentax.com/viewtopic.php?f=10&t=5037)
dodther said he used "Image to dds converter" script provided by chrrox (also in the post)
now just need to figure out what "plt file 1024x1px 8 L 8 bpp | luminance" means

Seems dodther and his friends are translating Ni no Kuni to Russian [here](http://alliancetm.net/forum/viewtopic.php?f=16&t=11&start=50).
But I really don't know Russian, so just guessing.

Hope dodther will come back soon...
## Post #7
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-12-05T00:34:53+00:00
- Post Title: Ni No Kuni DDS Files

save dds main image and plt as png. 

create txt file and rename to  anyname.php. put to him code

```
//dl("php_gd2.dll");

//$size_arr = getimagesize($argv['1']."_plt.png");
$img_plt = imagecreatefrompng($argv['1']."_plt.png");
$width_plt = imagesx($img_plt); 
//$rgb = imagecolorat($img_plt, "0","0");

for ($x=0,$xx = 0; $x<$width_plt; $x+=4, $xx++)
	{
	$color[$xx]["a"]  = imagecolorat($img_plt, $x,"0") & 0xFF; 
	$color[$xx]["r"] = imagecolorat($img_plt, $x+1,"0") & 0xFF; 
	$color[$xx]["g"] = imagecolorat($img_plt, $x+2,"0") & 0xFF; 
	$color[$xx]["b"] = imagecolorat($img_plt, $x+3,"0") & 0xFF; 
$alfa[]= imagecolorat($img_plt, $x,"0") & 0xFF; 

	}
	
	$img = imagecreatefrompng($argv['1'].".png");
	$img_alfa = imagecreatefrompng($argv['1'].".png");
	$width = imagesx($img);
	$height = imagesy($img);
	//$img_alfa = imagecreate ($width, $height);
	imagealphablending($img, false);
	imagesavealpha ($img, TRUE);
	//$png = imagecreatetruecolor($width,"1");
	//$temp_img = imagecreatetruecolor("1","1");
	for ($y=0; $y<$height; $y++){
	
	for ($x=0; $x<$width; $x++)//перебираем ширину
	{
	$rgb = imagecolorat($img, $x,$y);
	$color_temp = $rgb & 0xFF; 
	$color[$color_temp]["r"];
	$alfa_temp = ceil(128-($color[$color_temp]["a"] / 2))-1;
	
	// альфа в картинке
	//$alfa_temp = ($color[$color_temp]["b"]/2)-1;
	//$temp_color = imagecolorallocatealpha  ( $img, $color[$color_temp]["r"] , $color[$color_temp]["g"] , $color[$color_temp]["b"] ,$alfa_temp);
	
	// альфа отдельно
	 $temp_color = imagecolorallocate  ( $img, $color[$color_temp]["r"] , $color[$color_temp]["g"] , $color[$color_temp]["b"]);
	 $temp_color_alfa = imagecolorallocate  ( $img_alfa, $color[$color_temp]["a"] , $color[$color_temp]["a"] , $color[$color_temp]["a"]);
	 
	 
	 //echo "\r\n";
	 imagesetpixel($img , $x , $y ,$temp_color );
	imagesetpixel($img_alfa , $x , $y ,$temp_color_alfa );
	}
	}
	 imagepng ($img , $argv['1']."_color.png");
	 imagepng ($img_alfa , $argv['1']."_alfa.png");
	//print_r($alfa);



?>

```


create txt file and rename him to anyfile.cmd
put to him

```
path_to_php.exe anyfile.php main_png_amage_without_extension
```


in php.ini need activate gd library
## Post #8
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-12-05T00:43:15+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from dodther
>
> save dds main image and plt as png.

Thank you so much for this, dodther. Do you (or anyone else!) have a sample image I could use to test this? I'm at work and don't have access to my Ni No Kuni dumped files.
## Post #9
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-12-05T07:58:52+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from dodther
>
> save dds main image and plt as png.

Does anyone know how to save the plt as a png?
## Post #10
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-12-05T07:59:11+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from neurotech
>
> dodther wrote:save dds main image and plt as png.

Thank you so much for this, dodther. Do you (or anyone else!) have a sample image I could use to test this? I'm at work and don't have access to my Ni No Kuni dumped files.
[http://yadi.sk/d/2BdM-n5BDpFdk](http://yadi.sk/d/2BdM-n5BDpFdk)
## Post #11
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-12-05T08:29:15+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from dodther
>
> neurotech wrote:dodther wrote:save dds main image and plt as png.

Thank you so much for this, dodther. Do you (or anyone else!) have a sample image I could use to test this? I'm at work and don't have access to my Ni No Kuni dumped files.
http://yadi.sk/d/2BdM-n5BDpFdk

Using that example with the PHP file produces two files: pause01_alfa.png and pause01_color.png - both are 768 x 512 images, all black.

How can I get this to work?
## Post #12
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-12-05T08:57:18+00:00
- Post Title: Ni No Kuni DDS Files

for me works.
## Post #13
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-12-05T09:02:38+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from dodther
>
> for me works.

How do you convert the DDS files in your example to PNG?

I used Irfanview to 'Save as' PNG. Is that wrong?

Also, do you use instant messaging, like google talk?
## Post #14
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-12-05T10:11:27+00:00
- Post Title: Ni No Kuni DDS Files

i use Photoshop with dds plugin
## Post #15
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-12-05T10:23:20+00:00
- Post Title: Ni No Kuni DDS Files

> Reply from dodther
>
> i use Photoshop with dds plugin

Okay. And how'd you extract the textures/plt to DDS?
