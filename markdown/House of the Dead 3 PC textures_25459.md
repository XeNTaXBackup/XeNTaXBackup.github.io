## Post #1
- Username: genuro82
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 30, 2022 5:02 pm
- Post datetime: 2022-05-30T09:44:40+00:00
- Post Title: House of the Dead 3 PC textures

Sorry if this is the wrong area for this i'm new here,

I'am trying to fix a broken texture / sprite in House of the Dead 3 PC, the texture / sprite is easy enough to find extract and change but the game seems very picky about how its archives are structured.

The texture / sprite in question is also stored in 2 locations as far as I can tell.

first location is in a normal .zip format which is full of .dds files 

second location is in a .afs storage file which is full of similar .zip files which again contains almost the exact same .dds files.

on trying to replace the broken .dds file within the first location (.zip) via drag and drop, the shadow is fixed but most of the texture in this area are now blank.

with this i guess the game is trying to find the textures directly from the .zip file but because they are now mostly all moved slightly it just receives broken .dds files.

so I try and restore the structure of the .zip file in hxd by adding 000000 which does fix all the missing textures but my fixed shadow texture is now not being taken directly from the .zip file but now being taken from this second location (the .afs file) unfortunately the .afs file also seems to have a damaged shadow texture.

So I try and edit the .afs file but it then just skips the texture i added completely and uses the next one down the file. 

At this point i gave up on trying to replace the texture and instead tried to inject the fixed texture via special K, unfortunately this game uses direct x 8 and special k does not work well with this. 

So now I'm wondering if anyone here can help somehow or maybe just suggest a different texture injector (something that looks for a specific .dds file name and replaces it on the fly)

I have attached some screenshots for context, i will mention that on inspection the PS3 version actually uses a modded version of the pc port.

it even has the broken texture and has a "modify" folder which contains a single .dds file specifically for this shadow to be fixed.



Untitle1d.jpg (221.33 KiB) Viewed 41 times
## Post #2
- Username: genuro82
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 30, 2022 5:02 pm
- Post datetime: 2022-05-30T11:28:19+00:00
- Post Title: House of the Dead 3 PC textures

Im actually wondering if there's an answer at the bottom of the zip file in hex.

highlighted in the attachment is the filename of the .dds file that i have edited along with i guess some sort of crc check or file position info.

I had to copy this line from the original zip file before editing otherwise i just get loads of blank textures again.

is there any way to change this selected line to accurately go along with the compressed data? 



Untitled.jpg (233.76 KiB) Viewed 37 times
## Post #3
- Username: genuro82
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 30, 2022 5:02 pm
- Post datetime: 2022-05-30T13:19:57+00:00
- Post Title: House of the Dead 3 PC textures

Well ok...

I just decided to make these posts as i've been trying to fix this for a week now.

AND I just figured it out, turns out that the "header" i highlighted in the previous post was indeed broken.

a quick winrar repair and a little bit of hex rearranging again fixed the games broken texture.

hopefully this post can stay here incase anyone else ever tries to fix this issue.

heres the fixed zip file (just backup / replace original in the "fs2" folder) : [https://1drv.ms/u/s!AthYoE0KaQe7pW8qzVd ... T?e=bJZeJ2](https://1drv.ms/u/s!AthYoE0KaQe7pW8qzVdi7MZMblRT?e=bJZeJ2)




unknown1.jpg (242.8 KiB) Viewed 35 times
