## Post #1
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2017-09-08T11:06:00+00:00
- Post Title: Psarc help, setting compression only for specific files

it says here to use xml with psarc.exe to set compression for specific files: [http://www.psdevwiki.com/ps3/PlayStatio ... ve_(PSARC)](http://www.psdevwiki.com/ps3/PlayStation_archive_%28PSARC%29)
but how do i do that, i could find any more information, i have never used xml before

these were at 100% in the original psarc, now they are compressed, and the gaim wont load with them compressed, but the other files in the psarc are the correct sizes, so how do i make sure all but these get compressed?

/built/levels/haven_town_center/c_bowling_to_mainstreet/region.dat (20338/42908 47%)
/built/levels/haven_town_center/c_bowling_to_mainstreet/sky.dat (3333395/5636224 59%)

ps. there are about 100 files needing compressed, and 10ish not needing it
## Post #2
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2017-09-08T11:40:29+00:00
- Post Title: Psarc help, setting compression only for specific files

Nvm nailed it 

for those who want to know: 
put in xml.xml
<psarc>
	<create archive="C:\users\smasher248\desktop\the last of us\mods\psarc.psarc" absolute="false" ignorecase="false">
		<compression type="zlib" enabled="true" />

		<file path="C:\users\smasher248\desktop\the last of us\mods\levels\haven_town_center\scripts\main.lua"/>
		<file path="C:\users\smasher248\desktop\the last of us\mods\levels\haven_town_center\scripts\music.lua" compressed="false"/>
	</create>
</psarc>

C:\Users\smasher248\Desktop\the last of us\mods>psarc.exe --xml="xml.xml"              <--run in cmd
