## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2016-01-14T11:57:24+00:00
- Post Title: Need help defining a font format

Hello. I'm working on a Russian translation project for a Korean game called Whiteday: A Labyrinth named School. By whatever magic, the in-game font does actually include Cyrillic characters, but they're a bit wrong. To give you a comparison, here's what original English and Original Korean text look like in-game:
[](http://imgur.com/aTY3Cfp)

And here's how Russian text shows up:
[](http://imgur.com/JJbqhWn)

Notice how thin the characters are and spacing is way too high.

I did a little "research" and found out that what font is used in the game. I downloaded that font and replaced the glyphs with more decent ones (similar to the Latin set).

Now, the problem is, it's still a ttf, while the game uses files with .fnt and .wft extension. The first few bytes of both filetypes show "WFNT"in HEX-Editor. So I looked on the internet and found only one mention of .wfnt fonts. [Here](http://comments.gmane.org/gmane.comp.embedded.nano-x/62) is a discussion of something called the w windowing system, and they mention a wfnt font format. But I couldn't find any tools or even specifications of the format.
So I want to ask if anyone knows anything about that format? How can I create a (or more specifically, convert to) wfnt font?

I have uploaded the in-game fonts [here](https://cloud.mail.ru/public/HUi7/r1QQVDYhk).
