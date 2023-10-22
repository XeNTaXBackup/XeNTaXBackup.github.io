## Post #1
- Username: ponlork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 18, 2011 1:01 pm
- Post datetime: 2022-04-22T13:06:30+00:00
- Post Title: Need help decompressing graphics from NBA Hangtime (PSX)

I'm trying decompress the players head sprites from NBA Hangtime for the PS1, I located exactly where the head graphics are located but I am unable to decompress it. 

There's a file named BIGLUMP.BIN on the disc and at offset D1000 is where the heads start:


I've uploaded all the relevant files here:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1iZKwBH6OYxYQt3zj1az5xVd2a4Om9Hzs?usp=sharing)

basically it's categorized by Team names in alphabetical order, so the first team is the Atlanta Hawks with Dikembe Mutombo as the first player. And each player data is separated by a message that reads ""Gary Liddon BYC rules the world as caffeine boy" which I read was used for padding. 

I found another game that Gary Liddon program called SpongeBob SquarePants: SuperSponge and the source code is available online: [https://github.com/hazelcode/SBSPSS](https://github.com/hazelcode/SBSPSS)

it also contains a BIGLUMP.bin file and I thought maybe the two games shared similar tools and methodology in constructing the game. At first I thought the heads might be a uncompressed .gfx file and I used a tool from the github called Tga2Gfx.exe and converted some sample Tga images to gfx but when comparing it in hex I don't think it's that.

then I thought it might be compressed and I use the tool lznp.exe, and it did decompress something but I couldn't get it any image to display in TiledGGD.

I recently released a mod for a similar game called NBA Jam 22 ver1.4, and the heads in that one are uncompressed, while the body sprites use Rob Northen-compression. I believe hangtime uses a similar template for the heads.

here's a example of how the head data look in NBA Jam:


In hangtime, the head order seems the same, at D1000 is the backhead, then at D1100 is the upright angle facing away at 3/4, then at D1260 is the perfect side view angle. I haven't gone down much further but I confirm these are where the heads are stored by blanking the hex with zeros and it corrupted the image. Ive also copied the hex portion for the side view angle to the backhead angle and it does swap the image though it came out disjointed.

I also think that each angle is it's own individual sprite that is compressed opposed to it being in a spritesheet like NBA Jam. This allows for players to have long hair and wear top hats and stuff. Anyway, thanks for reading and any help would be appreciated.
