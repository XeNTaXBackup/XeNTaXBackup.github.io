## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-06-05T02:49:57+00:00
- Post Title: LiveMaker Engine compression format

Live maker is a japanese game engine. It's pretty popular, with a ton of games developed using it.
A new feature in version 3 was a new encryption/compression algorithm is used during the game publishing process in order to protect your resources. Prior to this, all of the resources were unprotected so if you can extract the files, you've got the stuff

I don't know what would be the easiest way to reverse it, but maybe if you could just step through the actual archive building process, you can reverse it from there.

Here are the steps

1. Download the engine from [http://www.livemaker.net/download/beta/](http://www.livemaker.net/download/beta/)
The latest version as of now is [http://www.livemaker.net/files/setup03120307f.exe](http://www.livemaker.net/files/setup03120307f.exe)

2. Install it

3. Download this project that I've put together: [http://www.mediafire.com/download/ii6pe ... vemaker.7z](http://www.mediafire.com/download/ii6pez12ms7dnis/livemaker.7z)

When you unpack it, you will find a "livemaker" folder, which contains a "runimage" folder that is the source project, along with a "game" folder which is a published game. In the game folder, you will also see an unpacked version of the game, with all of the files compressed and encrypted.

In the runimage folder, if you go to グラフィック and then 顔, you will find a picture called "squares.bmp" which is just a blue and red rectangle. You will also find a file called "squares.gal", which is just the image format that the engine uses. The .gal file will be compressed in the published game, and you can find it in the unpacked game under the same directory structure.

4. Run LiveNovel.exe

5. when the program begins, click on the file menu (first menu item at the top with an F) and click the second button. This will open a project. Select the "livemaker" folder that you downloaded earlier. This should open the project.

6. Click on the 4th menu item, with the P. Then select the item with the M. A dialog will appear with an OK and cancel option. Click OK to publish the game.

Now all the resources will be compressed/encrypted and packed up.

Let me know if you need a picture tutorial, or if something goes wrong along the way.
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-05T04:52:33+00:00
- Post Title: LiveMaker Engine compression format

What games use this?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-06-05T14:23:03+00:00
- Post Title: LiveMaker Engine compression format

They've got a list of products that have been submitted for showcasing
[http://www.livemaker.net/gallery/](http://www.livemaker.net/gallery/)
## Post #4
- Username: Veshurik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 08, 2015 10:43 pm
- Post datetime: 2017-03-13T09:16:10+00:00
- Post Title: LiveMaker Engine compression format

Wow, I finally find the right post. I just don't know how to unpack (extract) all the files and pack it then, if only exists live.dll and .exe file. I just want to translate the game, but don't know what to do. LiveMaker doesn't open project which already compilated.
Download the game is [here](https://box.yahoo.co.jp/guest/viewer?sid=box-l-mmiohbs3qsmi474ecb7xfd2cpu-1001&uniqid=d9e129a6-4eee-4c76-b950-820861fb60e7&viewtype=detail). Would be glad if you help.
