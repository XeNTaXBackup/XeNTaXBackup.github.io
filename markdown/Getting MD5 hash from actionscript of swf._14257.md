## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-04-22T10:27:37+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

Hi,   . I'm trying to figure out what 'input_md5_1' will be.
Here is sample files. [https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_bNTEyOWZSOXMtVkk/view?usp=sharing)
And this is actionscript from sample swf file. To see a actionscript from swf, use this program. [https://www.free-decompiler.com/flash/download/](https://www.free-decompiler.com/flash/download/)

scripts\game\entry\GameEntryDesktopAir.as

```
         {
            start = getTimer();
            gamesave_bin_txt = this.readChecksumFile("Front-Buffer subsystem M",rp + "gamesave.bin");
            gamesave_bin_txt = gamesave_bin_txt.replace("\n","");
            gamesave_bin_txt = gamesave_bin_txt.replace("\r","");
            swf_md5 = this.verifyChecksum("Front-Buffer subsystem W",rp + "app.game-" + appInfo.sku + ".air.swf",null);
            logInfo("Front-Buffer " + (getTimer() - start));
            worldserpent = "zabbawabba";
            [b]input_1 = swf_md5 + "\r\n" + worldserpent;[/b]
            input_md5_1 = MD5.hash(input_1);
            logInfo("INVOKE entry recursion timestamp [" + swf_md5 + "]");
            if(input_md5_1 != gamesave_bin_txt)
            {
               throw new ArgumentError("Bitswizzle I/O/D error on evaluation of quest parameters");
            }
```


In my opinion, 
> input_md5_1=app.game-appInfo.sku.air.swf\r\nzabbawabba
However MD5.hash(app.game-appInfo.sku.air.swf\r\nzabbawabba) = 036cd9b37886d3c845d5cd72052b8d2b.
I test it on this site. [http://www.miraclesalad.com/webtools/md5.php](http://www.miraclesalad.com/webtools/md5.php)

As a result, it is different from gamesave_bin_txt(928f95ce47e21045537273f8cc0c34e40D0A)
Can someone solve this problem? Exactly what 'input_md5_1' is?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-22T19:51:51+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

you sure it isn't hashing the file contents, not the name?

edit

yeah, according to this dump - [http://pastebin.com/65kLr9pf](http://pastebin.com/65kLr9pf) it's just

```
MD5.hash( MD5.hash( file_contents( app.game-appInfo.sku.air.swf) ) + "\r\nzabbawabba" )

```
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-04-23T01:26:23+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

> Reply from WRS
>
> you sure it isn't hashing the file contents, not the name?

edit

yeah, according to this dump - http://pastebin.com/65kLr9pf it's just
Code: Select all// pseudocode
MD5.hash( MD5.hash( file_contents( app.game-appInfo.sku.air.swf) ) + "\r\nzabbawabba" )

Uhm..




The result is not '928f95ce47e21045537273f8cc0c34e4'.. I'm not sure what do you mean 'file_contents'? Is it md5 hash of swf file? It is 'c3e3378b9e46a859269e1ff1f8ff0e99' But it still different from gamesave_text. And according to actionscripts swf_md5 uses private function veryfyChecksum.

```
      {
         logDebug(":::: " + param2);
         var _loc5_:* = param3 == "0";
         var _loc6_:File = new File(param2);
         if(!_loc6_.exists)
         {
            if(_loc5_)
            {
               return null;
            }
            if(!param4)
            {
               throw new ArgumentError("Bitswizzle I/O error on " + param1);
            }
            return null;
         }
         if(_loc5_)
         {
            throw new ArgumentError("Bitswizzle I/O error on " + param1);
         }
         var _loc7_:ByteArray = new ByteArray();
         var _loc8_:FileStream = new FileStream();
         _loc8_.open(_loc6_,FileMode.READ);
         _loc8_.readBytes(_loc7_,0,_loc8_.bytesAvailable);
         _loc8_.close();
         _loc8_ = null;
         var _loc9_:String = MD5.hashBytes(_loc7_);
         if(param3)
         {
            if(_loc9_ != param3)
            {
               throw new ArgumentError("Bitswizzle overflow error on " + param1 + " [" + _loc9_ + "]");
            }
         }
         return _loc9_;
      }
```
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-04-23T10:27:45+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

moved to code talk...
## Post #5
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-04-23T13:41:15+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

> Reply from michalss
>
> moved to code talk...

Hmm, sorry for my mistake. Could you specify what is swf_md5?
In the actionscript code, there are md5 hashs for the files which is need to be checked, so verifyChecksum function will compares param 2 and 3 whether the imported file is changed or not. This function will reads bytearray of file and convert it to MD5 hash with MD5.hashbyte. So, it will also compare md5 of swf and param3. But let's look at the code.

```
swf_md5 = this.verifyChecksum("Front-Buffer subsystem W",rp + "app.game-" + appInfo.sku + ".air.swf",null);
```


So, it will reads "C:/Program Files (x86)/Steam/SteamApps/common/tbs2/win32/app.game-saga2.air.swf" and get the md5 hash of swf. But.. param3 = null.

```
         if(param3)
         {
            if(_loc9_ != param3)
            {
               throw new ArgumentError("Bitswizzle overflow error on " + param1 + " [" + _loc9_ + "]");
            }
         }
         return _loc9_;
```


So, 'swf_md5 = Bitswizzle overflow error on Front-Buffer subsystem W [c137c4232879032d888bc0edbb94dd09]'..?
But it still doesn't match the one(gamesave.bin).
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-23T14:10:55+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

its very simple.

when i said file_contents i meant get the whole file as a binary stream and hash that as binary data - which is what your function does:

```
         var _loc8_:FileStream = new FileStream();
         _loc8_.open(_loc6_,FileMode.READ);
         _loc8_.readBytes(_loc7_,0,_loc8_.bytesAvailable);
         _loc8_.close();
         _loc8_ = null;
         var _loc9_:String = MD5.hashBytes(_loc7_);

```


the function MD5.hashBytes seems to return lower-case string for these files, so the md5 value for app.game-saga2.air.swf is

> c137c4232879032d888bc0edbb94dd09

thats part 1.

the next part is to hash it again using the "salt" , which is "zabbawabba"

if you hash "c137c4232879032d888bc0edbb94dd09\r\nzabbawabba" you get

> 928f95ce47e21045537273f8cc0c34e4

which is what you gave in the game data .bin file


edit

just to clarify, \r\n are special characters, not literals.

open http://pajhome.org.uk/crypt/md5/
open the console in your webbrowser
paste Code: Select allhex_md5('c137c4232879032d888bc0edbb94dd09\r\nzabbawabba')
## Post #7
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-04-23T14:38:54+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

> Reply from WRS
>
> its very simple.

when i said file_contents i meant get the whole file as a binary stream and hash that as binary data - which is what your function does:
Code: Select all         var _loc7_:ByteArray = new ByteArray();
         var _loc8_:FileStream = new FileStream();
         _loc8_.open(_loc6_,FileMode.READ);
         _loc8_.readBytes(_loc7_,0,_loc8_.bytesAvailable);
         _loc8_.close();
         _loc8_ = null;
         var _loc9_:String = MD5.hashBytes(_loc7_);


the function MD5.hashBytes seems to return lower-case string for these files, so the md5 value for app.game-saga2.air.swf is
c137c4232879032d888bc0edbb94dd09

thats part 1.

the next part is to hash it again using the "salt" , which is "zabbawabba"

if you hash "c137c4232879032d888bc0edbb94dd09\r\nzabbawabba" you get
928f95ce47e21045537273f8cc0c34e4

which is what you gave in the game data .bin file


edit

just to clarify, \r\n are special characters, not literals.

open http://pajhome.org.uk/crypt/md5/
open the console in your webbrowser
paste Code: Select allhex_md5('c137c4232879032d888bc0edbb94dd09\r\nzabbawabba')

That's the one that I firstly expected but.. look at this. (I'm not sure what do you mean 'open the console' yet.) I just put 'c137c4232879032d888bc0edbb94dd09\r\nzabbawabba' in to 'input'.


And the result is 
> 45c09947d609595d82f483b87781d649 Not a 
> 928f95ce47e21045537273f8cc0c34e4
## Post #8
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-04-23T14:55:22+00:00
- Post Title: Getting MD5 hash from actionscript of swf.

Ah.. I got it. Thank you!
