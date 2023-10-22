## Post #1
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2015-08-22T13:20:06+00:00
- Post Title: Batman Arkham Knight subtitles

Hi! I'm currently making a hungarian translation to Batman Arkham Knight and i want to know which files holding the subtitles. If anybody knows, please help me.
## Post #2
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-08-25T01:45:37+00:00
- Post Title: Batman Arkham Knight subtitles

> Reply from deneverfaszu
>
> Hi! I'm currently making a hungarian translation to Batman Arkham Knight and i want to know which files holding the subtitles. If anybody knows, please help me.

I founded subtitle text in usm video. But i can not see subtitle text ingame.
## Post #3
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2015-08-25T10:56:55+00:00
- Post Title: Batman Arkham Knight subtitles

And how did you open those usm files?
## Post #4
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-08-27T07:59:57+00:00
- Post Title: Batman Arkham Knight subtitles

> Reply from deneverfaszu
>
> And how did you open those usm files?

I open those usm file by hex editor and edit handmade!
## Post #5
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-11T00:52:17+00:00
- Post Title: Batman Arkham Knight subtitles

Up.
## Post #6
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2016-04-10T15:30:58+00:00
- Post Title: Batman Arkham Knight subtitles

Meanwhile I got a tool for unpacking and repacking upk files, it works fine and I can translate the in-game texts but the thing is, it only works with Arkham Origins.  
If somebody has a little knowledge of programming or knows how unreal engine's in-game texts are working, please help me to make it compatible with Arkham Knight.

Message me and i will send the tool.
## Post #7
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2016-08-07T17:04:07+00:00
- Post Title: Batman Arkham Knight subtitles

Well, I have a tool for Arkham Knight, but the new problem is I can't extract the texts from the .usm files. I know it could be done without extracting and editing by a hex editor, but I don't want that because hex editing usually messes up the files.

I have a tool for .usm files, but this one's for Arkham Origins too.

If somebody can make a working version for Arkham Knight, please let me know and I'll send the tool.
I would really appreciate that.
## Post #8
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-07-06T00:55:41+00:00
- Post Title: Batman Arkham Knight subtitles

Up. 
I need the unpack/repack .usm files.
Please, help!
## Post #9
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2017-07-25T23:13:03+00:00
- Post Title: Batman Arkham Knight subtitles

So the thing is the Arkham Origins usm extractor works, now only the repacker needs be fixed for AK.
Anyone a little help?  

Repacker's source code:

```
//--- 010 Editor v3.2.2 Script File
//
// File: usm injector
// Author: celikeins
// Revision: 0.88
// Purpose: repack usm files 
//--------------------------------------

int detSize( int  osize, int  size)
    {
		int base1 = 0x2C,base2=0x2C;
        while(base1<osize) base1+=0x20;
		while(base2<size) base2+=0x20;
		return base2-base1;

    }

uint KEY=1413632832;
ushort newl=2573;
uint sized; 
int i,j,aux,res,tsize,otsize,cur,out,cnt;

uchar buffer[0xFFF];
string txt;
TFindResults r;
TFileList fl = FindFiles( GetArg(0), "*.usm" );
Printf("%d",fl.filecount);
for(j=0;j<fl.filecount;j++)
{
			cnt=3;
			cur=FileOpen(GetArg(0)+"\\"+fl.file[j].filename);

			out=FileOpen(GetArg(0)+"\\usm_txts\\"+fl.file[j].filename+".txt");
			FileSelect(cur);
			r = FindAll( KEY);
			for( i = 3; i < r.count-1; i++ ){
                if(ReadInt(r.start[i]+0x20)==0){
					otsize=ReadInt(r.start[i]+0x30);					
					FileSelect(out);
					txt=ReadString(cnt); 
					tsize=Strlen(txt); cnt+=(tsize+2+2);
					FileSelect(cur);
					aux=detSize(otsize,tsize+2);					
					if(aux>0){
					    InsertBytes(r.start[i]+0x34+otsize,aux );
					    BigEndian();
						res=ReadInt(r.start[i]+4);
						WriteInt(r.start[i]+4,res+aux);
						LittleEndian();
					}
					ConvertDataToBytes(txt,buffer);
					WriteInt(r.start[i]+0x30,tsize+2);
                    buffer[tsize+1]=0;
					WriteBytes(buffer,r.start[i]+0x34,tsize+2);												
					FileSelect(cur);
				}									
			}
			FileSelect(out);
			FileClose();
			FileSelect(cur);
			FileSave();
			FileClose();
}
//Terminate();
```
## Post #10
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2019-11-27T09:34:34+00:00
- Post Title: Batman Arkham Knight subtitles

any update .. i need tool for batman arkham knight text fonts edit .. please help.
