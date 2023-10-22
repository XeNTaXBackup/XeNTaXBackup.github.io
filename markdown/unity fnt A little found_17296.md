## Post #1
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-11-17T03:13:20+00:00
- Post Title: unity fnt A little found

Not you can not find him; he can be any type * 7 *. 144 *.-44 ~~~~~~~~~~and so on
So you need to look for a possible, he between 3 KB - 10 KB is limited to the size of the ASCII code, if Asia may be large
Parse the data

Fnt The XML data

```
id="33" x="2034" y="626" width="6" height="21" xoffset="1" yoffset="5" xadvance="8" page="0" chnl="15" 
```


bmfont Binary data （length of 20）*（page= truncation）

```
21 00 00 00/F2 07 72 02 /06 00 15 00/01 00 05 00/08 00 00 0F
```


```
ID=21 00 00 00/X=F2 07/Y=72 02/W=06 00/H=15 00/ xoffset=01/ yoffset=05 00/ xadvance=08 00/ chnl=00 15
```


How to calculate the column

```
ID=0021=33/X=07F2=2034/Y=0272=626/W=0006=6/H=0015=21…………
```


Type 2

ID is an integer
The remainder is a floating number

Game fnt file（length of 32）（chnl=truncation）

```
21 00 00 00 /00 00 B7 43 /00 80 BE 43 /00 00 7A 41 /00 A0 63 42 /00 00 22 40/00 C0 63 42 /00 80 9B 41
```


```
ID=0021=33/x=43B70000=366/Y=43BE8000=381/W=417A0000=15.625/H=4263A000=56.90625/page=40220000=2.53125/Xoffset=4263C000=56.9375/yoffset=419B8000=19.4375
```


May not be very correct but would like to help other people
[20171117170052.png](https://xentaxbackup.github.io/file/13552_20171117170052.png)
## Post #2
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-11-17T05:42:27+00:00
- Post Title: unity fnt A little found

Here said that a new type of computing

Game fnt file（length of 36）（xadvance=truncation）

```
34 00 00 00/00 C0 2F 44/00 80 EC 43/00 80 61 42/00  A0 91 42/00 00 54 40/00 A0 91 42 /00 80 7C 42/00 00 80 3F/
```


```
ID=34 00 00 00/X=00 C0 2F 44/Y=00 80 EC 43/W=00 80 61 42/H=00  A0 91 42/page=00 00 54 40 /xoffset=00 A0 91 42/yoffset=00 80 7C 42/chnl=00 00 80 3F
```


Calculate Please use the floating point

```
ID=52/X=442FC000=703/Y=43EC8000=473/W=42618000=56.375/H=4291A000=72.8125/page=40540000=3.3125/xoffset=4291A000=72.8125/yoffset=427C8000=63.125/chnl=3F8000=1
```
## Post #3
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-12-01T06:26:20+00:00
- Post Title: unity fnt A little found

OK, so you want edit or change or add new characters in font, right?
Hex is a best way (not always!) Its different in some type of engine's
in this years, i just edit and make tools and use translate on unity games, wich used TTF font in data. unknow textures is (A8 dds) in new UNITY Games (this make work hard in header)
Fonts are Fnt?!?!?!    Right? is that true?  
tell me more, maybe i can help more to edit that file
## Post #4
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-12-01T06:54:39+00:00
- Post Title: unity fnt A little found

> Reply from GHOST DEAD
>
> OK, so you want edit or change or add new characters in font, right?
Hex is a best way (not always!) Its different in some type of engine's
in this years, i just edit and make tools and use translate on unity games, wich used TTF font in data. unknow textures is (A8 dds) in new UNITY Games (this make work hard in header)
Fonts are Fnt?!?!?!    Right? is that true?  
tell me more, maybe i can help more to edit that file

Unity font is a two-part is a dds graphics fonts There is a fnt file contains all the information dds graphics fonts
Alright forgive me for lazy English
First of all, I can only know what part of the data? It is important that his header data include the size of the grid as well as the number of characters and the size of the font. It takes a lot of time to know the exact data  The same calculation is not int is a float But you can only know that the data can not accurately determine that he is the part of the data
I hope you completed the development of this software to benefit more translators
This is what I wrote a simple template adjustment Can analyze the length of fnt 32-40 can get the value

```
//
//      File: 
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------
LittleEndian();
typedef struct{
SetBackColor(cLtRed);
int ucode;
SetBackColor(cLtBlue);
float x;
SetBackColor(cLtGreen);
float y;
SetBackColor(0xA020F0);
float w;
SetBackColor(0x9BCD9B);
float h;
SetBackColor(0xEEEE00);
float page;
float xoffset;
float yoffset;
}block;

SetBackColor(0x112266);
char uni[0xb4];
int empty;
SetBackColor(0x0000ff);
int num;
block b[num];
char uni2[320];
```
## Post #5
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-12-01T07:20:32+00:00
- Post Title: unity fnt A little found

> Reply from GHOST DEAD
>
> OK, so you want edit or change or add new characters in font, right?
Hex is a best way (not always!) Its different in some type of engine's
in this years, i just edit and make tools and use translate on unity games, wich used TTF font in data. unknow textures is (A8 dds) in new UNITY Games (this make work hard in header)
Fonts are Fnt?!?!?!    Right? is that true?  
tell me more, maybe i can help more to edit that file

There is a failure I wrote written in C #, it is not written Well I am stupid to give you a little

```
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace Projects1
{
    class Program
    {
        static void Main(string[] args)
        {
            while (true)
            {
                Console.Write("输入要转换的文件路径(可以使用相对路径)：");
                string path = Console.ReadLine().Trim();
                StartConvert(path, 8);
                path = Path.GetFileName(path) + "_convert.txt";
                Console.WriteLine($"结果已输出到{path}");
            }
        }
        /// <summary>
        /// 将一个指定格式的文件的内容转换为指定内容。<para/>每行第一个为 <see cref="int"/> 类型，其余全为 <see cref="float"/> 类型。
        /// </summary>
        /// <param name="path">文件路径。可以使用相对路径。</param>
        /// <param name="lineNumber">每行要转换的总个数</param>
        /// <param name="start">分割后的起始位置。</param>
        /// <param name="speed">步长。每隔几个数据需要转换。</param>
        public static void StartConvert(string path, int lineNumber = 8, int start = 1, int speed = 2)
        {
            path = Path.GetFullPath(path); //获取绝对路径(并不是必要的)
            string[] data = File.ReadAllText(path).Split('\"'); //读取文本内所有数据并按"分割
            int flag = 0; //标记。是否为第一个数据/ int 类型 否则 float 类型
            for (int i = start; i < data.Length; i += speed) //开始循环 其实位置指定 长度为数组长度 步长指定
            {
                if (flag % lineNumber == 0) //如果是每行第一个 
                {
                    int num = Convert.ToInt32(data[i]); //转换成 int 类型
                    var b = BitConverter.GetBytes(num); //转换成字节数组
                    data[i] = BitConverter.ToString(b).Replace("-", ""); //转换成字符并去掉所有-符号
                }
                else //否则转换成 float 类型
                {
                    float num = Convert.ToInt32(data[i]); //转换成 float 类型
                    var b = BitConverter.GetBytes(num); //转换成字节数组
                    data[i] = BitConverter.ToString(b).Replace("-", ""); //转换成字符并去掉所有-符号
                }
                flag++; //计数
            }
            StringBuilder stringBuilder = new StringBuilder(); //可变字符串 拼接速度快
            foreach (var s in data) //遍历 data 数组
            {
                stringBuilder.Append(s + "\""); //将内容拼接在一起并加上"号
            }
            File.WriteAllText(path + "_convert.txt", stringBuilder.ToString()); //写入文件
        }
    }

    
}
```
## Post #6
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-12-02T04:25:58+00:00
- Post Title: unity fnt A little found

asian characters? can you please, translate asian words in english? (in Console script)
