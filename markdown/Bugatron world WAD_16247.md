## Post #1
- Username: ewok
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 07, 2017 8:05 pm
- Post datetime: 2017-05-07T12:51:00+00:00
- Post Title: Bugatron world WAD

Hello,
So i'm new to all these things and today i was trying to modifying datas from a game.
the game is on pc platform and named 'bugatron world' it's developed by retro64, it's a sort of galaga like.
i've noticed a file "smash.wad" who seem to contain all the interesting stuff (musics, graphics, xml config of levels, etc..)

here is a small snippet of inside this file:

```
			<CAPTURE FREQUENCY="12" MODEL="capture" BULLET_MODEL="cap" FONT="powerup" POINTS="50" TEXT="CAPTURE!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<GUIDED FREQUENCY="5" MODEL="guided" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="GUIDED BULLETS!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<ADD_BULLET FREQUENCY="5" MODEL="extrab" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="EXTRA BULLET!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<WRECKING_BALL FREQUENCY="5" MODEL="wb" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="WRECKING BALL!" EXTRA_MODEL="link" EXTRA_MODEL="mace" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<ACCELLERATION FREQUENCY="5" MODEL="accel" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="ACCELLERATION!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<DIRECTIONAL FREQUENCY="5" MODEL="angular" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="DIRECTIONAL BULLETS!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<SPINNER FREQUENCY="5" MODEL="spinners" BULLET_MODEL="spinner" FONT="powerup" POINTS="50" TEXT="WIGGLE SHOT!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<FIREBALL FREQUENCY="5" MODEL="fireb" BULLET_MODEL="fireball" FONT="powerup" POINTS="50" TEXT="FIREBALLS!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<EXTRA_LIFE FREQUENCY="1" MODEL="plusone" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="EXTRA LIFE!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<TRIPLE_SHOT FREQUENCY="5" MODEL="tripleshot" BULLET_MODEL="fireball" FONT="powerup" POINTS="50" TEXT="TRIPLE SHOT!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<GUIDED_ROCKETS FREQUENCY="5" MODEL="guidedrockets" BULLET_MODEL="rocket" FONT="powerup" POINTS="50" TEXT="HEAT SEEKING ROCKETS!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
			<RAILGUN FREQUENCY="5" MODEL="railgun" BULLET_MODEL="bullet" FONT="powerup" POINTS="50" TEXT="RAILGUN!" SPAWN_SOUND="puspawn.ogg" CATCH_SOUND="powerup.ogg" BOUNCE_SOUND="ping.ogg">
		</POWER_UPS>
	</LEVEL>

```

So i tried to change the values with an hex editor and everything went good while running the game  
The <POWER_UPS> part is related to bonus drop when you kill an enemy.

But when i try to insert more chars (meaning increasing filesize) for example changing the extra_life frequency from 5 to 99, the game just crash when it try to load the WAD file.
I don't know much about WAD files, from what's i've read it's originating from doom, so i tried to find tools but they was obviously related for doom WAD files and with a bit more googling i ended up on a wiki pointing to this forum.
The 4 first bytes of the WAD file is 42 4D 36 0C (BM6) i have no idea if there is a sort of standard for wad file format or similar.
Maybe by increasing filesize i broke a CRC or something, i don't know and i'm out of ideas on how i can edit properly game level infos...
If someone with experience can guide me ?

Here is the download for wad file, it's arround 43Mb: [http://rgho.st/7Cl2WYDxh](http://rgho.st/7Cl2WYDxh)
## Post #2
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-05-07T18:37:42+00:00
- Post Title: Bugatron world WAD

'BM" - it is typical *.BMP image header. If you selecting bytes range from start to next 'BM' chars (0xC36 offset) and save these bytes as BMP file, you can see what that is the star texture.

WAD file, what you provide, it is raw container without any info (offsets, sizes) about files stored in. So, this info should be somewhere in other game files.
