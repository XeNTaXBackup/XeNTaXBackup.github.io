## Post #1
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-11-24T18:44:19+00:00
- Post Title: Unknown Image format from mobile games

I got these textures from 2 different game. They look like DXT1 which compression ratio are 1:8.
But I can't get the correct images. I wonder if this is a common format of mobile texture?

Phantom Soul has 68 bytes header 

samples: [https://mega.nz/#!rl1zkCIR!u2TCvRPKQ8WV ... kOjcdDHqkA](https://mega.nz/#!rl1zkCIR!u2TCvRPKQ8WVrxX6ZkdCD3sxxZqpxo8BWkOjcdDHqkA)

Absolute field has 16 bytes header

samples: [https://mega.nz/#!X8URnTIL!3Djjnjme507z ... vdxjGVr-qE](https://mega.nz/#!X8URnTIL!3Djjnjme507zELNwHJ8Rk2RLKaJMTgMcHvdxjGVr-qE)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-24T20:38:01+00:00
- Post Title: Unknown Image format from mobile games

give your "Phantom Souls" samples a ktx extension and your "Absolute field" samples a pkm extension
and you can open and convert them with the "Mali GPU Texture Compression Tool" here   
[http://malideveloper.arm.com/resources/ ... sion-tool/](http://malideveloper.arm.com/resources/tools/mali-gpu-texture-compression-tool/)

for the 2 pkm textures that error out you can delete the first 12 bytes then save and try again   
sky_014_u.pkm
zudui_u.pkm
## Post #3
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-11-25T20:22:49+00:00
- Post Title: Unknown Image format from mobile games

Thank you for the quick reply. it works!
