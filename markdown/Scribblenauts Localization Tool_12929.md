## Post #1
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-06-10T17:37:26+00:00
- Post Title: Scribblenauts Localization Tool

Hey there fellas!

I'm looking for a tool that would help me to extract the strings from Scribblenauts, and then I'd edit them and pack them back in. Yes, I've searched around the forums and found some tools, but they only unpack, but not in the way I'd like them to.

It's obvious that objects are stored in objects.p, and I need those. I need them like the tool extracts all objects, and then I could put custom names in the file, replacing older ones witch unicode support. So if there's an item called "PEAR", I could put "KÖRTE" in it. Also it would work with words with different meanings, like in Hungary "KÖRTE" means Pear, OR it could also mean Lamp bulb, so it would ask what I want (similar to the English "LETTER").

I don't know if you guys understand what I'm asking for, but it would be nice if there would be a tool like this, where we could replace the whole dictionary, thus translating it.

Also I don't know which file contains the in-game text, but I'd also need a tool for it, so I could translate objectives and such.

If anyone could help me with this I'd appreciate it
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-13T22:58:34+00:00
- Post Title: Scribblenauts Localization Tool

can you find any localisation tools for this program?

i'll help write a packer if we know the game does support unicode. is this for pc?
## Post #3
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-06-14T10:58:36+00:00
- Post Title: Scribblenauts Localization Tool

Yes, it's for PC. The unpacker tools that I found are interesting. You can find them here: [blog/?tag=scribblenauts-unlimited-unpacker](http://forum.xentax.com/blog/?tag=scribblenauts-unlimited-unpacker)

I do what the description says, namely drop the index.bin onto the unpacker, and it extracts everything. Also it should support unicode characters, because there's even a language selector in it, which changes lots of stuff, and you can write them in-game ([Screenshot](http://kepfeltoltes.hu/150614/7130146262015-06-14_00001_www.kepfeltoltes.hu_.jpg)).

Can't find any localisation tool, and that's my main problem here. There are homonim words (words that look and sound the same, but have different meanings), like Rocker, which can be a Furniture, or a Person ([Screenshot](http://kepfeltoltes.hu/150614/4897458372015-06-14_00002_www.kepfeltoltes.hu_.jpg)). If I were to edit it I would need to assing and add words like this, that's why it's not so easy. Another example is that the game uses differents words for the same object, like Bride and Virgin ([Screenshot](http://kepfeltoltes.hu/150614/991518372015-06-14_00003_www.kepfeltoltes.hu_.jpg)).

I could find the extracted files and stuff like adjectives in the index.bin_extracted\data\_game\scribbleadjectives\dictionary folder. It contains all the adjectives, plus the characters the specific language supports (for example the [adjective_dictionary_french](http://kepfeltoltes.hu/150614/screenshot1_www.kepfeltoltes.hu_.jpg) file looks like this, and I've also made [another screenshot with a HEX Editor](http://kepfeltoltes.hu/150614/screenshot2_www.kepfeltoltes.hu_.jpg)).


Hope this information is enough for research, although these are only the objects/adjectives, I didn't find the in-game text/dialog yet.
