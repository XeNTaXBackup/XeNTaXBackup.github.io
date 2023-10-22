## Post #1
- Username: Blaconix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 20, 2019 1:41 am
- Post datetime: 2019-04-19T18:48:53+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

Hello,

I'm having quite some trouble decompressing/parsing .dat files of Hi-Rez's custom modified UE3 engine which powers SMITE, Paladins and Realm Royale, so I decided to open a generalized thread to handle this kind of files.

Based on my research, the two most important files for those games are:
Lang_INT.dat - localization file, located in %game_folder%\Localization\INT
assembly.dat - core file putting everything together %game_folder%\CookedPCConsole

There have been previous threads which discussed the localization file, I will now combine what I've learned from those and what I have discovered on my own.

Let's learn a bit about the files (take note those are my findings and could be completely wrong, I am not an expert, nor average at reversing unknown files). I'll also be quoting Laooo, which is known in the UC community.

> Hi-Rez uses the same format to store and transmit data. They call it "Marshal" - marshalling means transforming any object to data that can be stored to the disk (file) or sent over the wire (game packets).
>
> The data is stored in form of rows. It looks like this:
>
> https://i.vgy.me/h9FXXm.png
>
> 
>
> It's an extremely flexible format that consists of rows, fields and sets of rows. These row sets can in turn store more rows, etc. A row contains fields, each of which is defined by an ID which is stored in a large array of IDs that contains information about what type of value they're supposed to hold (is it a string? an integer? a floating point? a boolean?), among others.
>
> 
>
> Two important files in the game folder use this format: Lang_INT.dat and assembly.dat. Lang_INT.dat (or Lang_CHN, Lang_FRA depending on the language) contains every single localized string in the game, Each row contains the message ID, the version ID, the message's "type", the message itself, etc.. so all you need to do is loop through all the rows and get each message.
>
> 
>
> assembly.dat is what I would call the "core" of the game. It's basically the game's local database: contains item definitions, stats, tips, etc.. there are over 14 types of data.

What about actually parsing them? They are XORed by 0x2A.
After unxoring, the strings become readable (every character is two bytes, with the string length prefixed to them).

Thus, Lang_INT.dat becomes quite nice to parse and edit if you'd like to do localization.
Now, the big boy assembly.dat is the challenge. After going through the same steps I ended up with readable strings, but that's pretty much it. I have no idea where to go from here, how to actually make stuff out of what seem like random bytes.

At the end of assembly.dat we can see the actual export which converted Marshall to a format the game can understand:
DBExport: 01/29/2019 9:24:51, Src=devsql.hirezcorp.com:game_build_server_0_14, LangSrc=devsql.hirezcorp.com:game_translations

Here are assembly.dat and Lang_INT.dat links for Hi-Rez's newest game (Realm Royale), uploaded as of making this post:
[assembly.dat](https://blaco.s-ul.eu/qvr8JitA)
[Lang_INT.dat](https://blaco.s-ul.eu/kqUq5FLl)

(as a sidenote, even if the files are from Realm Royale they seem to be containing strings and data from the other two games as well, which is pretty strange if you ask me)

Also, here's a quick python script to unxor by 0x2A.

```
import sys

f = open(sys.argv[1], "rb")
o = open(sys.argv[2], "wb")

data = f.read()
for d in data:
    o.write("" + chr (ord(d) ^ 0x2a))

f.close()
o.close()
```


That pretty much concludes my adventure with this kind of files. I don't think I can get any further by myself, so I am kindly asking for help. Any kind of suggestion matters. Thanks!
## Post #2
- Username: jackfrost
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2022 9:38 am
- Post datetime: 2022-04-08T01:44:48+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

```
import sys

f = open(sys.argv[1], "rb")
o = open(sys.argv[2], "wb")


data = f.read()
for d in data:
    o.write("" + chr (ord(d) ^ 0x2a))

f.close()
o.close()
```

How to use this code?
I tried dragging the lang.dat file to the py file, but it doesn't work.
## Post #3
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-08T05:37:13+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

```
python python_script.py file_to_read file_to_write
```
## Post #4
- Username: jackfrost
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2022 9:38 am
- Post datetime: 2022-04-08T07:04:17+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

I've just recently studied Python, so I don't understand.
What does this mean how to use?
## Post #5
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-08T11:05:25+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

It's a CMD line ...
Check [PythonForBeginners](https://www.pythonforbeginners.com/development/how-run-your-python-scripts#:~:text=To%20run%20Python%20script%20using%20a%20Python%20Text,typically%20would%20from%20a%20command%20line%20interface%20execution.) for more info.
## Post #6
- Username: jackfrost
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2022 9:38 am
- Post datetime: 2022-04-08T11:09:01+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

Thanks for the good info!
## Post #7
- Username: jackfrost
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2022 9:38 am
- Post datetime: 2022-05-31T09:23:00+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

I succeeded in decoding with quickbms.
However, I would like to get help in making a custom hexadecimal table.
## Post #8
- Username: SmartBar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2022 3:45 pm
- Post datetime: 2022-06-19T08:33:41+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

> Reply from jackfrost ↑Tue May 31, 2022 5:23 pm at Tue May 31, 2022 5:23 pm
>
> 
I succeeded in decoding with quickbms.
However, I would like to get help in making a custom hexadecimal table.

Hello, someone has debugged game and figured out how it reads assembly.dat
Here is some structure she told us

```
  uint16_t tag;
  void* data;
  /*
    Tag is 2 components:
      Token = Tag >> 24
      Param = Tag & 0x3F
    Token describe the format:
      1: 8-bit int (byte)
      2: 16-bit int (short)
      3: 32-bit int (int)
      4: 64-bit int (long)
      5: unused?
      6: dataset
      7: uuid
      8: blob
      9: utf-8 string
      10: utf-16? string
  */
};

struct row_data_1 {
  uint16_t fieldId[tag & 0x3F];
  uint8_t values[tag & 0x3F];
}

struct row_data_2 {
  uint16_t fieldId[tag & 0x3F];
  uint16_t values[tag & 0x3F];
}

struct row_data_3 {
  uint16_t fieldId[tag & 0x3F];
  uint32_t values[tag & 0x3F];
}

struct row_data_4 {
  uint16_t fieldId[tag & 0x3F];
  uint64_t values[tag & 0x3F];
}

struct row_data_6 {
  uint16_t fieldId;
  uint16_t length;
  if(length == 0xFFFF) {
    uint32_t length;
  }
  row* rowset;
}

struct row_data_7 {
  uint16_t fieldId;
  uint8_t uuid[16];
}

struct row_data_8 {
  uint16_t fieldId;
  uint16_t length;
  if(length == 0xFFFF) {
    uint32_t length;
  }
  uint8_t blob[length];
}

struct row_data_9 {
  uint16_t fieldId;
  uint16_t length;
  TCHAR text[length];
}

struct row_data_10 {
  uint16_t fieldId;
  uint16_t length;
  WCHAR text[length];
}

struct rowset_t {
  short rowCount;
  row_t rows[rowCount];
}

struct header_t {
  uint8_t unknown;
  uint32_t fileId;
  rowset_t rows;
};

```

Maybe that can help you. Also I can invite you to discord server where this conversation took place.
Is it necessary to write script to use QuickBMS, right? You can share your groundwork, I wanna try to understand it myself, cause I too bad at it right now
## Post #9
- Username: jackfrost
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2022 9:38 am
- Post datetime: 2022-06-20T06:03:33+00:00
- Post Title: Hi-Rez Games .dat file [SMITE, Paladins, Realm Royale]

Can you invite me?
