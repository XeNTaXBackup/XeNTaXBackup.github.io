## Post #1
- Username: alhakemmido2
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Dec 29, 2011 10:01 pm
- Post datetime: 2012-03-05T16:39:48+00:00
- Post Title: translate metro 2033

i want translate the game into arabic i need to extract the text from game and put into the game agian 
any help please or you can guied me to place i can have an answer
## Post #2
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-07T23:09:05+00:00
- Post Title: translate metro 2033

I have tool to localization stuff, but you'll also need to edit fonts to add your characters. I think the game doesn't support arabic alphabet. I can't explain you how to do it, 'cause this is a bit complicated and in my translation another guy did it for me.

In short, you need to extract a .upk file, edit the fonts (.dds format), edit the font mapping file (in hex) and then use my localization tool to export/import the texts. After that, you compile a new .upk with only the new files included (fonts + texts) and rename it like: content.upk9. This works like a patch, the game always read the upper file (0 up to 9).

Here is the upk extractor/packer:
[http://www.mediafire.com/?klbulykas4z9cks](http://www.mediafire.com/?klbulykas4z9cks)

Here are the fonts + font mapping file:
[http://www.mediafire.com/?mo0h3w1l61am2lu](http://www.mediafire.com/?mo0h3w1l61am2lu)

The font mapping file is: scripts.bin

Try to follow my infos and edit fonts + pack the content.upk9

If you're able to do this, i'll share my loc tools for texts.

H3rdell
## Post #3
- Username: alhakemmido2
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Dec 29, 2011 10:01 pm
- Post datetime: 2012-03-10T13:03:19+00:00
- Post Title: translate metro 2033

thank you i will try
but can you add more explain or details
## Post #4
- Username: xingzj0117
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 30, 2012 3:44 pm
- Post datetime: 2012-07-30T07:53:39+00:00
- Post Title: translate metro 2033

Hi H3rdell,

I am doing the localization of the metro 2033, and now I can unpack and pack the resource, but I need your localization tool to import the language text, so could you share your tool with me? thank you very much, my email address is [xingzj0117@gmail.com](mailto:xingzj0117@gmail.com)

Thanks,
Xingzj0117
## Post #5
- Username: Youba
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 07, 2023 7:43 am
- Post datetime: 2023-09-09T16:53:39+00:00
- Post Title: translate metro 2033

hello bro 
How do you arrange the letters of the Arabic alphabet according to your order?
Can you give me the email of the person who made the letters for you?
