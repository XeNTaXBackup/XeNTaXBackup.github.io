## Post #1
- Username: ccworks
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 25, 2023 10:10 pm
- Post datetime: 2023-04-27T13:28:22+00:00
- Post Title: [Unity]text extraction issues in game "Soccer Spirits"

Hello ,
Thank you for reading my post. I am a newcomer and am currently encountering some difficulties and hope to get help.
Since my English is not good, the following are documents translated by New Bing. If there are any unclear parts, please let me know and I will try to supplement them.

This is a game from 2014, almost 10 years ago.I’m worried that it will shut down at any time.

Game Infomation:

Game name: Soccer Spirits
package name:com.com2us.soccerspirits.normal2.freefull.google.global.android.common
Google Play Link:[https://play.google.com/store/apps/deta ... l=en&gl=US](https://play.google.com/store/apps/details?id=com.com2us.soccerspirits.normal2.freefull.google.global.android.common&hl=en&gl=US)

Recently, I have been extracting resources from this game. Fortunately, the game’s art assets were not encrypted and I was able to quickly extract them using AssetStudio. 

However, I soon discovered that AssetStudio was unable to extract the game’s text, such as the main story and character descriptions.I checked the TextAssets and some Monobehavior
[](https://ibb.co/1s38czY)

I tried to find the relevant files and discovered that a file under a DB folder might contain text information. When I opened it with 010 editor, just saw some random characters.
Here is a sample file:

 chainstory_11239.zip
(2.7 KiB) Downloaded 16 times


And full DB folder zip:[https://mega.nz/file/kF0BSZJY#Z80CWh9kY ... 54E5CanmGM](https://mega.nz/file/kF0BSZJY#Z80CWh9kYXr6v0hyFLwNQhdXJrIfqelrZ54E5CanmGM)
[](https://ibb.co/YDqmQT0)

I tried to analyze it using dnSpy and IDA, but my skills are too poor and I don’t know much about C language and assembly language, so I can only guess some simple situations.Despite looking at it for an entire evening, there were no good results.

Here is the questions：
1. Are these some kind of standard Unity files? If so, how can I read them?
2. If not, how to obtain the method to read it?
