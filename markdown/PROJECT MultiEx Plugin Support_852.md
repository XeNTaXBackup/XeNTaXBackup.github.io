## Post #1
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-11T20:49:39+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Thought I'd make a topic for this too, "code submission" is a little vague.

Ok, working on the Plugin Manager (the glue between Mexcom and the Plugins)

```
function GetManagerVersion(var Major, Minor: Integer): Boolean; stdcall;

// To Get the supported interface version
function GetSupportedInterfaceVersion(var Major, Minor: Integer): Boolean; stdcall;

// Allows the calling process to select the directory of the plugins
//    This way multiex can store the plugin path whereever it wants
//    Should always be called once
function SetPluginDirectory(Directory: PChar): Boolean; stdcall;

// This refreshes the plugin list, also must be called to load for the first time too
function RefeshPluginList(): Boolean; stdcall;

function PluginCount(): Integer; stdcall;

function PluginInfo(Index: Integer; var PluginInfo: TPluginInfo): Boolean; stdcall;

// TPluginInfo so far is defined as
type
  TPluginInfo = packed record
    Size: Integer;
    PluginName: PChar;     // Module Name (to be displayed)
    PluginFullPath: PChar;  // Full path to the plugin module
    VersionMajor, VersionMinor: Integer;
    InterfaceMajor, InterfaceMinor: Integer;
    Supported: Boolean;    // This allows us to show Unsupported plugins in the list
  end;
```


This information is mainly ment for display purposes to a user.  And Except for GetManagerVersion, should not be USED in coding.  The plugin manager will handle all supported and unsupported versions automatically.  This also lets plugin developers see what mexcom's plugin manager sees.
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-11T20:56:35+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Mr. Mouse, also, feel free to voice your opinions and/or ideas.  Maybe something you want mexcom to do or to provide.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-11T21:15:41+00:00
- Post Title: PROJECT: MultiEx Plugin Support

I most certainly will!   
There's been some criticism on the Painkiller.dll, and one thing that bugs me is that the Commander can't yet create these pak files from scratch. 
I will have to find time to implement stuff like that, but before I can, the Plugin Manager will have to be operational. There's no rush, by the way, this is not a push! Take your time, it's best to have something good, that took some time eh.
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-11T21:34:59+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Yeah, we have a saying at work  "Good, Fast, Cheap.  Pick any 2".

Good and Fast = Not Cheap
Good and Cheap = Not Fast
Cheap and Fast = Not Good
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T13:34:37+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Mr. Mouse, can you make me 2 vb programs for testing.

Something really simple

Program 1:

Create a program with 3 buttons on it,
  1) imports a function from "test.dll" called "TestFunction1" and calls it. Function has a parameter of a String returns a Long/Integer.
  2) imports a function from "test.dll" called "TestFunction2" and calls it.  Function has a parameter of an array of long/integer, returns a long/integer.
  3) imports a function from "test.dll" called "TestFunction3" and calls it.  Function has a parameter of an array of string, returns a long/integer.

Program 2:

Create a program with 3 buttons on it,
  1) import a function from "testcall.dll" called "TestFunction1" and calls it.  Function has a parameter of a pointer/reference to a function that takes a paramter of a string and returns a long/integer.
  2) imports a function from "test.dll" called "TestFunction2" and calls it.  Function has a parameter of a pointer/reference to a function has a parameter of an array of long/integer, returns a long/integer.
  3) imports a function from "test.dll" called "TestFunction3" and calls it.  Function has a parameter of a pointer/reference to a function has a parameter of an array of string, returns a long/integer.

Thx for your time.

This is for me to see how VB6 passes data back and forth between DLLs, and to see how i can make VB6 call backs.  Esp with strings and arrays.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T13:39:47+00:00
- Post Title: PROJECT: MultiEx Plugin Support

I'll see what I can do on short notice. I'm @work at the mo', so it will have to wait until I get home, and have time there. Pleasing the mrs. and raising the dog can be quite time-consuming, let alone a bunch of other hobby chores that await me.
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T14:08:22+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Np, i didn't mean this instant.  Oh yeah, call called programs use the standard API calling method, incase you need that.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T14:25:05+00:00
- Post Title: PROJECT: MultiEx Plugin Support

> Reply from Rahly
>
> Np, i didn't mean this instant.  Oh yeah, call called programs use the standard API calling method, incase you need that.

Ok!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-14T08:30:38+00:00
- Post Title: PROJECT: MultiEx Plugin Support

> Reply from Rahly
>
> Mr. Mouse, can you make me 2 vb programs for testing.

Something really simple

Program 1:

Create a program with 3 buttons on it,
  1) imports a function from "test.dll" called "TestFunction1" and calls it. Function has a parameter of a String returns a Long/Integer.
  2) imports a function from "test.dll" called "TestFunction2" and calls it.  Function has a parameter of an array of long/integer, returns a long/integer.
  3) imports a function from "test.dll" called "TestFunction3" and calls it.  Function has a parameter of an array of string, returns a long/integer.

Program 2:

Create a program with 3 buttons on it,
  1) import a function from "testcall.dll" called "TestFunction1" and calls it.  Function has a parameter of a pointer/reference to a function that takes a paramter of a string and returns a long/integer.
  2) imports a function from "test.dll" called "TestFunction2" and calls it.  Function has a parameter of a pointer/reference to a function has a parameter of an array of long/integer, returns a long/integer.
  3) imports a function from "test.dll" called "TestFunction3" and calls it.  Function has a parameter of a pointer/reference to a function has a parameter of an array of string, returns a long/integer.

Thx for your time.

This is for me to see how VB6 passes data back and forth between DLLs, and to see how i can make VB6 call backs.  Esp with strings and arrays.

Can you also give me the test.dll? Or should I create one. I must make sure the program does what it is supposed to do. 

Though you can just try these, scroll down for the download:

> Reply from testapp1
>
> 
MODULE :
Public Declare Function TestFunction1 Lib "test.dll" (ByVal str As String) As Long
Public Declare Function TestFunction2 Lib "test.dll" (ByRef arrLong() As Long) As Long
Public Declare Function TestFunction3 Lib "test.dll" (ByRef arrStr() As String) As Long

FORM:
Private Sub Command1_Click()
'Call
Dim John As Long
John = TestFunction1("ZuurmanRulez")
End Sub


Private Sub Command2_Click()
'Call
Dim Anita As Long
Dim John() As Long
ReDim John(10)
John(0) = 15
John(1) = 255
John(2) = 1023

Anita = TestFunction2(John)
End Sub


Private Sub Command3_Click()
'Call
Dim John As Long
Dim You() As String
ReDim You(10)
You(0) = "Mike"
You(1) = "Zuurman"
You(2) = "Was"
You(3) = "Here"
John = TestFunction3(You)
End Sub

> Reply from testapp2
>
> 
Public Declare Function TestFunction1 Lib "testcall.dll" (ByVal ptrFunc As Long) As Long
Public Declare Function TestFunction2 Lib "testcall.dll" (ByVal ptrFunc As Long) As Long
Public Declare Function TestFunction3 Lib "testcall.dll" (ByVal ptrFunc As Long) As Long


Public Function myFunc(str As String) As Long

myFunc = Len(str)
End Function

Public Function myFunc2(arrLong() As Long) As Long

myFunc2 = UBound(arrLong)
End Function

Public Function myFunc3(arrStr() As String) As Long

myFunc3 = UBound(arrStr)
End Function

Public Sub Command1_Clicked()
'Call
Dim John As Long
John = TestFunction1(AddressOf myFunc)
End Sub


Public Sub Command2_Clicked()
'Call
Dim Anita As Long

Anita = TestFunction2(AddressOf myFunc2)

End Sub


Public Sub Command3_Clicked()
'Call
Dim Anita As Long

Anita = TestFunction3(AddressOf myFunc3)
End Sub
[testapp.zip](https://xentaxbackup.github.io/file/53_testapp.zip)
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-14T14:43:33+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Thanks, the first program works great.  I need to write the DLL for the second one.  I just wanted to see how VB passed Strings and Arrays to functions.  I had thought that it passed strings as PWideChars which is the native strings in VB, but it infact converts them PChars using OLE automation.  Now i need to find how how to call a function
## Post #11
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T02:21:33+00:00
- Post Title: PROJECT: MultiEx Plugin Support

decided to remove GetVersion from the plugin, replaced it will GetPluginInfo(var PluginInfo: TPluginInfo);

```
    // Version 1.0
    Size: Integer;
    Name: PChar;
    Author: PChar;
    Major: Integer;
    Minor: Integer;
  end;
  
function mpGetPluginInfo(var Info: TPluginInfo): Boolean; stdcall;
```


This allows information such as a plugin name and the name of the author,  All information this function provides is for display or informational purposes only, and my no means, should be used in conditional coding, use the Interface Version number for conditional testing.
## Post #12
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T04:40:39+00:00
- Post Title: PROJECT: MultiEx Plugin Support

```
var
  Count: Integer;
  MyPlugInfo: TPluginInfo;
  MyStr: String;
begin
  ListBox1.Items.Clear;
  RefreshPluginList();
  ListBox1.Items.Clear;
  For Count := 0 to PluginCount()-1 do
    begin
    MyPlugInfo.Size := SizeOf(MyPlugInfo);
    if PluginInfo(Count, MyPlugInfo) then
      begin
      MyStr := String(MyPlugInfo.PluginName) + ' (' + ExtractFilename(String(MyPlugInfo.PluginFullPath)) + ' ' + IntToStr(MyPlugInfo.VersionMajor) + '.' + IntToStr(MyPlugInfo.VersionMinor) + ') by '+ MyPlugInfo.PluginAuthor;
      if Not(MyPlugInfo.Supported) then
        MyStr := MyStr + ' (Not Supported)';
      ListBox1.Items.Add( MyStr );
      end;
    end;
end;
```


Sample code for getting plugin information and showing the user.  See attached picture.  This procedure is the code for the "Refresh" button.

Also, i'm thinking of adding, in the plugin, a URL and email field.  Possibly for support reasons of the plugin.
[plugin.jpg](https://xentaxbackup.github.io/file/56_plugin.jpg)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-17T12:10:12+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Looking good!
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T17:09:57+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Current I have plugin information completed.  Here is the manager dll with the ability to get a list of plugins and plugin information, if you wanna test it, or start that functionality in mexcom.  You can bind statically to this dll.

How it should work.

On startup

1. mexcom calls GetManagerVersion to get the version of the manager dll, alert the user if its not the version your looking for and exit OR ignore, continue if its the right version

2. call SetPluginDirectory to set the path for the plugins for the manager to use

3. call RefreshPluginList to find all available plugins (Initial Plugin Load)

Where you want to display a list of the plugins

1. Call PluginCount to get a count of plugins

2. Call PluginInfo with an index of 0 to (PluginCount-1) to get information for a plugin.

Whenever you want to refresh the a list of the plugins call RefreshPluginList.
## Post #15
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T17:18:00+00:00
- Post Title: PROJECT: MultiEx Plugin Support

Didn't post the file GRRR.

Common.pas is a file with all the common types and constants.

Unit3.pas is a sample file of imported static functions from PluginManager.dll

PluginManager.dll is the plugin manager(if you couldn't guess )

BFFileFormat.mxp is a good plugin (supported)

Unsupported.mxp is a bad plugin (unsupported)
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T17:51:50+00:00
- Post Title: 

Working on the plugin manager to add phase 2, code to call the plugins to actually do the work.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-17T18:19:32+00:00
- Post Title: 

Allright, thanks, I sure will test it sometime soon.
## Post #18
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-17T18:52:26+00:00
- Post Title: 

Adding a small feature to the plugin system.  New function for plugins in general.


function mpInUse():Boolean; stdcall;

basically this function will return if the plugin is in use, like if there are open archive handles(Someone called mpOpenArchive and hasn't called mpCloseArchive yet).  What this will do, is allow the Plugin manager to know who is still in use, without having to keep track of it.

Steps

1. Plugin Manager needs to make a call into the plugin, checks its list of loaded plugins to see if its available, if so, calls the function it needs to.

2.  if the plugin is not loaded yet, manager tests open plugins to see if they are "IN USE", and if not, unloads them,  this keep loaded code down to a minimum(you don't wanna load ALL), and if DONE in a generic mannor, the plugin manager SHOULD only have one plugin loaded at any one time.  After cleanup dll code is run, loads a plugin into memory

This will be a required function of the plugin system, in order for it to be considered a supported plugin.

[EDIT]Note: I'm not unloading on the close, that way, if you are working with bulks of the same file, it doesn't reload the same plugin over and over again.  Also, I might add a function to the manager CachePlugin(Index), so that you can keep a certain plugin loaded, but i don't know what reasons, you would use this though[/EDIT]
## Post #19
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-22T01:45:17+00:00
- Post Title: 

lol Mr Mouse, at least you don't have to deal in this type of basic

```
00035 VIEWMAINT1: SETERR ERREXIT; FORMAT INCLUDE #IDVIP ,OPT="NONE"; LET USRTYP$=#IDSV.VIEW-USER-MODE , OLS$="Y"; IF #IDVIP.FVIEWS="Y" THEN LET GUI$="Y" FI; LET ]SYSV$=#IDSV , JAVA$=#IDVIP.JAVA-ON , NO$=#IDSV.NO-CHAR , YS$=#IDSV.YES-CHAR , Y2KBASE=#IDSV.Y2KBASE, MSG$[0]="", M=NEA("MSG$",1), WNR$="WRITE NEWR", WMR$="WRITE MODR", GTR$="GOTO *", INV$="INDENTV", FK$="X"; IF M<27 THEN INSERT ARRAY MSG$[(M+1,27-M)] FI; LET UDH$=MSG$[22], TMP$=MSG$[21], DNL$=MSG$[23], RVV$=MSG$[24]; IF NMV(RVV$) THEN LET RVV=INT(NUM(RVV$)) FI; LET X=0; DIM X$[3]; WHILE STL(TMP$) AND X<=3; LET P=POS(","=TMP$); IF P<>0 THEN LET X$[X]=TMP$(1,P-1), TMP$=TMP$(P+1), X=X+1 ELSE LET X$[X]=TMP$, X=4 FI; WEND ; FOR X=0 TO 3; IF LEN(X$[X])<>0 THEN IF NMV(X$[X])=0 OR NUM(X$[X])<0 OR FPT(NUM(X$[X]))<>0 THEN LET X$[X]="" FI FI; NEXT X; LET UDCOLS$=X$[0], UDROWS$=X$[1], UDCOL$=X$[2], UDROW$=X$[3]; DIM X$[0]; LET FS18$=#IDSV.FILE-SUFFIX , FS18V$=CVT(MSG$[18],136); IF FS18V$="" THEN LET FS18V$=FS18$ FI; IF MSG$[2]<>"" AND NMV(MSG$[2]) THEN LET RETST$=STR(NUM(MSG$[2])), MSG$[2]="" FI; DIM MA$[9]; LET MA$[0]="IDMSGS1"; LET MA$[9]="C "+CHR(80)+$000000$+DIM(8); IF MSG$[16]<>"" THEN SETESC VIEWEXIT; LET W$=MSG$[16], CM1$=W$(1,1); IF CM1$<>"S" THEN LET CM2$=W$(2,1); IF CM1$="c" THEN IF STL(W$)>3 THEN LET W=ASC(W$(3,1)), CMH$=W$(W+4) FI ELSE IF STL(W$)<10 THEN LET W$=PAD(W$,10) FI; LET CML$=W$(3,8), CMH$=W$(11) FI ELSE IF STL(W$)<3 THEN EXIT ELSE LET FSR=1, SUM=ASC(W$(2,1)); IF SUM+2>STL(W$) OR SUM=0 THEN EXIT FI; LET SUM$=W$(3,SUM), CMH$=W$(SUM+3); DIM SUM[SUM*7],SUM$[SUM*7] FI FI FI; IF CM1$="L" THEN LET CM1$="", CM2$="" FI; IF CM1$="P" THEN DIM PT$[3]; CALL "8OPENP","R O",PT$[ALL],PCH,]SYSV$; LET #IDSV =]SYSV$; IF PCH=0 OR CTL=4 THEN EXIT FI; LET HCL=#IDSV.PRINTER-LNPERPG , VPN=0 FI; IF RVV AND MSG$[1]="" THEN LET MSG$[0]="V"; GOTO CUEXIT FI; WHILE MSG$[1]=""; LET HELP$="OOVWNAM1"; GOSUB MSG; LET FK=CTL; LET Y$=CVT(]INP$[1],128); IF FK=0 THEN LET MSG$[1]=Y$ FI; IF FK=2 THEN DIM TMP$[14]; LET TMP$[1]="OOVIEW", TMP$[4]="V"+Y$, TMP$[9]="F", TMP$[10]="E"; CALL "OO3A",TMP$[ALL]; IF TMP$[2]<>"" THEN LET MSG$[1]=CVT(TMP$[2](2),128) FI; DIM TMP$[0] ELSE IF FK=4 THEN GOTO CUEXIT ELSE IF FK=9 THEN DIM SRM$[1]; CALL "OO2A",SRM$[ALL] FI FI FI; WEND ; IF NEA("LNK",1)=0 THEN DIM LNK[3]; IF NEA("MSG$",1)>18 AND LEN(MSG$[19])>=4 THEN LET LNK[0]=DEC(MSG$[19](1,2)), LNK[1]=DEC(MSG$[19](3,2)) FI FI; LET SUFLG$="X", G0$=MNE("G0"), G1$=MNE("G1"), CV$="01-", VWLC=#IDSV.WIN-LBAR-COLORV , VWHC=#IDSV.COLOR-VIEWH , VWDC=#IDSV.WIN-VIEW-COLORN , INPC=#IDSV.COLOR-INPUT , INPA=#IDSV.WIN-ATTR(11), VWLA=#IDSV.WIN-ATTR(7), VWHA=#IDSV.WIN-ATTR(10), VWDA=#IDSV.WIN-ATTR(2); IF #IDSV.FLD-ED-FLAG ="Y" THEN LET FEF$=$01$ ELSE LET FEF$=$00$ FI; GOSUB VIEWSETUP; LET DNN=1, CMD$="INSERT "; GOSUB GETOOP; LET I=POS("METHOD"=METH$); IF I AND RVV=0 THEN LET IMETH$=CVT(METH$(I+7),136); LET I=POS(" "=IMETH$); IF I THEN LET IMETHP$=CVT(IMETH$(I),136), IMETH$=IMETH$(1,I-1) FI; IF IMETH$(STL(IMETH$))=";" THEN LET IMETH$=IMETH$(1,STL(IMETH$)-1) FI; LET I=POS("CONNECT"=IMETHP$); IF I THEN LET IMETHP$=CVT(IMETHP$(1,I-1),128) FI FI; IF CRM$="P" THEN LET CRD$="D", DND$="N", KCH$="N", DCH$="N", VMOD $="N", MS$="N", CT$="F" FI; IF AUTOE$<>"Y" THEN IF STL(SGO$) THEN LET PW$=SGO$; GOSUB PRCMD1 FI; GOSUB MAINLINE FI; LET MSG$[0]="."; GOTO VIEWEXIT
```


Which is one line of basic code and 2 Points if you can name the basic
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-22T11:23:23+00:00
- Post Title: 

LOL   What basic is this?
## Post #21
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-22T15:42:59+00:00
- Post Title: 

Its a form of Business Basic (BB), one of the 40 variations.  Too bad its still in use in a lot of companies.
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-27T21:27:48+00:00
- Post Title: 

Okay, Rahly, as an excuse, don't think I'm too lazy or not interested in implementing the plugin-system, because I really want to work on it. 
Yet, I'm getting married in a month, which takes up a lot of my time, as well as my job. 

Basically, that's what keeps me from working on it. Rest assured though, that I will. Like I said, it's just a matter of getting old and not having time due to family business, I guess.  I just thought I'd let you know, to show my appreciation of the cooperation!

Things will be more at ease after the marriage. (Well, one can always hope.   ). 

Still, I hope to have some time  before  the marriage to get it in the Commander.
## Post #23
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-27T22:45:58+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay, Rahly, as an excuse, don't think I'm too lazy or not interested in implementing the plugin-system, because I really want to work on it. 
Yet, I'm getting married in a month, which takes up a lot of my time, as well as my job.
 HAHAH SUCKER! 

> Reply from Mr.Mouse
>
> Basically, that's what keeps me from working on it. Rest assured though, that I will. Like I said, it's just a matter of getting old and not having time due to family business, I guess.  I just thought I'd let you know, to show my appreciation of the cooperation!

Things will be more at ease after the marriage. (Well, one can always hope.   ). 

Still, I hope to have some time  before  the marriage to get it in the Commander.

Thats ok, i'm also doing another Open Source Project.  An open source business basic virtual machine.
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-27T23:09:28+00:00
- Post Title: 

> Reply from Rahly
>
>  HAHAH SUCKER!

Haha, well, I take it you haven't gone through this process, or perhaps HAVE and KNOW what I am talking about  ?
## Post #25
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-28T00:47:55+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Haha, well, I take it you haven't gone through this process, or perhaps HAVE and KNOW what I am talking about  ?

No, but my beliefs are against the marriage process.  I believe in monogamous relationships, just not in marriage.  I believe we are reaching a state in our society where rituals such as this, really have little or no meaning, as most people don't hold it as they use to hold it.  But I believe in love in its purest sense.  I believe I can have a happy lifetime relationship without marriage.  "As the world changes, so must we."
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-28T07:19:06+00:00
- Post Title: 

Yeah. Look, I've been in a relationship for 8 years before the one I am in now, and I swore not to get married, more or less because of the same reasons you state. Times change. For me it is the other way around. Turned from stubborn anti-marriage to marriage. And why not? Life's too short to take too seriously in these matters, and if it feels like the right thing to do, you should do it. 
Like there really are no reasons to get married, there are also no reasons NOT to get married. I am thrilled I am, and this would be unthinkable in the past. I've grown.
## Post #27
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-28T17:03:21+00:00
- Post Title: 

As I always say, "To each their own".  You can only live your life the way you think it should be run.  When I was younger, all I wanted to do was find the right woman to marry, and I went through 6 gfs in a 2-3 year period.  I even use to goto church with some of them, and I'm strongly against organized religions.  Now, I'm at a point in my life, where most of the men my age, are either "how many chicks can I have sex with" or are married and having children, I really don't want either.  I'm sure my priorities will change eventually.  You say "lifes too short", your absolutely right.  There are not enough hours in a day to do all the things I wanna do.  A lot of these things can't be done with a girlfriend or wife, and in fact doing them, makes them feel neglected.
## Post #28
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-06T19:31:55+00:00
- Post Title: 

Okay, back to the stuff at hand. I tried addressing the manager.dll from within VB by declaring and coding:

> Reply from pluginman.mod
>
> 
Type TManagerPluginInfo
    ' Version 1.0
    Size As Integer
    PluginName As String
    PluginAuthor As String
    PluginURL As String
    PluginEmail As String
    PluginFullPath As String
    VersionMajor As Integer
    VersionMinor As Integer
    InterfaceMajor As Integer
    InterfaceMinor As Integer
    Supported As Boolean
 End Type

Public PlugInform As TManagerPluginInfo

Declare Function GetManagerVersion Lib "pluginmanager.dll" (ByRef Major As Integer, ByRef Minor As Integer) As Boolean
Declare Function SetPluginDirectory Lib "pluginmanager.dll" (ByVal Directory As String) As Boolean
Declare Function GetSupportedInterfaceVersion Lib "pluginmanager.dll" (ByRef Major As Integer, ByRef Minor As Integer) As Boolean
Declare Function RefreshPluginList Lib "pluginmanager.dll" () As Boolean
Declare Function PluginCount Lib "pluginmanager.dll" () As Integer
Declare Function PluginInfo Lib "pluginmanager.dll" (ByVal Index As Integer, ByRef PluginInfo As TManagerPluginInfo) As Boolean


Public Function GetMan()

Dim r As Boolean
Dim ma As Integer
Dim mi As Integer
Dim i As Integer


r = GetManagerVersion(ma, mi)
r = SetPluginDirectory(App.path & "\data\plugins")
r = GetSupportedInterfaceVersion(ma, mi)

r = RefreshPluginList
i = PluginCount
Dim t
For t = 1 To i
r = PluginInfo(i, PlugInform)
MsgBox PlugInform.PluginName & " version " & _
PlugInform.InterfaceMajor & "." & PlugInform.InterfaceMinor & _
" was loaded. "
Next t


End Function

All works, except the last one, PluginInfo. the r(esult) = False and the PluginForm variables are empty. Any idea? As said, everything else 
r(eturns) TRUE and PluginCount = 1.
## Post #29
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-06T21:54:26+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay, back to the stuff at hand. I tried addressing the manager.dll from within VB by declaring and coding:

All works, except the last one, PluginInfo. the r(esult) = False and the PluginForm variables are empty. Any idea? As said, everything else 
r(eturns) TRUE and PluginCount = 1.

Yeah, it should return false, you never set size.

PluginForm.Size = Sizeof(TManagerPluginInfo)

Which for this manager version is 41 or 0x29.

[edit]needs to be set b4 you call "PluginInfo"[/edit]
## Post #30
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-07T07:30:51+00:00
- Post Title: 

Ah, I see now. Probably would have to check the .pas file you send more closely eh. I think that won't be a problem then. 

If it works out I will work on the implementation.
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-08T09:42:52+00:00
- Post Title: 

Right, no this stupid VB obviously has not got a SizeOf method (it has Len, or LenB but both probably do not give the right size (32, or 36 respectively), as the function still fails). 

I will see if I can do this by calling an external method, have to see which one will do the trick though. VB is especially picky when it comes to user defined types and passing them to external sources.
## Post #32
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T03:36:05+00:00
- Post Title: 

You could always hard code the size, thats what the SizeOf command does, only its a constant created at compile time, instead of in the code.
## Post #33
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-09T18:13:46+00:00
- Post Title: 

That's not working either. I have tried making the strings just byte() or even fixed byte(10), but that's also not working. I keep getting FALSE as return value.
## Post #34
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T19:17:38+00:00
- Post Title: 

PluginForm.Size = 41

doesn't work?

well, if it doesn't, compile one for me, where you set the size to 41, and post the program here, and i'll try running it here to see what the problem is.

```
begin
  Result := False;
  if (Index >= 0) and (Index < PluginList.PluginCount) then
    begin
    if MyPluginInfo.Size = SizeOf(TManagerPluginInfo) then
      begin
      with PluginList.PluginList[Index] do
        begin
        MyPluginInfo.PluginName := PChar(PluginName);
        MyPluginInfo.PluginFullPath := PChar(PluginFullPath);
        MyPluginInfo.VersionMajor := VersionMajor;
        MyPluginInfo.VersionMinor := VersionMinor;
        MyPluginInfo.InterfaceMajor := InterfaceMajor;
        MyPluginInfo.InterfaceMinor := InterfaceMinor;
        MyPluginInfo.PluginAuthor := PChar(PluginAuthor);
        MyPluginInfo.Supported := Supported;
        end;
      Result := True;
      end;
    end;
end;
```


there are only 3 conditions for it to return true

the value has to be greater than or equal to 0
the value has to be less than the number of plugins
the PluginInfo.Size has to equal the compiled size of ManagerPluginInfo which is 41
## Post #35
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-09T19:46:17+00:00
- Post Title: 

Okay, THAT did work. I did not know it had to be 41. I tried it and it worx now. Only, that's not a very elegant way to do it.  Still, it gives us enough to work with.
## Post #36
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T20:23:07+00:00
- Post Title: 

ok

redid the manager, i took out all the packing of the structures and changed Supported from Boolean to a LongBool which is a 4 byte boolean, this should create the record structure as a 44 Size, and this is what "Len" function should say when you create it, if its less, then you have some missing fields

```
    // Version 1.0
    // Size 4 Bytes
    Size: Integer; 
    // PluginName 4 bytes                       
    PluginName: PChar;
    // Plugin Author 4 bytes
    PluginAuthor: PChar;
    // Plugin URL 4 bytes
    PluginURL: PChar;
    // Plugin Email 4 bytes
    PluginEmail: PChar;
    // Plugin Full Path 4 Bytes
    PluginFullPath: PChar;
    // Version Major 4 bytes
    // Version Minor 4 bytes
    VersionMajor, VersionMinor: Integer;
    // Interface Major 4 bytes
    // Interface Minor 4 bytes
    InterfaceMajor, InterfaceMinor: Integer;
    // Supported 4 Bytes
    Supported: LongBool;
  end;
```


11 fields * 4 Bytes each = 44 in size
## Post #37
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-09T20:32:07+00:00
- Post Title: 

Nah, that's not it. 

You know, it has something to do with the PChars (strings) I think. Because the lenB function gave 36 (the longest I got) with the old method. There are 5 strings, 5 + 36 = 41 , so perhaps VB is missing a byte when doing lenB on the record and strings are in the record.
## Post #38
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T20:47:44+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Nah, that's not it. 

You know, it has something to do with the PChars (strings) I think. Because the lenB function gave 36 (the longest I got) with the old method. There are 5 strings, 5 + 36 = 41 , so perhaps VB is missing a byte when doing lenB on the record and strings are in the record.

Thats interesting, cuz in VB all strings are pointers, every pointer is 4 bytes, at least in a 32bit system?  are you running a 24 bit system? 

ummm do this

make a structure for "each" field and do a len on each one, and list me the sizes of each.

ie

```
  Value As Integer
END TYPE
TYPE TManagerPluginInfo_PluginName
  Value As String
END TYPE
TYPE TManagerPluginInfo_PluginAuthor
  Value As String
END TYPE
TYPE TManagerPluginInfo_PluginURL
  Value As String
END TYPE
TYPE TManagerPluginInfo_PluginEmail
  Value As String
END TYPE
TYPE TManagerPluginInfo_PluginFullPath
  Value As String
END TYPE
TYPE TManagerPluginInfo_VersionMajor
  Value As Integer
END TYPE
TYPE TManagerPluginInfo_VersionMinor
  Value As Integer
END TYPE
TYPE TManagerPluginInfo_InterfaceMajor
  Value As Integer
END TYPE
TYPE TManagerPluginInfo_InterfaceMinor
  Value As Integer
END TYPE
TYPE TManagerPluginInfo_Supported
  Value As Boolean
END TYPE

TYPE TManagerPluginInfo_Strings
  Value1 As String  
  Value2 As String  
  Value3 As String  
  Value4 As String  
  Value5 As String  
END TYPE
```


they SHOULD add up to AT LEAST 44, strings should add up to 20.
## Post #39
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T20:55:35+00:00
- Post Title: 

a REPOST

i found this

[http://www.a1vbcode.com/vbtip.asp?ID=135](http://www.a1vbcode.com/vbtip.asp?ID=135)

this is call to an API function that works exactly the same way, passing pchars, i donno if "PRIVATE" fixes it or not.
## Post #40
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-09T22:03:59+00:00
- Post Title: 

No, but it did put me on the right track though. There were 5 strings, but also 5 integers. And it was them all along. These only reserve 2 for themselves. I changed them to longs (signed 4 bytes). 

> Type TManagerPluginInfo
>
>     ' Version 1.0
>
>     Size As Long
>
>     PluginName As String
>
>     PluginAuthor As String
>
>     PluginURL As String
>
>     PluginEmail As String
>
>     PluginFullPath As String
>
>     VersionMajor As Long
>
>     VersionMinor As Long
>
>     InterfaceMajor As Long
>
>     InterfaceMinor As Long
>
>     Supported As Boolean
>
>  End Type

And called the 0 based size like this:

> PlugInform.Size = Len(PlugInform) - 1

Now it works like a charm
## Post #41
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T22:19:10+00:00
- Post Title: 

ok
but you should prolly use the new manager, because i was reading that vb doesn't support packed structures, you use a "natural" alignment.  So i made a fix for it.

Ahh, integers for other languages, mean the best size for the CPU, in this case C++ int and Delphi int = 32 bits (4 Bytes),  I guess vb just wanted to be different?
## Post #42
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-09T22:28:09+00:00
- Post Title: 

Will do. I guess we can work on the actual usage of the plugins then!
## Post #43
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-09T22:40:55+00:00
- Post Title: 

yep still working on that

I have 2 things i'm working on

1. Standard DLL Plugin support (C++/Delphi) with Direct DLL Calls

2. ActiveX/COM Dll Plugin support (VB/C++/Delphi) although this is mainly for VB support with COM Object calling convention.

first i test the dll(MXP) for the mpGetPluginInfo and mpGetInterfaceVersion functions, this tells me that its a Standard Dll plugin, if i don't find it, i test for DLLGetClassObject, if i find that, then i try to access it VIA COM/ActiveX by "DllName.Archive" and if that works, i add it to the plugin list.

After than, i determine weither or not the plugin is supported, this information can get read via the plugin manager functions.

Com doesn't NEED mpGetPluginInfo like the dll direct does, BUT it does REQUIRE mpGetInterfaceVersion, if the manager can't call that function, it doesn't even show up in the list.

Also good to note, the manager does NOT try to register ActiveX or Coms in the directory, this should be handled by whoevers installer for that plugin.
## Post #44
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-10T20:51:21+00:00
- Post Title: 

Ah, okay, so the Installer will have register them. Hmm, I noticed I could not register the pluginmanager.dll, nor needed to to address it.
## Post #45
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-10T23:31:46+00:00
- Post Title: 

No its a standard dll, similar to an API call.

The plugin manager will export all possible functions, so when you reference them, they will be there.  The manager will handle the calls to the plugins.

For example


MexCom -> Pluginmanagers mpExportFileByNameToFile -> plugin has  the function -> processes request

MexCom -> Pluginmanagers mpExportFileByNameToFile -> plugin does not have the function -> Pluginmanager returns false.

Although, this should NEVER happen, cuz you will know what functions to call via mpGetFormatInfo which will tell you what functions are available for the format.
## Post #46
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-11T00:16:19+00:00
- Post Title: 

Explaination of how the pluginmanager will work

1. Mexcom checks plugin managers version to make sure its valid

2. Mexcom sets the plugin directory. and refreshs the plugin list

3. In a refresh, manager does the following

a) destroys current plugin list, and format list
b) does a recursive search through the plugin directory looking for *.mxp
c) tests each "library" for versioning and adds it to the plugin list
d) for each plugin, calls its format count and info
e) adds each format to the format list, and links it to a plugin in the plugin list

4) Mexcom gets information on the formats, and calls get format info for the format that its needs info on.  Using that information to determine which functions that format supports.

5) Calls the right function, indicating which format it works with

6) Plugin manager connects to the right plugin and tests for function, if function not found or "errors" plugin manager returns that the function failed.  (Returns false or 0)




Right now i'm currently still on #3 d+e
## Post #47
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-11T17:05:37+00:00
- Post Title: 

Forgot one thing, I'm adding a caching system.

This caches plugins which is at 5 right now,when you need a format, will load it into memory and leave it in memory, instead of loading the library every time you call a function, if it needs to load a plugin and the cache is full, it unloads the oldest loaded plugin, and uses that cache slot.

There is a new plugin manager function  "SetCacheSize(Integer32Bit)" and "FreeCache" if you plan to set a cache size, set it after "ProcessPluginDirectory".  That function clears EVERYTHING and frees all plugins, and resets the cache size to default which is 5(requires a compiler change).  Also note, setting the cache size, after plugins are loaded, causes all plugins to be uncached, and reloaded when needed, as it calls "FreeCache"
## Post #48
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-11T17:31:47+00:00
- Post Title: 

I'm thinking about changing all Strings in the plugin system to Unicode strings for better support of the file system.

Unfortunately, VB converts their "unicode" strings to Ansi strings before passing them to the DLL function. I did find some code to prevent it, and need your input on it.

```
PluginDirectory = ".\plugins\"
ProcessPluginDirectory(StrPtr(PluginDirectory))
```


Its an undocumented function where you get a pointer to the string without converting.  The only problem i can see, is losing win95 support, which, i don't think vb5 supports anymore.
## Post #49
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-11T21:43:10+00:00
- Post Title: 

Hmm, so I would have to send pointers to strings to the Manager instead of the actual strings? I know that any variable passed to an external dll is by default By Reference (in effect a pointer), instead of the actual value, unless specifically declared By Value.
## Post #50
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-12T01:51:56+00:00
- Post Title: 

well

```
Declare Function SetPluginDirectory Lib "pluginmanager.dll" (ByVal Directory As String) As Boolean
```


everywhere i read, VB converts all passed in strings to ANSI instead of Wide. but if you think it will work, i can change it.
## Post #51
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-28T15:18:06+00:00
- Post Title: 

Ok, i finished the Caching system, although, it require a small rewrite of the plugin interface for the manager.  Anyway, half of the plugin interface functions are done, did them last night, most of them is copy/paste with a few changes, like the function name to extract, and the format of function to be called is different for each command.  I also had to change the find data structure to include a variant variable for the vb/com interface as you can't pass pointer variables around.  This variable MUST return variables Filename and FieldData, but this is for the VB/COM plugin to do, not mexcom.

functions done

```
function mpGetFormatInfo(FormatIndex: Integer; var FormatInfo: TFormatInfo): Boolean; stdcall;
function mpGetOptions(FormatIndex: Integer; OptionType: Integer; var Options: PChar): Boolean; stdcall;
function mpOpenArchive(var ArchiveHandle: Integer; FormatIndex: Integer; ArchiveName: PChar; Flags: Cardinal; CreateOptions: PChar): Boolean; stdcall;
function mpOpenArchiveBindStream(var ArchiveHandle: Integer; FormatIndex: Integer; Stream: IStream; Flags: Cardinal; CreateOptions: PChar): Boolean; stdcall;
function mpCloseArchive(FormatIndex: Integer; ArchiveHandle: Integer): Boolean; stdcall;
function mpIndexCount(FormatIndex: Integer; ArchiveHandle: Integer): Integer; stdcall;
function mpFindFirstFile(FormatIndex: Integer; ArchiveHandle: Integer; FileMask: PChar; FieldList: PChar; var FindData: TFileFindInfo): Boolean; stdcall;
function mpFindNextFile(FormatIndex: Integer; var FindData: TFileFindInfo): Boolean; stdcall;
function mpFindClose(FormatIndex: Integer; var FindData: TFileFindInfo): Boolean; stdcall;
```


functions to go

```
function mpIsStreamAnArchive(FormatIndex: Integer; Stream: IStream): Boolean; stdcall;
function mpExportFileByNameToFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean; stdcall;
function mpExportFileByIndexToFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean; stdcall;
function mpExportFileByNameToStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean; stdcall;
function mpExportFileByIndexToStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean; stdcall;
function mpImportFileByNameFromFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean; stdcall;
function mpImportFileByIndexFromFile(ArchiveHandle: Integer; FileIndex: Integer; ExternalFile: PChar): Boolean; stdcall;
function mpImportFileByNameFromStream(ArchiveHandle: Integer; ArchiveFile: PChar; Stream: IStream): Boolean; stdcall;
function mpImportFileByIndexFromStream(ArchiveHandle: Integer; FileIndex: Integer; Stream: IStream): Boolean; stdcall;
```
## Post #52
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-28T22:32:23+00:00
- Post Title: 

PluginManager is finished, now all i need to do is test it all out.
## Post #53
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-09-29T09:03:30+00:00
- Post Title: 

> Reply from Rahly
>
> PluginManager is finished, now all i need to do is test it all out.
## Post #54
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-16T19:34:20+00:00
- Post Title: 

Still testing, but here is a copy of the pluginmanager.
## Post #55
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-17T21:04:01+00:00
- Post Title: 

Excellent, I downloaded it.
## Post #56
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-18T20:29:10+00:00
- Post Title: 

Now, all I would need is an actual plugin, so I can rebuild the routines in MultiEx Commander so it will use the plugin.
## Post #57
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-19T00:06:26+00:00
- Post Title: 

On the first page is my ORIGINAL post of pluginmanager.zip, it has a good plugin and a bad plugin.  But do you need one of a game that YOU have?  If so, i'll need information for that.
## Post #58
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-19T07:28:58+00:00
- Post Title: 

How about this format : 

[viewtopic.php?t=941](http://forum.xentax.com/viewtopic.php?t=941)

It's just a basic directory structure, it looks like. 

0-3 Starts off with the length of the id-tag (I assume), 
4-n ID tag of the file (all the same in the archives I've seen)

then come the entries:
Byte - number of directories below the current directory level
unsigned 32bit - Length of the current directory string
string - the current directory string

Now, if there are no directories below the current level, naturally a 0 will be found at this byte position. Note that this 0 is then immediately followed by an unsigned 32-bit value denoting the numer of files in this directory. 
So, when directories-below-this-level = 0 :
unsigned 32-bit - Number of files in this directory
-
unsigned 32-bit - Length of first listed filename string 
string - first listed filename string
unsigned 32-bit - size of first listed file (in bytes)
unsigned 32-bit - offset of first listed file 
-
unsigned 32-bit - Length of second listed filename string 
string - first second filename string
unsigned 32-bit - size of second listed file (in bytes)
unsigned 32-bit - offset of second listed file 

etc. 

I believe you can end the search for entries when directory values start turning 0 , and when you have reached the offset of the file with the lowest offset (so right after the header).
## Post #59
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-19T19:12:50+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> It's just a basic directory structure, it looks like. 

0-3 Starts off with the length of the id-tag (I assume), 
4-n ID tag of the file (all the same in the archives I've seen)

then come the entries:
Byte - number of directories below the current directory level
unsigned 32bit - Length of the current directory string
string - the current directory string

Now, if there are no directories below the current level, naturally a 0 will be found at this byte position. Note that this 0 is then immediately followed by an unsigned 32-bit value denoting the numer of files in this directory. 
So, when directories-below-this-level = 0 :
unsigned 32-bit - Number of files in this directory
-
unsigned 32-bit - Length of first listed filename string 
string - first listed filename string
unsigned 32-bit - size of first listed file (in bytes)
unsigned 32-bit - offset of first listed file 
-
unsigned 32-bit - Length of second listed filename string 
string - first second filename string
unsigned 32-bit - size of second listed file (in bytes)
unsigned 32-bit - offset of second listed file 

etc. 

I believe you can end the search for entries when directory values start turning 0 , and when you have reached the offset of the file with the lowest offset (so right after the header).

```
0000010: 0000 0000 0000 0001 0700 0000 636f 6d6d  ............comm
0000020: 6f6e 0001 0600 0000 7669 6465 6f00 0002  on......video...
0000030: 0000 0010 0000 0063 6f6d 7074 655f 746f  .......compte_to
0000040: 7572 2e62 696b 0000 a903 006f a903 000c  ur.bik.....o....
0000050: 0000 0063 6f6d 7074 6573 2e62 696b 0000  ...comptes.bik..
0000060: a903 006f 0000 0000 0000 0000 0000 0042  ...o...........B
0000070: 494b 69f8 a803 00b5 0000 00b8 0500 00b5  IKi.............
```


Ok using this file as an example,

Bytes 0-3 = size of string
Bytes 4-14 = string
Byte 15 = Directory count  $01 ?
Byte 16-19 = Directory string name size?  0? is this right?  if not it seems like i'm 8 bytes off, so what are bytes 16-23?
## Post #60
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-24T00:27:27+00:00
- Post Title: 

any ideas?
## Post #61
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-24T09:20:06+00:00
- Post Title: 

Yeah sorry, have been busy lately. 

I think the first bytes indicate the root of the archive. 

So you have the ID-tag UBI_BF_SIG, then a 32-bit value of 1 followed by a 0. I think these just apply to the root. So the root is 1 "directory" with a name of 0 size. Then come the other values of directories below the root. 
Which have names etc.
## Post #62
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-01T22:00:01+00:00
- Post Title: 

Well, some heavy other chores to do, but I looked at implementing the pluginmanager. Have found that the new pluginmanager.dll probably uses another TPlugInInfo structure? Also, it returns version 0.0 if I ask for it. Perhaps I got my function declares all screwed up.
## Post #63
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-03T23:46:23+00:00
- Post Title: 

which function are you talking about?

TManagerPluginInfo?  or TPluginInfo ?
## Post #64
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-04T09:27:44+00:00
- Post Title: 

I guess I mean TPluginInfo (that will give you information on loaded plugin number xxx). The struct I send (the size) may not be correct or something. It just returns "False".
## Post #65
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-05T00:19:53+00:00
- Post Title: 

what did you get back for "plugincount" ?
## Post #66
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-05T08:33:18+00:00
- Post Title: 

I believe I got a 1. That's what it did with the old version as well;
the BF Extractor.
## Post #67
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-05T20:12:25+00:00
- Post Title: 

and your passing a "0" to  GetPluginInfo ?
## Post #68
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-05T22:24:57+00:00
- Post Title: 

This is how it is declared and called:

> Type TManagerPluginInfo
>
>     ' Version 1.0
>
>     Size As Long
>
>     PluginName As String
>
>     PluginAuthor As String
>
>     PluginURL As String
>
>     PluginEmail As String
>
>     PluginFullPath As String
>
>     VersionMajor As Long
>
>     VersionMinor As Long
>
>     InterfaceMajor As Long
>
>     InterfaceMinor As Long
>
>     Supported As Boolean
>
>  End Type
>
> 
>
> Public PlugInform As TManagerPluginInfo
>
> Declare Function PluginInfo Lib "pluginmanager.dll" (ByVal Index As Integer, ByRef PluginInfo As TManagerPluginInfo) As Boolean
>
> 
>
> 
>
> r = PluginInfo(0, PlugInform)

It may therefore be that I am using old functions? You said GETPluginInfo?
## Post #69
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-08T01:51:51+00:00
- Post Title: 

that sounds right. don't mind me, i have a few projects spinning around my head.

TManagerPluginInfo.Size should be 44 bytes
## Post #70
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-08T14:36:46+00:00
- Post Title: 

Hmm, mine is 41. Could you post your TPluginManager structure, with datatypes and all?
## Post #71
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-08T20:15:45+00:00
- Post Title: 

sure... here its my common.pas

```

interface

type
  TManagerPluginInfo = record
    // Version 1.0  Size = 44 bytes
    Size: Integer; // 4
    PluginName: PChar; // 4
    PluginAuthor: PChar;  // 4
    PluginURL: PChar;  // 4
    PluginEmail: PChar;  // 4
    PluginFullPath: PChar;  // 4
    VersionMajor, VersionMinor: Integer;  // 4 4
    InterfaceMajor, InterfaceMinor: Integer;  // 4 4
    Supported: LongBool;  // 4
  end;

  TPluginInfo = record
    // Version 1.0  Size = 28
    Size: Integer;  // 4
    Name: PChar;  // 4
    Author: PChar;  // 4
    URL: PChar;  // 4
    Email: PChar;  // 4
    Major: Integer;  // 4
    Minor: Integer;  // 4
  end;

  TFormatInfo = record
    // Version 1.0  Size = 20
    Size: Integer;  // 4
    FileMask: PChar; // This is better than an Interface (4)
    GameName: PChar; // This is the name of the game it supports (4)
    Flags: Int64;    // Support flags (8)
  end;

  // Not to be used outside of the plugin
  TFileFindInfo = record
    Filename: PChar;
    FieldData: PChar;
    FileMask: PChar;
    ArchiveHandle: Integer;
    FieldList: PChar;
    InternalFindInfo: Pointer;
  end;

const
  SUPPORTFLAG_CREATE        = $0000000000000001;
  SUPPORTFLAG_IMPORT        = $0000000000000002;
  SUPPORTFLAG_EXPORT        = $0000000000000004;
  SUPPORTFLAG_DELETE        = $0000000000000008;
  SUPPORTFLAG_REPLACE       = $0000000000000010;
  SUPPORTFLAG_ADD           = $0000000000000020;
  SUPPORTFLAG_BYINDEX       = $0000000000000040;
  SUPPORTFLAG_BYNAME        = $0000000000000080;
  SUPPORTFLAG_HANDLEISTREAM = $0000000000000100;
  SUPPORTFLAG_HANDLEFILE    = $0000000000000200;
  SUPPORTFLAG_TESTARCHIVE   = $0000000000000400;

  OPTIONTYPE_CREATE  = $00000001;
  OPTIONTYPE_EXPORT  = $00000002;
  OPTIONTYPE_IMPORT  = $00000003;

  OPENFLAG_CREATENEW      = $00000001;
  OPENFLAG_CREATEEXISTING = $00000002;

  InterfaceVersionMajor = 1;
  InterfaceVersionMinor = 0;

implementation

end.
```
## Post #72
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-08T20:17:12+00:00
- Post Title: 

You "Boolean" might be only 1 byte, try using an Integer.
## Post #73
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T16:02:00+00:00
- Post Title: 

I made it a long (4 bytes) and now I got "True" and it seems to work fine. 

Could you briefly show how (function-wise) I would use the Manager to open Battlefield files and extract stuff from it?
## Post #74
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-09T20:55:54+00:00
- Post Title: 

which part

Manager->Plugin interface

or 

Mexcom -> Manager interface?
## Post #75
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T20:59:48+00:00
- Post Title: 

> Reply from Rahly
>
> which part

Manager->Plugin interface

or 

Mexcom -> Manager interface?

The latter. What I can do to call the manager to open a certain file and how mexcom will know what files are in there. 

Also, I noticed in the PluginInfo that you have not reserved space for file extensions (archive extensions). Perhaps it would be neat to have that as well, so mexcom can tell the user which archive extensions can be processed using the plugin.
## Post #76
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-10T02:39:17+00:00
- Post Title: 

Plugin Information is only for plug information, remember one plugin can support MULTIPLE formats if needed.  This is just for present the user with what formats are installed and who did them, etc etc.  To rest of it doesn't care about plugins.  At least in YOUR point of view the individual plugins have no meaning.

First call

mpGetFormatCount()

This will give you a format count of EVERY format  EVERY plugin has.

then a loop from 0 to formatcount-1 on   mpGetFormatInfo will give you the formatinformation

File Mask for that format
Game name for that format
Flags that the format supports

Support flags were listed in an earlier post.

then you text for the flags SUPPORTFLAG_HANDLEFILE and SUPPORTFLAG_HANDLEISTREAM, this lets you know wether the format allows filenames or streams

then you can test for the flag SUPPORTFLAG_TESTARCHIVE and if it allows it, you can use mpIsFileAnArchive or mpIsStreamAnArchive depends on the above flags

mpOpenArchive/mpOpenArchiveBindStream and mpCloseArchive are used to open and close an archive file with a particular format

to get a list of files you can use 

mpFindFileFirst
mpFindFileNext
mpFindFileClose

if format supports BYNAME or  (archive that store file names)

mpIndexCount to get the index count

if format support BYINDEX  (archive that doesn't store file names)

then test wether it supports Importing/Exporting and use the respected function name for the job

mpExportFileByNameToFile
mpExportFileByIndexToFile
mpExportFileByNameToStream
mpExportFileByIndexToStream
mpImportFileByNameFromFile
mpImportFileByIndexFromFile
mpImportFileByNameFromStream
mpImportFileByIndexFromStream


is this confusing?
## Post #77
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-10T02:41:20+00:00
- Post Title: 

oh yeah

don't forget to call mpGetOptions to get any "extra" options
## Post #78
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-10T08:10:41+00:00
- Post Title: 

> Reply from Rahly
>
> 
is this confusing?
## Post #79
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-11T01:19:22+00:00
- Post Title: 

do you need more information?
## Post #80
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T07:41:16+00:00
- Post Title: 

I think I'm okay for nowwill try to work on it a.s.a.p. If I run into trouble, I'll come crying..
## Post #81
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-17T19:34:21+00:00
- Post Title: 

Might you include a mpGetLastError function, that will return a number or description of the last error the Plugin Manager encountered?

I am having trouble with mpGetFormatInfo. You say it's size should be 20. But if I set that, no go. But in fact I should set it to 24 to get something back. This something is a correct file mask and game name. Yet, the flags are 0. An int64 may not translate easily to a VB variable, perhaps.
## Post #82
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-19T05:52:15+00:00
- Post Title: 

yeah sorry, my bad, delphi aligns to the 64bit boundary, not the 32bit,

i recompiled, this should be right.

Ok, what you CAN do, is use 2 integers next to each other, and call them Flag1: Integer;  Flag2: Integer;

I only made room for more flags, but at the moment, only flags in the Flag1 are used at the moment, everything else is "reserved" for future use.
## Post #83
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-19T05:55:17+00:00
- Post Title: 

I'll see what i can do about a "GetLastError"
## Post #84
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-19T11:52:18+00:00
- Post Title: 

Excellent. That works now. 

I have implemented the stuff the PM coughs up in the global formats list, next is the actual implementation of the functionality.
## Post #85
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-20T02:56:19+00:00
- Post Title: 

okie dokie
## Post #86
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-22T20:44:10+00:00
- Post Title: 

Hmm, mpIsFileAnArchive will test whether a given file is a valid archive in the format indexed right? 

The Prince of Persia format just returns True all the time, even if it's not a valid archive??

res = mpisFileAnArchive (1, Filename)  (= True for all files)

W3rd.
## Post #87
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-23T01:59:23+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Hmm, mpIsFileAnArchive will test whether a given file is a valid archive in the format indexed right? 

The Prince of Persia format just returns True all the time, even if it's not a valid archive??

res = mpisFileAnArchive (1, Filename)  (= True for all files)

W3rd.

Are you checking to make sure the plugin SUPPORTS file testing?
## Post #88
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-23T08:46:52+00:00
- Post Title: 

Yep, and it says it does. Prince of Persia .BF files...
## Post #89
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-25T06:24:14+00:00
- Post Title: 

hmm, what files are you testing it with?


i tested it like this

```
     (Major <> 1) or (Minor <> 0) then
    begin
    ShowMessage('Invalid Version of the plugin manager found');
    Application.Terminate;
    end;
  SetPluginDirectory('.\Plugins\');
  RefreshPluginList();
  if mpIsFileAnArchive(1, 'C:\program files\Ubisoft\Prince of Persia The Sands of Time\prince.bf') then
    Showmessage('yes')
  else
    Showmessage('no');
  if mpIsFileAnArchive(1, 'C:\program files\Ubisoft\Prince of Persia The Sands of Time\PrinceOfPersia.EXE') then
    ShowMessage('yes')
  else
    showmessage('no');

```


and it printed yes on the first one, and no on the second one, that should be right. prince.bf is a valid file, and princeofpersia.exe is an invalid file.
## Post #90
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-05T00:14:23+00:00
- Post Title: 

Well, I tested it alike. 

Anyway, I'm having trouble retrieving the indexcount from a BF file from Beyond Good and Evil (from the demo named 'sally_something.bf'). 

Here's the test VBCode:

```
inh = CInt(formats(Supported).Games(FormatSel).BMSCS)
res = False
res = mpIsFileAnArchive(inh, DataFileName)
If res = False Then
DebugLog ("!!ERROR: " & RPMErrorDescription(ERPM_ArchiveInvalid))
MsgBox RPMErrorDescription(ERPM_ArchiveInvalid), , "Error: "
GoTo Endoffunction
End If
Dim freehand As Integer
freehand = FreeFile
res = False
res = mpOpenArchive(freehand, inh, DataFileName, 0, "")
If res = False Then
DebugLog ("!!ERROR: " & RPMErrorDescription(ERPM_ArchiveInvalid))
MsgBox RPMErrorDescription(ERPM_ArchiveInvalid), , "Error: "
GoTo Endoffunction
End If
Dim IndexCount As Long
IndexCount = mpIndexCount(inh, freehand)
res = False

res = mpCloseArchive(inh, freehand)

```


inh is the formatindex, stored in my global structure 'formats' (retrieved prior to processing). 

Now, all 'res' are true after I call any of the functions. 
But the IndexCount = 0 after the call.

Weird huh? What is is with the flags I got to give and the Pchar (or string) I got to provide in OpenArchive. I just assumed that I didn't have to give anything if I just wanted to open the archive.
## Post #91
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-07T17:51:23+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> inh is the formatindex, stored in my global structure 'formats' (retrieved prior to processing). 

Now, all 'res' are true after I call any of the functions. 
But the IndexCount = 0 after the call.

Weird huh? What is is with the flags I got to give and the Pchar (or string) I got to provide in OpenArchive. I just assumed that I didn't have to give anything if I just wanted to open the archive.

Ok, i downloaded the demo, had a small problem with the demo file as its just a little bit different than the full version.  Fixed that, as well as the problem you were having,  in my test i was use a static handle, instead of the one it gave to me.  I found a small bug in the mpOpenArchive for BFFileFormat which didn't set the ArchiveHandle after it was created .  Fixed both of those and mpIndexCount gave me 1025 indexes.

Flags should be 0, and the PChar doesn't have to be set, as BFFileFormat ignores it.  Its ment to set options like for example a string of "Password=string" to set a password to open with, note this is just an example, but these options should be gleamed from mpGetOptions.

EDIT: Opps, forget to attach the new BFFileFormat
## Post #92
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-07T18:56:55+00:00
- Post Title: 

Aaah ! Excellent! Thanks, will work with with asap!
## Post #93
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-07T22:24:31+00:00
- Post Title: 

Damn, still no go. I get the same stuff. All files are valid archives, even if they're not, and IndexCount = 0 for all. Perhaps the key lies in using proper variables by reference?!

```
'FUNCTION DECLARES

Declare Function mpIsFileAnArchive Lib "pluginmanager.dll" (ByVal FormatIndex As Integer, ByVal Filename As String) As Boolean
Declare Function GetManagerVersion Lib "pluginmanager.dll" (ByRef Major As Integer, ByRef Minor As Integer) As Boolean
Declare Function SetPluginDirectory Lib "pluginmanager.dll" (ByVal Directory As String) As Boolean
Declare Function GetSupportedInterfaceVersion Lib "pluginmanager.dll" (ByRef Major As Integer, ByRef Minor As Integer) As Boolean
Declare Function RefreshPluginList Lib "pluginmanager.dll" () As Boolean
Declare Function mpGetFormatCount Lib "pluginmanager.dll" () As Integer
Declare Function PluginCount Lib "pluginmanager.dll" () As Integer
Declare Function PluginInfo Lib "pluginmanager.dll" (ByVal Index As Integer, ByRef PluginInfo As TManagerPluginInfo) As Boolean
Declare Function mpGetFormatInfo Lib "pluginmanager.dll" (ByVal FormatIndex As Integer, ByRef FormatInfo As TFormatInfo) As Boolean
Declare Function mpOpenArchive Lib "pluginmanager.dll" (ByVal ArchiveHandle As Integer, ByVal FormatIndex As Integer, ByVal ArchiveName As String, ByVal Flags As Long, ByVal CreateOptions As String) As Boolean
Declare Function mpCloseArchive Lib "pluginmanager.dll" (ByVal FormatIndex As Integer, ByVal ArchiveHandle As Integer) As Boolean
Declare Function mpIndexCount Lib "pluginmanager.dll" (ByVal FormatIndex As Integer, ByVal ArchiveHandle As Integer) As Long

Type TManagerPluginInfo
    ' Version 1.0
    Size As Long
    PluginName As String
    PluginAuthor As String
    PluginURL As String
    PluginEmail As String
    PluginFullPath As String
    VersionMajor As Long
    VersionMinor As Long
    InterfaceMajor As Long
    InterfaceMinor As Long
    Supported As Long
 End Type

  Type TFormatInfo
  '   Version 1.0  Size = 20
    Size As Long
    FileMask As String '// This is better than an Interface (4)
    GameName As String
    Flags As Long ' // Support flags (8)
    FlagsUp As Long
  End Type


```
## Post #94
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-07T23:27:58+00:00
- Post Title: 

let me see your code, here is mine

```
     (Major <> 1) or (Minor <> 0) then
    begin
    ShowMessage('Invalid Version of the plugin manager found');
    Application.Terminate;
    end;
  SetPluginDirectory('.\Plugins\');
  RefreshPluginList();
  if mpIsFileAnArchive(0, 'C:\program files\Ubisoft\Beyond Good & Evil DEMO\sally_clean.bf') then
    Showmessage('yes')
  else
    Showmessage('no');
  if mpOpenArchive( MyHandle, 0, 'C:\program files\Ubisoft\Beyond Good & Evil DEMO\sally_clean.bf', 0, nil) then
    begin
    Count := mpIndexCount(0, MyHandle);
    ShowMessage(IntToStr(Count));
    mpCloseArchive(0, MyHandle);
    end;
```


I donno if that helps?
## Post #95
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-08T08:13:58+00:00
- Post Title: 

This I wrote some posts ago: 

Here's the test VBCode:

```

inh = CInt(formats(Supported).Games(FormatSel).BMSCS) 'inh is format 0

res = False 'This is just there for testing purposes

res = mpIsFileAnArchive(inh, DataFileName) 'res is a boolean 

If res = False Then
DebugLog ("!!ERROR: " & RPMErrorDescription(ERPM_ArchiveInvalid))
MsgBox RPMErrorDescription(ERPM_ArchiveInvalid), , "Error: "
GoTo Endoffunction
End If

Dim freehand As Integer
freehand = FreeFile 'here i get a valid file handle (a free one) 

res = False 'This is just there for testing purposes
res = mpOpenArchive(freehand, inh, DataFileName, 0, "")

If res = False Then
DebugLog ("!!ERROR: " & RPMErrorDescription(ERPM_ArchiveInvalid))
MsgBox RPMErrorDescription(ERPM_ArchiveInvalid), , "Error: "
GoTo Endoffunction
End If

Dim IndexCount As Long
IndexCount = mpIndexCount(inh, freehand)

res = False 'This is just there for testing purposes
res = mpCloseArchive(inh, freehand)

```


inh is the formatindex, stored in my global structure 'formats' (retrieved prior to processing). 

Now, all 'res' are true after I call any of the functions. 
But the IndexCount = 0 after the call.

Question is: that MyHandle of yours, is that something I should create first and give "ByValue" ? Or is it something the PluginManager will return and MexCom has to store somewhere for future reference?

There may also be some dicrepancy with Longs versus Integers. Does mpIndexCount return actual integers (up to 65535) or dwords (32-bit)? because I noticed I had to replace your "integers" with longs in records. 

Perhaps you could write a test dll that just has very simple functions like:

```
'MyBool will be set by the manager (as it is ByReference) and the manager will also return the same boolean
'Similarly:
GetInt(ByRef MyInt as integer) as Integer
GetLong (ByRef MyLong as long) as long

SetBool (ByVal MyBool as boolean) as boolean
'the manager will now set an internal boolean to the value it got and return that value. 
'This makes possible a Bool1 = SetBool(Bool2) and Bool1 vs Bool2 compare afterwards
'Similarly:
SetInt(ByVal MyInt as integer) as Integer
SetLong (ByVal MyLong as integer) as long

```

And perhaps even some more combinations. We must be sure that the right variables are given by value or by reference.
## Post #96
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-09T01:43:36+00:00
- Post Title: 

All integers = 32bit

Yeah, mpOpenArchive( ArchiveHandle ) is passed by reference, not value, this is returned to you, this is a value that indicates which archive you are working with, this allows you to have more than one archive open with the same plugin, although this prolly WONT happen with the current implementation of mexcom, but it could be used in the future, this "handle/reference" is use when you pass to other functions like mpCloseArchive(release archive).
## Post #97
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-09T06:52:36+00:00
- Post Title: 

Okay! Good, that solves one (important) problem. 
I gave the wrong handle (I created my own, but I should have gotten it from the manager). 
Now I get 1025 indexcounts indeed. 

Still no luck with mpIsFIleAnArchive. Returns true for all files. 

However, at least this enables me to continue retrieving fileinfo and showing it to the user!
## Post #98
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-09T17:33:11+00:00
- Post Title: 

does mpIsFileAnArchive return true but fail on the mpOpenArchive ?
## Post #99
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-09T19:20:39+00:00
- Post Title: 

Nope, returns true for all functions (also mpCloseArchive). 

Perhaps the boolean thing is not working right? How about returning a byte?
## Post #100
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-09T22:15:34+00:00
- Post Title: 

Woops, I get a crash everytime I call mpFindFirst. 

Do you have some sample code of that as well?
## Post #101
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-10T00:37:56+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Nope, returns true for all functions (also mpCloseArchive). 

Perhaps the boolean thing is not working right? How about returning a byte?

mpCloseArchive, should almost always return true, unless there was some memory error or something.  mpIsFileAnArchive works for me

mpIsFileAnArchive(0,'sally_clean.bf); returns true for me
mpIsFileAnArchive(0,'bge.exe'); return false for me

you sure, it seems to be working for me.
## Post #102
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-10T03:19:53+00:00
- Post Title: 

my sample?

```
     (Major <> 1) or (Minor <> 0) then
    begin
    ShowMessage('Invalid Version of the plugin manager found');
    Application.Terminate;
    end;
  SetPluginDirectory('.\Plugins\');
  RefreshPluginList();
  if mpIsFileAnArchive(0, 'C:\program files\Ubisoft\Beyond Good & Evil DEMO\sally_clean.bf') then
    Showmessage('yes');
  if Not(mpIsFileAnArchive(0, 'C:\program files\Ubisoft\Beyond Good & Evil DEMO\bge.exe')) then
    ShowMessage('no');
  if mpOpenArchive( MyHandle, 0, 'C:\program files\Ubisoft\Beyond Good & Evil DEMO\sally_clean.bf', 0, nil) then
    begin
    Count := mpIndexCount(0, MyHandle);
    ShowMessage(IntToStr(Count));
    Memo1.Lines.Clear;
    if mpFindFirstFile( 0, MyHandle, '*.*', nil, MyInfo) then
      begin
      repeat
        Memo1.Lines.Add(String(MyInfo.Filename));
        writeln(MyInfo.Filename);
      until Not( mpFindNextFile(0, MyInfo));
      mpFindClose(0, MyInfo);
      end;
    mpCloseArchive(0, MyHandle);
    end;
```
## Post #103
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-14T08:02:21+00:00
- Post Title: 

Ok, well, each call to mpFindFirstFile crashes my IDE. Perhaps the "pointer" variable in the TFileInfo is not easily implemented. What is its purpose? VB doesn't have a "pointer" variable unfortunately, I know that sucks, but that's the way it is. No 

*p as char; 

vars in VB.. . . .
## Post #104
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-15T02:37:48+00:00
- Post Title: 

That should be remedied, Pointers are implemented as LongInt (32bit Integers);  since you don't USE that parameter, it should be ok.

TFindInfo is how you get the filename/file attributes, Internally it stores information like "what file am i on?" so that any NEW calls know where to continue from (aka state information).
## Post #105
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-15T03:13:00+00:00
- Post Title: 

what do you have it defined as, and whats the SizeOf the type.
## Post #106
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-15T08:58:21+00:00
- Post Title: 

The size is 24

This is your declaration :

```
  TFileFindInfo = record 
    Filename: PChar; 
    FieldData: PChar; 
    FileMask: PChar; 
    ArchiveHandle: Integer; 
    FieldList: PChar; 
    InternalFindInfo: Pointer; 
  end; 

```


This is mine :

```
    Filename As String
    FieldData As String
    FileMask As String
    ArchiveHandle As Long
    FieldList As String
    InternalFindInfo As Long 'pointer?
  End Type

```


Then I declare the function like this:

```
Declare Function mpFindFirstFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal ArchiveHandle As Long, ByVal FileMask As String, ByVal FieldList As String, ByRef finddata As TFileFindInfo) As Boolean
```


And call it like this:

```
SizeOfTheThing = Len(finddata)

res = mpFindFirstFile(inh, freehand, "*.*", Null, finddata)

```


It no longer crashes, as the msitake was to call the function with a LOCALLY declared finddata, I have now created a global finddata and the function returns TRUE. However, the FindData info is blank. No filenames, etc. Also afer using mpFindNext. It just returns no info.
## Post #107
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-15T13:04:15+00:00
- Post Title: 

can you send me your "test" program?
## Post #108
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-16T11:32:01+00:00
- Post Title: 

Ok, I'll see what I can do about sending a test program with the VB code.
## Post #109
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-17T20:04:23+00:00
- Post Title: 

Okay, I have send you the code to your terrygoodkind mail address.
## Post #110
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-17T23:30:06+00:00
- Post Title: 

umm great.... ummm can you do me a favor, send me the compile executable, thats all

i tried compiling and running it myself, but i had to convert it to VB.NET, and it fails on mpGetFormatInfo.
## Post #111
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-18T08:33:47+00:00
- Post Title: 

Hmm, please try to compile it nonetheless, if you will. I have experienced some difficulty with this test program. I had to copy the relevant code from another test program, as that one was too big. But once copied, the mpFindFirstFile no longer can be called using a "null" for fieldlist. VB nags abouth that. Consequently, the executable would also nag about that. When I use "" instead (empty string) everything crashes. If you can have both VB and Delphi running you can finetune the functions so they match, n'est-pas?
You know your own code best and can see what is happening. Just a thought.
## Post #112
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-18T22:15:15+00:00
- Post Title: 

Yes, but all i need is the executable, the main problem is that VB.NET doesn't run anything like the other versions of VB.  The main problem is that i COULD get it working with VB.NET but it is almost guaranteed not to work with VB5 or 6.  If you want me to get it working under .NET I will though.  I was shooting for VB5, the one you have.
## Post #113
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-18T22:21:51+00:00
- Post Title: 

Okay, so the problem is the VB.net thing. I have Delphi installed, so I could also take a look at the plugin manager code and play with that code. The problem is, the test program just crashes at the moment. I'm not sure what good it would do, when you start it, and it crashes. Perhaps I'm just calling it all wrong, and without the code, you can't alter the behaviour of my executable.
## Post #114
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-19T01:21:57+00:00
- Post Title: 

i don't really need too, but with the executable i can tell how your calling the function, and suggest changes.

What is it crashing on?
## Post #115
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-19T08:01:14+00:00
- Post Title: 

It crashes when I use an empty string for FieldList. ( "" )
But the crash may be due to the call itself, or some other variable. 
Anyway, I sent you the executable.
## Post #116
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-19T08:04:28+00:00
- Post Title: 

Whooops, that was me....
## Post #117
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-20T02:15:39+00:00
- Post Title: 

i think i'm going to do what you said earlier though, but i'm going to do it in the plugin manager.
## Post #118
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-20T04:29:09+00:00
- Post Title: 

ok, for that error, what are the differences in the "Type" from the working version and the one that doesn't work, also is mpGetFormatInfo being called the same  and "ByRef"?

From what i can see, the function works correctly, but when you get it back, you copy the strings out of it, and then try to FREE the ones i sent you, which you can't, you try to free them like Ole/Com strings, and they aren't
## Post #119
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-20T09:33:53+00:00
- Post Title: 

Yes, both ByRef

```
Declare Function mpGetFormatInfo Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByRef FormatInfo As TFormatInfo) As Boolean
```


```
Declare Function mpFindNextFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByRef FindData As TFileFindInfo) As Boolean
```


As for the freeing of strings, there's no code of mine doing that, must be how VB handles certain things. You are talking about the fieldlist and filemask strings, right? As for the FindData strings, I don't do much with them, as the program crashes before I can do something.
## Post #120
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-20T16:12:20+00:00
- Post Title: 

how do you have it TFormatInfo defined in both? how are the variables declared? globally in one, locally in another?
## Post #121
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-20T16:37:49+00:00
- Post Title: 

They are both global... One works, the other crashes. We should zoom in on each of the parameters that are used in TFindFileInfo (separate functions) to see which one screws up.
## Post #122
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-21T02:22:57+00:00
- Post Title: 

I wonder though, if its doing the same thing that happening with mpGetFormatInfo
## Post #123
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-22T08:39:21+00:00
- Post Title: 

Well, I just don't know what is different. I could not detect any. Yo uhave the VB code as well, you can see there's no difference in the way the records are addressed. I can install Delphi and take a look at your code, if you haven't got the time or anything, but it's still a mystery to me what is going wrong. 

We must pinpoint the parameter that is causing this and more importantly: why.
## Post #124
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-02-23T04:43:50+00:00
- Post Title: 

well, i could make a simple fix for the problem, but that makes plugin development a bit more complicated.  Would you like me to try the fix, to see if it works for you?

Edit: Its really not a "fix" per say, but it fools VB, the only problem i have is that sometimes VB doesn't free the memory, so you could be left with memory leaks in those instances.  I think it has something to do with strings in record structures.

What happens, is that VB calls the plugin, plugin points to memory of the string, plugin returns to vb and vb copies the string into another string, and then tries to free the string that was passed back to it, and it fails because its not in the "vb string" format.
## Post #125
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-23T07:55:54+00:00
- Post Title: 

Well, we could try to work with the fixed version so, that new versions of MexCom and the PluginManager would be able to work with the "unfixed version" as well when we figure out how to overcome this problem. That way I can continue work on it and prepare a release version. We then have time to work in peace and quite on this problem, after the release.
## Post #126
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-03-28T21:09:01+00:00
- Post Title: 

Sorry it took so long, here try this
## Post #127
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-29T12:01:47+00:00
- Post Title: 

Thanks, I'll try to work on it when I have time. I just released the new version. So we have time to work on getting the manager in, in peace.
## Post #128
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-07T07:13:34+00:00
- Post Title: 

Well, hmm, this is an altered BF plugin? It doesn't help. The crash occurs when MexCom talks to the Manager. That is still the case.
## Post #129
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-04-30T22:34:36+00:00
- Post Title: 

yeah hmmm.. damn... it doesn't email me when you post... grrrr... and here i thought you were still working on it.

Edit: calling what function again?  just to make sure
## Post #130
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-12T07:35:48+00:00
- Post Title: 

Well, the function that should list the contents of an archive.
## Post #131
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-13T05:09:57+00:00
- Post Title: 

Try this update, this should get ride of the crash.  Let me know if this stops the crash, and if it does crash, is it the same spot? as it doesn't crash with the test app you sent me.
## Post #132
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-13T05:50:01+00:00
- Post Title: 

Also, when you call mpIsFileAnArchive, it looks like your doing it

mpIsFileAnArchive(ByVal Index as Long, ByRef FileName as String): Boolean

is this the way your doing it?
## Post #133
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-15T23:21:03+00:00
- Post Title: 

It didn't stop the crash.   

It's not ID-ing the archive as a valid one, nor is it listing the filenames (it crashes there). How is it possible that the app did not crash when you tried it? Can you show me the result of my app?

Regarding the mpIsFileAnArchive, yes,  I'm calling it like you said.
## Post #134
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-16T18:01:36+00:00
- Post Title: 

ok let me get a screenshot

try changing  "ByRef Filename As String" to "ByVal Filename As String"
## Post #135
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-16T18:04:53+00:00
- Post Title: 

Here is the screenshot, no crash, only a popup that you send, and i think the problem for that is, that your passing the string by ref, which is sending it to the program as a Pointer to an OleVariant, i think you need to send by value, which will convert to a Pointer to a char array.


Note: this is NOT the compiled .NET version, i just overwrote that binary, with the compiled one you sent me.
[mexcom.png](https://xentaxbackup.github.io/file/226_mexcom.png)
## Post #136
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-16T19:08:55+00:00
- Post Title: 

Ok, well , it didn't crash , because the test app won't allow any errors. It will only start to retrieve the resource list if the mpIsFileAnArchive is satisfied.

Your suggestion worked, so the archive is now detected as a valid one. 

 

However, the list (mpFindFirst) crashes the program. 

```
Declare Function mpFindFirstFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal ArchiveHandle As Long, ByVal FileMask As String, ByRef FieldList As String, ByRef FindData As TFileFindInfo) As Boolean
```


```
    Filename As String
    FieldData As String
    FileMask As String
    ArchiveHandle As Long
    FieldList As String
    InternalFindInfo As Long 'pointer?
  End Type

```
## Post #137
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-16T20:41:28+00:00
- Post Title: 

Maybe?

```
Declare Function mpFindFirstFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal ArchiveHandle As Long, ByVal FileMask As String, ByVal FieldList As String, ByVal FindData As TFileFindInfo) As Boolean
```


All Strings that are passed in parameter values, like FileMask and FieldList should be Value, try changing FindData to ByVal and see what happens.
## Post #138
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-18T07:36:12+00:00
- Post Title: 

That doesn't work, as VB does not allow user-defined structures to be passed ByVal.   

Fixing up the parameters in the struct from "String" to char() didn't help either. It still crashes. Very VERY Odd.
## Post #139
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-18T13:11:37+00:00
- Post Title: 

ok

change

ByRef FieldList As String

to

ByVal FieldList As String

keep the Structure as ByRef, and then send me a copy of that COMPILED program, i should be able to fix it up and any other functions that pass structures.  I'm thinking that passing by ref, is creating a different sized struct, and then i'm filling the strings with PChars, and then VB is treating them like an OLE Variant, but i'd like to make sure, but I'd like to see for myself, this way we don't have to keep "trying" things.
## Post #140
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-19T11:47:20+00:00
- Post Title: 

I have mailed you the recompiled program...did you get it?
## Post #141
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-19T21:26:17+00:00
- Post Title: 

Got it, i'm looking at it now.

Also, I wanted to run something by ya.  I just wrote a new tool, game trainer system.  As MexCom, it will support multiple games with the added feature of user upgrade.  Anyway, I'm writing updating system for it, I thought Mexcom might want to use.
## Post #142
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-19T22:41:42+00:00
- Post Title: 

I like the sound of that, could you perhaps PM me the specifics?
## Post #143
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-19T23:33:21+00:00
- Post Title: 

Ok, found a problem with isFileAnArchive, i had been playing with it and forgot to change it back, it was looking for a Pointer to an Ole Variant, instead of a PChar, now that passes and its failing on the mpFindFirstFile, it seems that VB is building the structure, and then after calling the function, its destroying that version, which has memory allocated from the plugin.  it then tries to free that memory in the struct and fails miserably.

Question:  what is your definition for the mpFindFirstFile/mpFindNextFile? and the structure you pass it.
## Post #144
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-20T08:28:38+00:00
- Post Title: 

```
Declare Function mpFindNextFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByRef FindData As TFileFindInfo) As Boolean

```
## Post #145
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-20T14:21:54+00:00
- Post Title: 

and the TFileFindInfo structure?
## Post #146
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-20T15:03:46+00:00
- Post Title: 

```
    Filename As String
    FieldData As String
    FileMask As String
    ArchiveHandle As Long
    FieldList As String
    InternalFindInfo As Long 'pointer?
  End Type

```
## Post #147
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-20T15:46:05+00:00
- Post Title: 

```
    Filename As String 
    FieldData As String 
    FileMask As String 
    ArchiveHandle As Long 
    FieldList As String 
    InternalFindInfo As Long 'pointer? 
    InternalFindVar As Variant
  End Type
```


I have it almost working
## Post #148
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-20T16:47:32+00:00
- Post Title: 

i think it should be set, if you can make that change and send me the new copy, cuz at the moment, i'm writing to that area of memory, which is on the stack, which is writing over another variable, and killing the program.

If it works, i'll send you the new programs.

EDIT: what did you think of the PM? or have you not assimilated it yet?
## Post #149
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-20T17:07:13+00:00
- Post Title: 

OKay, it's on your way. 

Yes, I think your idea of update is pretty nifty. I will have to see it first, though. And see how much work is in there to get something like that implemented. I have a busy schedule, with multiple projects. And that's just my hobby. My job is even worse, and then I have a family as well. 

Nevertheless, I say it's a good idea.
## Post #150
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-20T17:43:58+00:00
- Post Title: 

Ok, sent you the new copies of the manager and plugins

its working for me, your not printing out the Filename after each mpFindNextFile, also, you need to call mpFindClose after you use the FindFirst/FindNext so that the plugin can free any data it was using for the find (prevent memory leaks)

see how that works for you
## Post #151
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-20T18:01:15+00:00
- Post Title: 

SUCCES! 

It worked! I could now retrieve the filenames !

I sent you the recompiled test app.  

Question is, do I need more than the filename? I also get an Internal FindInfo, which is a uint32 (long, DWORD etc). Is that correct?
## Post #152
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-20T18:38:04+00:00
- Post Title: 

Yes, thats a pointer to memory that the program controls

the InternalFindVar is a variable that COM plugins will use, since VB can't use pointers, i provided a Variant, for it to use instead of the Info,  the raw programs like C/C++/Delphi can use the pointer to speed it up.

Umm no, well you can

There are 2 ways to extract, by name(wildcard) and by index, you should also be able to say mpExtractFileByIndexToXXXXX, or mpExtractFileByNameToXXXXX

depending on the plugin, you can query using the mpFileFirstFile/mpFileNextFile for other info as well.

Right now BFFileFormat doesn't have any options, but i could add some if you want

the way it works is

FindFileInfo.FieldList = "FileSize;FileAttrib;"

and after the First/Next you get FindFileInfo.FieldData = "1234567;500" where the first number is the file size and the second number is the value of the attributes of the file

you could make some fields manditory, and you can query the plugin for valid fields.

Note: there could be 2 different file sizes as well, a compressed filesize and a real file size
## Post #153
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T12:41:44+00:00
- Post Title: 

I will have to check, 'cause I believe my FieldData was "" (empty).
## Post #154
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-26T15:24:54+00:00
- Post Title: 

Whether Mr. Mouse MultiEx Commander supports plug-ins there is an example of their writing? (it is desirable on Pascal - Delphi) it is possible and on Basic
## Post #155
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-27T02:19:34+00:00
- Post Title: 

It is possible on basic, although, THAT support is more experimental than what we are working with.  At least until someone works with me to get that side working.

Right now, VB is supported via COM DLL similar to the old DLL, but with functions that are the same in RAW DLL.
## Post #156
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-28T08:13:11+00:00
- Post Title: 

Strange as that... In folder Plugins 3 plug-ins lay and MultiEx Commander sees only 2...
## Post #157
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T08:16:36+00:00
- Post Title: 

I have noticed that as well.    Weird. Especially, since it does show in the list if you wish to open an archive. 

It's a bug, and on my to-do list for the next release.
## Post #158
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-28T08:36:15+00:00
- Post Title: 

Perfectly... We Shall wait next release.
## Post #159
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T16:14:20+00:00
- Post Title: 

Kornet, the new plugin system is actually written in Delphi.
## Post #160
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T17:59:29+00:00
- Post Title: 

OK, as I saw, the FieldData in TFindFIleInfo is en empty string after mpFindFirst/Next . Is this correct? Do I have to tell the manager to give me the details (like offset size etc)?
## Post #161
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T18:36:51+00:00
- Post Title: 

You have to ask for it, yes, in the FindFirst, but you also have to know which fields the plugin supports.
## Post #162
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-28T18:49:16+00:00
- Post Title: 

> Reply from Rahly
>
> Kornet, the new plugin system is actually written in Delphi.

It pluginmanager.dll?
## Post #163
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T18:57:02+00:00
- Post Title: 

the new plugin system isn't implemented in mexcom at the moment, its being worked on by Mr Mouse
## Post #164
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T19:06:05+00:00
- Post Title: 

I found out something Mr Mouse, I need to try something to see if it works. I need to send you a new copy of the manager to test though.
## Post #165
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T19:07:01+00:00
- Post Title: 

Ok, send it!
## Post #166
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T19:30:20+00:00
- Post Title: 

Nvm, i forgot i could test it as well.  Didn't work out so well.
## Post #167
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T22:05:44+00:00
- Post Title: 

DId you alter the calling convention for 

```
function mpExportFileByNameToFile(ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): Boolean; stdcall;
```


I get the Error "Bad calling convention" 

with 

```
Declare Function mpExportFileByNameToFile Lib "pluginmanager.dll" (ByVal ArchiveHandle As Long, ByVal ArchiveFile As String, ByVal ExternalFile As String) As Boolean 
```
## Post #168
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-28T23:12:36+00:00
- Post Title: 

yeah a while ago

```
function mpExportFileByNameToFile(FormatIndex: Integer; ArchiveHandle: Integer; ArchiveFile: PChar; ExternalFile: PChar): LongBool; stdcall;
```


i guess that would be

```
Declare Function mpExportFileByNameToFile Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal ArchiveHandle As Long, ByVal ArchiveFile As String, ByVal ExternalFile As String) As Boolean
```
## Post #169
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-28T23:47:31+00:00
- Post Title: 

Thx
## Post #170
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-29T18:34:36+00:00
- Post Title: 

okay, I do that. But the process fails and returns False. 

I get the list of files in the archive allright, and I then take one of them and use as the ArchiveFile string. I use a temporary filename as external file. I use the same FormatIndex stuff and ArchiveHandle that I needed to list the contents in the first place. 

Any ideas?
## Post #171
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-29T18:59:02+00:00
- Post Title: 

More problems, the mpGetOptions crashes, not unlike the previous crashes.
## Post #172
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-29T19:59:27+00:00
- Post Title: 

Send me the compiled program?
## Post #173
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T12:22:51+00:00
- Post Title: 

Will do.
## Post #174
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-01T21:47:42+00:00
- Post Title: 

I've sent it! Did you get it?
## Post #175
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-01T22:15:21+00:00
- Post Title: 

yup, email sent

I had left some debug code for printing out to a console (Command Prompt) which you don't have, so it gets fubared.

Edit: Sorry about that, I also modified the call a little so you can call it. and i rewrote a single function, that allowed me to take out a standard unit of delphi, cut down on the file size from 107K down to 87K
## Post #176
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-01T22:27:56+00:00
- Post Title: 

Okay, but if I run the test app now, it still doesn't extract, did this work for you? 
Also, how should I call mpGetOptions now? As it gives me a Bad Calling Convention.
## Post #177
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-01T22:35:29+00:00
- Post Title: 

Oh, i didn't know you were still having an extraction problem.  i'll look right now

```
Declare Function mpGetOptions Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal OptionType As String, ByRef Options As String) As Boolean
```


Edit: would an IM service be a little better communicating?
## Post #178
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-01T22:59:52+00:00
- Post Title: 

haha, another one of my mistakes

i had originally named the functions mpExtractFileByNameToFile

i renamed them all to mpExportFileByNameToFile, and it was changed in the plugin and the plugin manager, but the plugin manager was looking for the old name in the plugin
## Post #179
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-02T21:10:47+00:00
- Post Title: 

1. Hmm, the mpGetOptions still gives a Bad Calling Convention. 

Doesn't that sound like a gathering of geeks calling eachother names through their cell phones?

2. You changed the string type to unicode in mpGetFormatInfo structure? TFormatInfo? It returns 0 . 0 B 0 F now for FileMask. 
It didn't before
## Post #180
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-03T01:49:14+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> 1. Hmm, the mpGetOptions still gives a Bad Calling Convention. 

Doesn't that sound like a gathering of geeks calling eachother names through their cell phones?

2. You changed the string type to unicode in mpGetFormatInfo structure? TFormatInfo? It returns 0 . 0 B 0 F now for FileMask. 
It didn't before

1. I donno why, here is the exact syntax

```
function mpGetOptions(FormatIndex: Integer; OptionType: Integer; var Options: PWideChar): LongBool;
```


Since you are passing a string by ref, VB passes the string by ref but in Unicode format (wide character).

2. My bad, when i said i was testing things earlier, i left some code in.

```
FormatInfo.GameName := SysAllocStringByteLen(PChar(GameName), Length(GameName));
```


should have been

```
FormatInfo.GameName := SysAllocStringByteLen(PChar(GameName), Length(GameName));
```


sent you email
## Post #181
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-03T06:08:28+00:00
- Post Title: 

Ok, it doesn't work.  I call it like 

```

```


I noticed you used LongBool instead of Boolean as the return value. 

Also, in the VB declare you gave above, you made OptionType a string. I guess that was a typo.  

I call it as

```
res = mpGetOptions(0,0,options)
```
 where options is a string. 

I don't know which are valid option types though.
## Post #182
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-03T10:55:30+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I noticed you used LongBool instead of Boolean as the return value.

Yes, i had to change all the function to LongBool because Delphi booleans are 1 byte, and VB booleans are 1 Long (4 bytes).  I was setting the one byte to false, but vb was reading the 3 other bytes of "garbage" which could have been anything.  Delphi set the one byte to $00, then VB said does $13563800 <> 0? and thereby thinking it was true.

> Reply from Mr.Mouse
>
> Also, in the VB declare you gave above, you made OptionType a string. I guess that was a typo. 
Code: Select allres = mpGetOptions(0,0,options) where options is a string. 

I don't know which are valid option types though.

Not that I know of since we are passing by reference, and not by value.  when you had by ref before, vb was passing in everything as a w_char *, or a PWideChar

i'm thinking about just changing the way the function works, a lot less hastle

```
  OPTIONTYPE_EXPORT  = $00000002;
  OPTIONTYPE_IMPORT  = $00000003;
  OPTIONTYPE_FIND    = $00000004;
```
## Post #183
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-03T11:16:25+00:00
- Post Title: 

Well, this still does not explain the Bad Calling Convention. 

Which is weird then. But if you change the way the function works, that's ok. 

I'll await the new version
## Post #184
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-03T22:55:55+00:00
- Post Title: 

you have mail

changed the function from

```
function mpGetOptions(FormatIndex: Integer; OptionType: Integer; var Options: PWideChar): LongBool;
```


to

```
function mpGetOptions(FormatIndex: Integer; OptionType: Integer): PChar;
```


so it should be 

```
Declare Function mpGetOptions Lib "pluginmanager.dll" (ByVal FormatIndex As Long, ByVal OptionType As Long) As String
```


see if that works.
## Post #185
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-03T23:03:58+00:00
- Post Title: 

working on mpGetLastError
## Post #186
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-04T07:17:48+00:00
- Post Title: 

Alrighty, got the manager up and running. It extracts BF contents now from MultiEx Commander.
## Post #187
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-26T21:38:53+00:00
- Post Title: 

And there is an example of a writing of a plug-in for MultiEx Commander? I Wish to try
## Post #188
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-06-27T01:21:36+00:00
- Post Title: 

there are, but this is the new plugin system for mexcom, which hasn't been implemented in an offical release yet.

You could ask for the new implementation, but i might be changing them just slightly.
## Post #189
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-03T11:32:01+00:00
- Post Title: 

So Rahly, are you making progress on the new PM, with a test plugin? So I can start finalizing implementation in MexCom and release the new version?
## Post #190
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-03T20:41:00+00:00
- Post Title: 

Yes I am, did you want it with Stream support as well? I'm not sure if you can actually test that within VB
## Post #191
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-03T20:43:46+00:00
- Post Title: 

Hmm, I don't think so, it won't be completely necessary, I can call it the other  way.
## Post #192
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-03T21:07:22+00:00
- Post Title: 

there is always the other plugin support too
## Post #193
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-04T14:57:49+00:00
- Post Title: 

Indeed. I do like the other idea you had, about updating MexCom from the WIKI. It will interesting to see if that can be done in a new version.
## Post #194
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-06T19:38:09+00:00
- Post Title: 

Whether Mr. Mouse will be SDK for development of plug-ins?
## Post #195
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-06T23:30:19+00:00
- Post Title: 

SDK? prolly not unless its in the wiki.  But there will be samples.
## Post #196
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-07T06:19:54+00:00
- Post Title: 

Yep. And it's already possible to create activeX plugins. There's been some document on that in the past
## Post #197
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-09T17:03:58+00:00
- Post Title: 

Adding a new function, i noticed the only way to get info from archives was to use Find, which sucks if the archive doesn't support names, so i'm adding a function to get info via index number as well.  I'm also toying with the idea of pulling out the Field Data from the find, this will make it easier to upgrade in the future, also taking out most of the FindDataInfo structure including filename.
## Post #198
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-09T17:15:37+00:00
- Post Title: 

Okido !
## Post #199
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T20:10:07+00:00
- Post Title: 

the find system has been completely replaced for something a little easier to use. No more crazy structures
## Post #200
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T20:18:50+00:00
- Post Title: 

Allright! People keep pushing me to release the new version, along with a new Scriptor/Binder, so that's good news.
## Post #201
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T20:19:30+00:00
- Post Title: 

oops, clicked submit by accident

```
function mpFindFirstFile(ArchiveHandle: Integer; FileMask: PChar): LongWord;
```


for the manager though it'll be

```
function mpFindFirstFile(FormatIndex: Integer; ArchiveHandle: Integer; FileMask: PChar): LongWord;
```


next

```
function mpFindNextFile(Handle: Integer): LongBool;
```


```
function mpFindNextFile(FormatIndex: Integer; Handle: LongWord): LongBool;
```


to get information from the find

```
function mpFindInfo(ArchiveHandle: Integer; Handle: LongWord; Field: PChar): PChar;
```


```
function mpFindInfo(FormatIndex: Integer; ArchiveHandle: Integer; Handle: LongWord; Field: PChar): PChar;
```


also added a function for if the archive supports ByIndex

```
function mpIndexedInfo(ArchiveHandle: Integer; Index: Integer; Field: PChar): PChar;
```


```
function mpIndexedInfo(FormatIndex: Integer; ArchiveHandle: Integer; Index: Integer; Field: PChar): PChar;
```


Field Information is polled by mpGetOptions using the 
OPTIONTYPE_FILEINFO option.
## Post #202
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T20:26:53+00:00
- Post Title: 

File information will be in a  Format


<name>=<type>[:<size>];<name>=<type>[:<size>];

i'm defining certain static types

STRING, UINT8,  UINT16, UINT32, UINT64, INT8, INT16, INT32, INT64, and DATE

so FAR

for example, FILENAME=STRING:5  = Filename is a string of characters, with a max size of 5 characters, DATE is a special case

for example    'FILEDATE=DATE;ARCHIVEDATE=DATE'

when you ask for the date you can pass format of the date,  'FILEDATE=YYYY MM DD'
or use whatever is defined in the system (if format not defined)
'FILEDATE='
## Post #203
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T20:30:27+00:00
- Post Title: 

Almost forgot, the test plugin is litered with error information for mpGetLastError(), i'll also release a list of error values and meanings
## Post #204
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T20:40:08+00:00
- Post Title: 

Ok, good to know. How to address them.
## Post #205
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T22:38:17+00:00
- Post Title: 

ok, question for ya?

Extracting files

mpExportFileByNameToFile(Format, Handle, "*.WAV", "C:\AllMyWavs\")

should the plugin assume the directory exists? or should plugins force directories to exist?
## Post #206
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-07-14T22:49:17+00:00
- Post Title: 

> Reply from Rahly
>
> ok, question for ya?

Extracting files

mpExportFileByNameToFile(Format, Handle, "*.WAV", "C:\AllMyWavs")

should the plugin assume the directory exists? or should plugins force directories to exist?
Sorry for butting in like this, but I just had to say my thoughts.

Perhaps the plugin should first check for the existance of the directory, proceeding if it exhists, but asking the user if they would like to create it or specify a different directory if it doesn't...

Once again, just my thoughts...
## Post #207
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-14T22:52:50+00:00
- Post Title: 

If thats the case, then it shouldn't be the plugins job, (plugin should fail/not create the directories) and it should be handled by the application.
## Post #208
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-15T01:03:03+00:00
- Post Title: 

Only things left right now are 

The 2 Import functions and the 2 new Remove functions for the test plugin.
## Post #209
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-15T05:43:17+00:00
- Post Title: 

> Reply from Rahly
>
> If thats the case, then it shouldn't be the plugins job, (plugin should fail/not create the directories) and it should be handled by the application.

I agree. That really isn't the plugin's job, it's the caller's job, in this case MultiEx Commander. 

The way I see it, the user will always have to point to a directory anyway to extract in to, so that will always exist. Any subdirectories should be created, more so, when files with the same name are in different subdirs in the archive. If not allowing for subdir creation, it get's a bit messy. I think it's the end-user's job to know where he extracts what. And the plugin should just go and extract/create subdirs/overwrite files already in existing files.
## Post #210
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-23T16:33:33+00:00
- Post Title: 

I'm thinking about removing the function

mpImportFileByIndexFromFile
mpImportFileByIndexFromStream

I don't see how this would work anyway.

and changing

mpImportFileByNameFromFile to

mpImportFileFromFile

and mpImportFileByNameFromStream to

mpImportFileFromStream
## Post #211
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-23T17:43:09+00:00
- Post Title: 

all i need to do is mpImportFileByFile, and fix up the manager
## Post #212
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-23T18:09:07+00:00
- Post Title: 

Great!!
## Post #213
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-23T23:27:56+00:00
- Post Title: 

should it default to overwritable, or not?
## Post #214
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-23T23:38:58+00:00
- Post Title: 

Yes.
## Post #215
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-26T01:46:52+00:00
- Post Title: 

New Plugin Manager and Test Plugin,

documentation to follow
## Post #216
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-26T01:48:34+00:00
- Post Title: 

Manager function list

  GetManagerVersion,
  GetSupportedInterfaceVersion,
  SetPluginDirectory,
  RefreshPluginList,
  PluginCount,
  PluginInfo,
  FreeCache,
  SetCacheSize,

  mpGetFormatCount,
  mpGetFormatInfo,
  mpGetOptions,
  mpSetOption,
  mpOpenArchive,
  mpOpenArchiveBindStream,
  mpCloseArchive,
  mpIndexCount,
  mpIndexedInfo,
  mpFindInfo,
  mpFindFirstFile,
  mpFindNextFile,
  mpFindClose,
  mpIsFileAnArchive,
  mpIsStreamAnArchive,
  mpExportFileByNameToFile,
  mpExportFileByIndexToFile,
  mpExportFileByNameToStream,
  mpExportFileByIndexToStream,
  mpImportFileFromFile,
  mpImportFileFromStream,
  mpRemoveFileByName,
  mpRemoveFileByIndex,
  mpGetLastError,
  mpGetErrorText
## Post #217
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-26T01:57:04+00:00
- Post Title: 

New functions

  mpSetOption,
  mpIndexedInfo,
  mpFindInfo,
  mpRemoveFileByName,
  mpRemoveFileByIndex,
  mpGetLastError,
  mpGetErrorText

Changed functions
  mpOpenArchive,
  mpOpenArchiveBindStream,
  mpFindFirstFile,
  mpFindNextFile,
  mpFindClose,
  mpImportFileByNameFromFile,       // Name changed to mpImportFileFromFile
  mpImportFileByNameFromStream  // Name changed to  mpImportFileFromStream,

Removed functions
  mpImportFileByIndexFromFile,
  mpImportFileByIndexFromStream
## Post #218
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-26T07:06:44+00:00
- Post Title: 

Thanks, have go it! w00t!
## Post #219
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-26T12:51:18+00:00
- Post Title: 

New Functions

```
function mpIndexedInfo(FormatIndex: LongInt; ArchiveHandle: LongInt; Index: LongInt; Item: PChar): PChar; stdcall;
function mpFindInfo(FormatIndex: LongInt; Handle: LongInt; Field: PChar): PChar; stdcall;
```


```
function mpOpenArchiveBindStream(var ArchiveHandle: LongInt; FormatIndex: LongInt; Stream: IStream; Flags: Cardinal): LongBool; stdcall;
function mpFindFirstFile(FormatIndex: LongInt; ArchiveHandle: LongInt; FileMask: PChar): LongInt; stdcall;
function mpFindNextFile(FormatIndex: LongInt; FindHandle: LongInt): LongBool; stdcall;
function mpFindClose(FormatIndex: LongInt; FindHandle: LongInt): LongBool; stdcall;
```


You'll notice in the open functions I've removed CreateParams, I opted to let mpSetOption() to handle this, so there was no need for it to be here.
mpFind's have been changed with the removal of the TFindFileInfo structure
## Post #220
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-26T13:00:36+00:00
- Post Title: 

Do you have a complete docs as to all functions and syntax etc?
## Post #221
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-26T23:16:13+00:00
- Post Title: 

no, but i could write something up in the WIKI, just not sure where to put it
## Post #222
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-27T08:25:39+00:00
- Post Title: 

Hmm, I would like to add some docs with the next release on how people should write their plugins for the Manager. Not necessarily how the Manager talks to MexCom. So the plugin-->Manager bit.
## Post #223
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-27T11:24:03+00:00
- Post Title: 

Well, i removed things like TFileFindInfo, because it wasn't generic enough, so i put it on par with index viewing, because not all archives have file names.

For Example though, the test pluging, gives you.

FILENAME=STRING;FILESIZE=UINT64;FILEDATE=DATE;ARCHIVEDATE=DATE
when you mpGetOptions with the OPTIONTYPE_FILEINFO.

updated common unit

```

interface

type
  TManagerPluginInfo = packed record
    // Version 1.0
    Size: LongInt;
    PluginName: PChar;
    PluginAuthor: PChar;
    PluginURL: PChar;
    PluginEmail: PChar;
    PluginFullPath: PChar;
    VersionMajor, VersionMinor: LongInt;
    InterfaceMajor, InterfaceMinor: LongInt;
    Supported: LongBool;
  end;

  TPluginInfo = packed record
    // Version 1.0
    Size: LongInt;
    Name: PChar;
    Author: PChar;
    URL: PChar;
    Email: PChar;
    Major: LongInt;
    Minor: LongInt;
  end;

  TFormatInfo = packed record
    // Version 1.0
    Size: LongInt;
    FileMask: PChar; // This is better than an Interface
    GameName: PChar; // This is the name of the game it supports
    Flags: Int64;    // Support flags
  end;

const
  SUPPORTFLAG_CREATE        = $0000000000000001;
  SUPPORTFLAG_IMPORT        = $0000000000000002;
  SUPPORTFLAG_EXPORT        = $0000000000000004;
  SUPPORTFLAG_DELETE        = $0000000000000008;
  SUPPORTFLAG_REPLACE       = $0000000000000010;
  SUPPORTFLAG_BYINDEX       = $0000000000000020;
  SUPPORTFLAG_BYNAME        = $0000000000000040;
  SUPPORTFLAG_HANDLEISTREAM = $0000000000000080;
  SUPPORTFLAG_HANDLEFILE    = $0000000000000100;
  SUPPORTFLAG_TESTARCHIVE   = $0000000000000200;
  SUPPORTFLAG_EXPORTNAMEWILD= $0000000000000400;
  SUPPORTFLAG_IMPORTNAMEWILD= $0000000000000800;

  OPTIONTYPE_CREATE   = $00000001;
  OPTIONTYPE_EXPORT   = $00000002;
  OPTIONTYPE_IMPORT   = $00000003;
  OPTIONTYPE_FILEINFO = $00000004;

  OPENFLAG_CREATENEW      = $00000001;
  OPENFLAG_OPENALWAYS     = $00000002;
  OPENFLAG_FOREXPORT      = $00000004;
  OPENFLAG_FORIMPORT      = $00000008;

  pERROR_OK              = $00000000;
  pERROR_INVALID_PARM_1  = $00000001;
  pERROR_INVALID_PARM_2  = $00000002;
  pERROR_INVALID_PARM_3  = $00000003;
  pERROR_INVALID_PARM_4  = $00000004;
  pERROR_INVALID_PARM_5  = $00000005;
  pERROR_INVALID_PARM_6  = $00000006;
  pERROR_INVALID_PARM_7  = $00000007;
  pERROR_INVALID_PARM_8  = $00000008;
  pERROR_INVALID_PARM_9  = $00000009;
  pERROR_FILE_NOT_EXISTS = $0000000A;
  pERROR_FILE_CANT_OPEN  = $0000000B;
  pERROR_INVALID_FORMAT  = $0000000C;
  pERROR_STREAM_READ     = $0000000D;
  pERROR_INVALID_HANDLE  = $0000000E;
  pERROR_INVALID_INDEX   = $0000000F;
  pERROR_CREATE_ERROR    = $00000010;
  pERROR_ARCHIVE_READ_ERROR = $00000011;
  pERROR_NO_MATCHES      = $00000012;
  pERROR_ARCHIVE_CLOSED  = $00000013;
  pERROR_INVALID_OPTION  = $00000014;
  pERROR_WILDCARDS_NOT_ALLOWED = $00000015;
  pERROR_INVALID_ARCHIVE = $00000016; 
  pERROR_FILE_EXISTS     = $00000017;

  pERROR_SPECIFICPLUGIN  = $80000000;

  InterfaceVersionMajor = 1;
  InterfaceVersionMinor = 0;

implementation

end.
```


I'll also write up a C header later.
## Post #224
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-03T17:53:27+00:00
- Post Title: 

Can you email me a complete, working test app Delphi source code that uses the manager functions? Along with all new .pas files (such as "common" etc). 
So I can read them and implement the same stuff in MexCom? For instance, the testplugin is not detected by the manager. But I need to see how you have it in mind, and how each function is declared. 

Yes, of course I have a lot of docs. But not all, and I need ALL.  

Edit: Also, after a firstfile find, then I should do a mpFindInfo to get know what the file is about eh? But, the "working" BF plugin doesn't return the mpGetOptions FILEFIND options, just an emtpy string. So I have no way to get the fields, are do you have default fields to give in mpFindInfo?

Edit2: OpenArchive crashes the whole IDE now. Perhaps due to the Cardinal there? Or the LongBool return? Please check your PM.
## Post #225
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-03T22:40:30+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Can you email me a complete, working test app Delphi source code that uses the manager functions? Along with all new .pas files (such as "common" etc). 
So I can read them and implement the same stuff in MexCom? For instance, the testplugin is not detected by the manager. But I need to see how you have it in mind, and how each function is declared.

sure

> Reply from Mr.Mouse
>
> Edit: Also, after a firstfile find, then I should do a mpFindInfo to get know what the file is about eh? But, the "working" BF plugin doesn't return the mpGetOptions FILEFIND options, just an emtpy string. So I have no way to get the fields, are do you have default fields to give in mpFindInfo?

of course, remember that i change a WHOLE LOT OF STUFF with the new manager, when you made me write a plugin that tested about 99% of the functionality.  So the BF plugin does need to be updated

> Reply from Mr.Mouse
>
> Edit2: OpenArchive crashes the whole IDE now. Perhaps due to the Cardinal there? Or the LongBool return? Please check your PM.

shouldn't perhaps you forgot to take out the CreateParams value?
## Post #226
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-03T23:14:03+00:00
- Post Title: 

do you want a WORKING delphi application? or how it SHOULD work for you, but in delphi?

I have talored the Manager to work with VB, and because of VB crazy dll talking, i've had to do some special.  So if i wrote a working application, it would do have to do some cleanup, that VB does automatically and stuff like that.
## Post #227
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-03T23:22:43+00:00
- Post Title: 

I guess it's just all the new manager source (functions, declares, consts) etc. 

No need to rewrite it
## Post #228
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-04T00:29:54+00:00
- Post Title: 

```

function GetManagerVersion(var Major, Minor: LongInt): LongBool; stdcall;
function GetSupportedInterfaceVersion(var Major, Minor: LongInt): LongBool; stdcall;
function SetPluginDirectory(Directory: PChar): LongBool; stdcall;
function RefreshPluginList(): LongBool; stdcall;
function PluginCount(): LongInt; stdcall;
function PluginInfo(Index: LongInt; var MyPluginInfo: TManagerPluginInfo): LongBool; stdcall;
function FreeCache():LongBool; stdcall;
function SetCacheSize(Size: LongInt):LongBool; stdcall;

// Plugin Calls

function mpGetFormatCount(): LongWord; stdcall;
function mpGetFormatInfo(FormatIndex: LongInt; var FormatInfo: TFormatInfo): LongBool; stdcall;
function mpGetOptions(FormatIndex: LongInt; OptionType: LongInt): PChar; stdcall;
function mpSetOption(FormatIndex: LongInt; OptionType: LongInt; Name: PChar; Value: PChar): LongBool; stdcall;
function mpOpenArchive(var ArchiveHandle: LongInt; FormatIndex: LongInt; ArchiveName: PChar; Flags: Cardinal): LongBool; stdcall;
function mpOpenArchiveBindStream(var ArchiveHandle: LongInt; FormatIndex: LongInt; Stream: IStream; Flags: Cardinal): LongBool; stdcall;
function mpCloseArchive(FormatIndex: LongInt; ArchiveHandle: LongInt): LongBool; stdcall;
function mpIndexCount(FormatIndex: LongInt; ArchiveHandle: LongInt): LongInt; stdcall;
function mpIndexedInfo(FormatIndex: LongInt; ArchiveHandle: LongInt; Index: LongInt; Item: PChar): PChar; stdcall;
function mpFindInfo(FormatIndex: LongInt; Handle: LongInt; Field: PChar): PChar; stdcall;
function mpFindFirstFile(FormatIndex: LongInt; ArchiveHandle: LongInt; FileMask: PChar): LongInt; stdcall;
function mpFindNextFile(FormatIndex: LongInt; FindHandle: LongInt): LongBool; stdcall;
function mpFindClose(FormatIndex: LongInt; FindHandle: LongInt): LongBool; stdcall;
function mpIsFileAnArchive(FormatIndex: LongInt; Filename: PChar): LongBool; stdcall;
function mpIsStreamAnArchive(FormatIndex: LongInt; Stream: IStream): LongBool; stdcall;
function mpExportFileByNameToFile(FormatIndex: LongInt; ArchiveHandle: LongInt; ArchiveFile: PChar; ExternalFile: PChar): LongBool; stdcall;
function mpExportFileByIndexToFile(FormatIndex: LongInt; ArchiveHandle: LongInt; FileIndex: LongInt; ExternalFile: PChar): LongBool; stdcall;
function mpExportFileByNameToStream(FormatIndex: LongInt; ArchiveHandle: LongInt; ArchiveFile: PChar; Stream: IStream): LongBool; stdcall;
function mpExportFileByIndexToStream(FormatIndex: LongInt; ArchiveHandle: LongInt; FileIndex: LongInt; Stream: IStream): LongBool; stdcall;
function mpImportFileFromFile(FormatIndex: LongInt; ArchiveHandle: LongInt; ArchiveFile: PChar; ExternalFile: PChar): LongBool; stdcall;
function mpImportFileFromStream(FormatIndex: LongInt; ArchiveHandle: LongInt; ArchiveFile: PChar; Stream: IStream): LongBool; stdcall;
function mpRemoveFileByName(FormatIndex: LongInt; ArchiveHandle: LongInt; Filename: PChar): LongBool; stdcall;
function mpRemoveFileByIndex(FormatIndex: LongInt; ArchiveHandle: LongInt; FileIndex: LongInt): LongBool; stdcall;
function mpGetLastError(FormatIndex: LongInt): Cardinal; stdcall;
function mpGetErrorText(FormatIndex: LongInt; Value: Cardinal): PChar; stdcall;
```


that it?
## Post #229
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-07T00:42:46+00:00
- Post Title: 

Saw this, didn't know if maybe you wanted to read it.

[http://www.vbaccelerator.com/home/VB/Ty ... rticle.asp](http://www.vbaccelerator.com/home/VB/Type_Libraries/Stream/article.asp)
## Post #230
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-07T08:08:07+00:00
- Post Title: 

> Reply from Rahly
>
> Saw this, didn't know if maybe you wanted to read it.

http://www.vbaccelerator.com/home/VB/Ty ... rticle.asp

Ah yes, something like that may come in handy in the future.
## Post #231
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-09T00:39:05+00:00
- Post Title: 

Hey, i'm also looking at the prospect of binding with explorer, similar to how ZIP files are implemented in XP.
## Post #232
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-11T21:30:13+00:00
- Post Title: 

Example



this binds .fpk archives (from Sid Meier's Pirates!) with explorer.
## Post #233
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-12T06:39:09+00:00
- Post Title: 

That is nice stuff.
## Post #234
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-08-12T06:51:45+00:00
- Post Title: 

Awesome!
## Post #235
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-29T22:09:13+00:00
- Post Title: 

Are there any examples of a Delphi plug-in or plug-in manager?
I want to make one.
## Post #236
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-30T05:09:57+00:00
- Post Title: 

it was just released this week, i haven't had time to finish the documentation yet.  nor have i finished the C/C++ header files for generating a plugin.
## Post #237
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T17:56:17+00:00
- Post Title: 

Can you send me a copy of the current Common.pas and the list of mp* function definitions? I don't know if the ones in this topic are still current and wouldn't want to get it wrong.
## Post #238
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T22:40:06+00:00
- Post Title: 

On the current API: it might be possible to change the PChar arguments to WideString. That would make it not reference counted and prevent certain problems. Visual Basic will just take it... but I cannot easily check.

Returning strings (PChar) in DLL functions (also WideStrings) generally leads to problems. Do these functions work right now?
## Post #239
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-31T22:50:10+00:00
- Post Title: 

I'll have a plugin skeleton shortly, PChars are not referenced counted, AnsiStrings are.

And VB Doesn't take it.  ByVal Value as String <--- VB converts a UTF-16 String to an Ansi String.  I'm trying to see if i can find a better way to get WideStrings, as I would like to have that implemented in a later version.

MrMouse and I have spend a few hours just getting strings to work.  PChar is what the plugins use as its easy for a C/C++ pluging to make a char* and delphi already has support (PChar).  The plugin manager itself acts as a buffer between MexCom and the Plugins.  There are a few reasons that make VB a terrible language to implement plugins in.
## Post #240
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T23:27:24+00:00
- Post Title: 

> Reply from Rahly
>
> 
MrMouse and I have spend a few hours just getting strings to work.  PChar is what the plugins use as its easy for a C/C++ pluging to make a char* and delphi already has support (PChar).  The plugin manager itself acts as a buffer between MexCom and the Plugins.  There are a few reasons that make VB a terrible language to implement plugins in.

I know, I've spend days on it in the past. And got it to work eventually. The 'correct' way to return a string (this is what I used anyway):

```
  function PlugInVersions(Path: PChar; BufferSize: Integer; var Buffer: PChar): Integer; stdcall; forward;
```

(returning string length as function result).

```
    Buffer[i-1]:=tmpDynaFile[i];
  end;
  Buffer[Length(tmpDynaFile)]:=#0;
  Result:=Length(tmpDynaFile);

```

And this would return something. But note that this code does not check BufferSize, which is a requirement these days. Wouldn't want buffer overflows.
This is the corresponding VB declaration and code:

```

Function GetPluginLiveUpdateInfo() As String
  Dim Buffer As String * 255
  Dim q As Long
  q = PlugInVersions(DataDir$, 255, Buffer)
  GetPluginLiveUpdateInfo = Left$(Buffer, q)
End Function

```

Might be useful.
## Post #241
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-01T00:23:39+00:00
- Post Title: 

> Reply from Neko
>
> I know, I've spend days on it in the past. And got it to work eventually. The 'correct' way to return a string (this is what I used anyway):
Code: Select all  function PlugInVersions(Path: PChar; BufferSize: Integer; var Buffer: PChar): Integer; stdcall; forward;
(returning string length as function result).
Code: Select all  for i:=1 to Length(tmpDynaFile) do begin
    Buffer[i-1]:=tmpDynaFile[i];
  end;
  Buffer[Length(tmpDynaFile)]:=#0;
  Result:=Length(tmpDynaFile);

And this would return something. But note that this code does not check BufferSize, which is a requirement these days. Wouldn't want buffer overflows.
This is the corresponding VB declaration and code:
Code: Select allPrivate Declare Function PlugInVersions Lib "tibedhlp.dll" (ByVal Path As String, ByVal BufferLength As Long, BufferText As String) As Long

Function GetPluginLiveUpdateInfo() As String
  Dim Buffer As String * 255
  Dim q As Long
  q = PlugInVersions(DataDir$, 255, Buffer)
  GetPluginLiveUpdateInfo = Left$(Buffer, q)
End Function

Might be useful.

Too much work for Mr.Mouse   better to just return a PChar thats compatible with VB.  The main problem with VB is that if you return a string, vb tries to free that memory itself, so you CAN'T make memory with Delphi's memory manager or your fubar things there.  In fact, windows gives you some GREAT functions to do it, as VB uses the same functions.  Thereby, it simplifies my end as well as Mr.Mouse's end, doesn't worry about buffer overflows, can still use delphi strings internally, and it works via a single call where he doesn't have to write a wrapper.  I had 3 goals in mind, multiple language support, ease for MrMouse to implement, and functionality.
## Post #242
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-01T00:33:17+00:00
- Post Title: 

oh and again, the manager handles all this, doesn't matter what the plugin does.
## Post #243
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-01T07:43:14+00:00
- Post Title: 

I recently noticed a function in VB that would convert UNICODE strings. The problem is that this stuff is not possible in dll-calls.
## Post #244
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-06T05:47:43+00:00
- Post Title: 

Skeleton plugin for delphi is done, I'll be releasing it the same time i've finished updating the BF plugin.
## Post #245
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-06T06:23:01+00:00
- Post Title: 

Awesome!
## Post #246
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T02:26:12+00:00
- Post Title: 

This is kinda better, now i have a final product to work with 

I'm already thinking of new ideas for the new one
## Post #247
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T03:52:57+00:00
- Post Title: 

Small problem,

BF plugin only supports the OPENFLAG_FOREXPORT

if the plugin doesn't have SUPPORTFLAG_CREATE, then OPENFLAG_CREATENEW and OPENFLAG_OPENALWAYS shouldn't be passed, as CREATENEW OPENALWAYS

CREATENEW = overwrite file with a new archive
OPENALWAYS = if archive file doesn't exist create a new one
## Post #248
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-07T07:06:02+00:00
- Post Title: 

Hmm. Allright, we can take a look at that. The problem was that your test plugin didn't work if I just used FOREXPORT, I HAD to give the other flags as well. We discussed this be email as well.
## Post #249
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T10:31:36+00:00
- Post Title: 

I thought we fixed that, and I sent you another version.
## Post #250
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-07T11:05:19+00:00
- Post Title: 

Interesting. Anyway. A new version is easily released, this is just small fix. I will take care of that.
## Post #251
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T11:16:23+00:00
- Post Title: 

wait a min on that, i have to check something else out too.
## Post #252
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-07T11:25:31+00:00
- Post Title: 

Ok
## Post #253
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T11:38:58+00:00
- Post Title: 

screens of the BF plugin




Exports good as well
## Post #254
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-07T11:40:13+00:00
- Post Title: 

W00t!!
## Post #255
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T11:49:37+00:00
- Post Title: 

what do you mpGetOptions() for when you startup?
## Post #256
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-07T11:59:33+00:00
- Post Title: 

I'll release them tonight.  Also I was thinking of reviving your Eureka project but with a major modification.
## Post #257
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-07T12:03:44+00:00
- Post Title: 

@the release: Okido! 

@Eureka: it was rather dead wasn't it   I'll await your "modification".
## Post #258
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-08T02:00:46+00:00
- Post Title: 

Some more goodies

Plugin for Sid Meier's Pirates *.FPK files
## Post #259
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-08T02:07:00+00:00
- Post Title: 

Release

[BF plugin](http://www.terrygoodkind.net/~rahly/BFFileFormat.zip) for the Prince of Persia games and Beyond Good and Evil (quite possibly, it'll work with other Ubisoft games that use the same Engine.)
[FPK plugin](http://www.terrygoodkind.net/~rahly/FPKFileFormat.zip) for the Sid Meier's Pirates! game
[Skeleton](http://www.terrygoodkind.net/~rahly/Skeleton.zip) delphi source for a plugin, just fill in the blanks, rename, and compile.
## Post #260
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-08T07:34:24+00:00
- Post Title: 

This is great. I tested the BF one and it works. 

I noticed my code in MexCom for online update of RPM plugins was rather lame, it will try to download a DLL for each game (while in cases such as the BF one only one DLL rules them all). Stupid me. Damn rush work. Anyway, users can just put them in the data/rpm directory and they'll work. Meanwhile,I'll try to get a new version out that handles this better.
## Post #261
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-08T07:48:43+00:00
- Post Title: 

I've found a bug in the POP extraction. See screenshot:
[popbfcorrupt.jpg](https://xentaxbackup.github.io/file/425_popbfcorrupt.jpg)
## Post #262
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-08T10:49:38+00:00
- Post Title: 

What file?
## Post #263
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-08T11:00:45+00:00
- Post Title: 

It says in the screenshot...popdata.bf
## Post #264
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-09T00:44:50+00:00
- Post Title: 

Kopie van POPData.bf?

sorry i don't have that file my game, perhaps its not a real bf file?

I do have a POPData.bf though, but its not in bf format, in fact.. my plugin will refuse to open it, although, your mexcom script opens it and gives me the same error you gave me.  Perhaps its a script error?

EDIT:

Prince of Persia(*.BF) = My plugin works on Prince.bf but "Can't open" POPData.bf
Prince of Persia - Warrior Within(*.BF) = mex script
Prince of Persia SOT(*.BF) = mex script works on POPData.bf with errors but fails on prince.bf
## Post #265
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T05:24:49+00:00
- Post Title: 

lol , anyway, why won't it open with the plugin?
## Post #266
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-09T13:20:20+00:00
- Post Title: 

That BF files isn't a real BF file, not one the game itself uses

BF files in the POPs and BG&E or anything that uses the same gaming engine, all have headers that begin with the "BIG" signature, POPData.bf begins with an S

I think POPData.bf is used only for the in game menu, which doesn't use the gaming engine.
## Post #267
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T20:26:20+00:00
- Post Title: 

Hmmm for plugin uses ActiveX ?  
Yes here still I have compiled Skeleton plugin source but MultiEx Commander it not distinguishes as a plug-in why that: (... Though like all it is correctly written. Can you will send a source code of an available plug-in?
## Post #268
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T20:42:30+00:00
- Post Title: 

No, but you should have the plugin dll in the data/rpm directory. 

You must also make sure some options are returned. MultiEx Commander will check for certain options, such as Create, Extract, Import etc.
## Post #269
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T20:55:09+00:00
- Post Title: 

Yes certainly compiled I have put a plug-in in a folder data/rpm and to not be loaded why that: (
## Post #270
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T20:55:33+00:00
- Post Title: 

To Rahly:
I call mpGetOptions for this: 

```

res = ParseRFileInfo(str, RPMPlugins(t).Fileinfo)
```


I want to know upon start-up what each plugin can do.
## Post #271
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T20:59:32+00:00
- Post Title: 

> Reply from KorNet
>
> Yes certainly compiled I have put a plug-in in a folder data/rpm and to not be loaded why that: (

Can you find a reference in the debug.log file of MultiEx Commander (CTRL+L) when MultiEx has loaded? 

Please attach the dll here, so Rahly and I can also take a look.
## Post #272
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T21:02:08+00:00
- Post Title: 

Sure

```
-----------------------------------------
mc32, C:\Program Files\MultiEx Commander
4.2.0
-----------------------------------------
10.09.2005, 0:59:21
0:59:21[i]-  ]-WebUpdate: user selected :3
0:59:21[i]-  0:59:21- Main : Opening MRF file
0:59:22[i]-  -Main : AddRahlyPlugins->RPM at pluginmanager.dll for Rahly's Test Archive
0:59:23[i]-  -Main : AddRahlyPlugins->RPM at pluginmanager.dll for Beyond Good and Evil
0:59:23[i]-  -Main : AddRahlyPlugins->RPM at pluginmanager.dll for Prince of Persia
0:59:23[i]-  -Main : AddRahlyPlugins->RPM at pluginmanager.dll for Sid Meier's Pirates!
0:59:23[i]-  -Main : Mex_FindPlugins
0:59:23[i]-  -Main : Mex_FindPlugins->Searching
0:59:23[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
0:59:23[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll
0:59:23[i]-  -Main : RunAnalysis->Progid to connect to Sacrifice.archive
0:59:23[i]-  Sacrifice WAD Files Extractor
0:59:23[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
0:59:23[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll
0:59:24[i]-  -Main : RunAnalysis->Progid to connect to Painkiller.archive
0:59:24[i]-  Painkiller PAK Files Extractor
0:59:24[i]-  PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
0:59:24[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\idx\Survival.dll for Survival
0:59:24[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\idx\Survival.dll
0:59:25[i]-  -Main : RunAnalysis->Progid to connect to Survival.archive
0:59:25[i]-  Survival IDX/PAK format Extractor
0:59:25[i]-  PlugIn Called: Survival IDX/PAK format Extractor version 1.0, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
0:59:25[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\fpk\WWE.dll for WWE
0:59:25[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\fpk\WWE.dll
0:59:26[i]-  -Main : RunAnalysis->Progid to connect to WWE.archive
0:59:26[i]-  WWE Raw 2 FPK Files Extractor
0:59:26[i]-  PlugIn Called: WWE Raw 2 FPK Files Extractor version 1.0, type (2), importation(1), varsreturned(3), restypespec(0), cancreate(0)
0:59:26[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\d64\Commodore_64_disk_files.dll for Commodore_64_disk_files
0:59:26[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\d64\Commodore_64_disk_files.dll
0:59:26[i]-  -Main : RunAnalysis->Progid to connect to Commodore_64_disk_files.archive
0:59:26[i]-  Commodore 64 D64 disk format Extractor
0:59:26[i]-  PlugIn Called: Commodore 64 D64 disk format Extractor version 1.0, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
0:59:26[i]-  -Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\cnt\Rayman3.dll for Rayman3
0:59:26[i]-  -Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\cnt\Rayman3.dll
0:59:27[i]-  -Main : RunAnalysis->Progid to connect to Rayman3.archive
0:59:27[i]-  Rayman 3 CNT Files Extractor
0:59:27[i]-  PlugIn Called: Rayman 3 CNT Files Extractor version 0.9, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
0:59:27[i]-  - Main : Loading 
0:59:27[i]-  - Main : Creating Panels 
0:59:27[i]-  - Main : Setting Variables 
0:59:28[i]-  - Main : Preparing Datafile List Columns 
0:59:28[i]-  - Main : Setting Additional Variables
0:59:28[i]-  - Main : Loading SupportForm
0:59:28[i]-  - Main : Setting FileFilter
0:59:29[i]-  - Main : Enabling All
0:59:29[i]-  - Main : Creating New Instance
0:59:29[i]-  - Main : Showing Program
0:59:30[i]-  - Main : BASS Init called.
0:59:30[i]-  - Main : DevIL Init called.

```


Suspiciously
0:59:22[!]- RPM Parse FileInfo error 
0:59:22[!]- RPM Parse FileInfo error 
0:59:22[!]- RPM Parse FileInfo error
## Post #273
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T21:31:08+00:00
- Post Title: 

Yes, ok, I see the plugin is not found. That means that Rahly's pluginmanager does not detect your plugin as a valid one. I think you should take this up with Rahly. 

The Parse error is a bug. There is no error. I will fix that in a new release
## Post #274
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T21:33:49+00:00
- Post Title: 

Perfectly... But here the source code of a ready plug-in does not need to be looked
## Post #275
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T21:43:52+00:00
- Post Title: 

> Reply from KorNet
>
> Perfectly... But here the source code of a ready plug-in does not need to be looked

Correct, but I don't have that source code. Rahly does. Until he wakes up at his end of the world (the US), we'll probably be asleep (Moscow time  ).  Let's just wait for him.
## Post #276
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:04:34+00:00
- Post Title: 

We wait Rahly... I Hope it to share the initial text of any ready plug-in
## Post #277
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-09T23:47:46+00:00
- Post Title: 

don't use "Skeleton" as your plugin name

4 things

1) plugin manager calls mpGetInterfaceVersion, and the interface version it returns MUST be 1.0

2) plugin manager calls mpGetPluginInfo, and this has to return valid information, this should be set up for you already

if the above is good, then its a valid plugin, please note that MrMouse ONLY displays formats, not actual plugin information, in this case, there can be zero or more formats, so it could be a valid plugin and seen

ok to be seen by MrMouse, you need to

3) plugin manager calls mpGetFormatCount to get the number of formats that the plugin supports

4) plugin manager calls mpGetFormatInfo to get the information of the plugin, this is zero based, for example, if mpGetFormatCount = 2 then mpGetFormatInfo will be called for formats 0 and 1

after this, MrMouse will show you the list of formats in the Rahlys Plugin Manager view.
## Post #278
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:55:41+00:00
- Post Title: 

Rahly can you will make a sketch of a plug-in if to you not difficultly?
## Post #279
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-09T23:57:40+00:00
- Post Title: 

i can release the code for the test plugin, which was my plan, but i have to talk to MrMouse first.
## Post #280
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-09T23:58:16+00:00
- Post Title: 

i can post example code for those functions though.
## Post #281
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-10T00:17:01+00:00
- Post Title: 

I have disassembled not few game formats and it would be desirable to try to write plug-ins... As programs for extraction are written... I even created a theme such.. And and so the list

3D Mark 2003 - DAT
3D Mark 2004 - DAT
3D Mark 2005 - DAT
Colin McRally 2004 - BIG
Colin McRally 2005 - BIG
Cossacks - GSC
Crimsonland - PAQ
Dungeon Siege - BAM
Dungeon Siege - GAF
Dungeon Siege - DS
Dungeon Siege - TVC
Dungeon Siege - DSSAVE
Dungeon Siege - DSQSAVE
Dungeon Siege - DSPARTY
Dungeon Siege - DSMAPS
Dungeon Siege - DSRES
Dungeon Siege 2 - DSRES
Earth 2140 - WD
Earth 2150 - WD
FlatOut - BFS
Grand Theft Auto 3 - IMG
Grand Theft Auto 3 - SFX
Grand Theft Auto Vice City - ADF
Grand Theft Auto Vice City - IMG
Grand Theft Auto San Andreas - IMG
Grand Theft Auto San Andreas - MUSIC
Hitman Contracts - TEX
Jame Bond 007 - 007
Liero - SND
Majesty - CAM
DarkStone - MTF
Die By The Sword - ATD
Raindow Six - RSB
Rally Challange - RFF
Sacred - TEXTURES
Sacred - SOUNDS
Sacred - MODELS
Scorher - BIN
Silent Hill 2 - ASF
The Sims 2 - PACKAGE
Space Rangers - PKG
Space Rangers - GAI
Space Rangers - GUI
Space Rangers 2 Dominators - PKG
Space Rangers 2 Dominators - GAI
Space Rangers 2 Dominators - GUI
Syberia 2 - SYB
Vanguard Ace - DIR
Worms Armageddon - DIR
Worms World Party - DIR
Operation Flashpoint Cold War - PBO
Operation Flashpoint Resistance - PBO
Wacky Wheels - DAT
ZoneRaides - MAS
Macromedia Flash - EXE -> SWF
## Post #282
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-10T00:23:26+00:00
- Post Title: 

kewl, so do you want that example code?
## Post #283
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-10T00:38:34+00:00
- Post Title: 

Certainly... I shall try to make a working plug-in of an example
[z0omik@mail.ru](mailto:z0omik@mail.ru)
## Post #284
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-09-10T01:25:45+00:00
- Post Title: 

mpGetInterfaceVersion

```
begin
  Major := InterfaceVersionMajor;
  Minor := InterfaceVersionMinor;
  Result := True;
end;
```


this should be done for you already

mpGetPluginInfo

```
begin
  Result := False;
  if Info.Size = SizeOf(TPluginInfo) then
    begin
    Info.Name := 'Sample Plugin';
    Info.Author := 'Rahly';
    Info.URL := 'http://dl748.com/';
    Info.Email := '';
    Info.Major := 1;
    Info.Minor := 0;
    Result := True;
    end
  else
    LastError := pERROR_INVALID_PARM_1;
end;
```


make sure you fill in the data with YOUR information

now for the formats information, i make a const variable to hold my data for easy additions

```
  MyFormats: Array[0..0] of TFormatInfo =
    (
      (FileMask: '*.rta'; GameName: 'Rahly''s Test Archive'; Flags: SUPPORTFLAG_CREATE or SUPPORTFLAG_IMPORT or SUPPORTFLAG_EXPORT or SUPPORTFLAG_DELETE or SUPPORTFLAG_BYINDEX or SUPPORTFLAG_BYNAME or SUPPORTFLAG_HANDLEFILE or SUPPORTFLAG_TESTARCHIVE)
    );
```


mpGetFormatCount

```
begin
  Result := Length(MyFormats);
end;
```


mpGetFormatInfo

```
begin
  Result := False;
  if (FormatIndex >= 0) and (FormatIndex < Length(MyFormats)) then
    begin
    if (FormatInfo.Size >= SizeOf(TFormatInfo)) then
      begin
      FormatInfo.FileMask := MyFormats[FormatIndex].FileMask;
      FormatInfo.GameName := MyFormats[FormatIndex].GameName;
      FormatInfo.Flags    := MyFormats[FormatIndex].Flags;
      Result := True;
      end
    else
      LastError := pERROR_INVALID_PARM_1;
    end
  else
    LastError := pERROR_INVALID_FORMAT;
end;
```


the size check is for changes in format

I'll post the Test Plugin as soon as i talk to MrMouse
## Post #285
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-10T15:00:13+00:00
- Post Title: 

Okey .. I am waitng .
## Post #286
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-11T13:14:58+00:00
- Post Title: 

Rahly, the updated plugins/manager cause problems with MexCom (the strings I get like filename etc contain illegal characters.)
[beyondcor.jpg](https://xentaxbackup.github.io/file/433_beyondcor.jpg)
## Post #287
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-14T23:34:16+00:00
- Post Title: 

Well when will be Test Plugin?
## Post #288
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-30T17:46:44+00:00
- Post Title: 

Rahly - as the matters with plugins? there are what updating?
## Post #289
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-30T23:42:08+00:00
- Post Title: 

updating? the plugins work, Mr Mouse was just using older plugins for some reason, he figured it out a few weeks ago i think, the new ones work fine
## Post #290
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T06:17:07+00:00
- Post Title: 

Yep, they work fine in the new release.
## Post #291
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-31T15:34:03+00:00
- Post Title: 

Nice what is new ?
## Post #292
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-31T18:55:01+00:00
- Post Title: 

Several things.

New compiler
New specialized CVS-like software
File Analyst
