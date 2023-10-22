## Post #1
- Username: Kenny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 18, 2011 9:58 pm
- Post datetime: 2013-02-10T22:58:26+00:00
- Post Title: Chrono Tales: gpak files

Hello there. I would like to request help for the game Chrono Tales. It's a browser based game where it stores data files in the AppData Folder.

I'm trying to get best quality pictures of icons and such for an upcoming wiki I'll be creating for it, but I can't seem to find any way to extract it.

There are two files which contains all the stuff I'm after (models etc):
netpak.gpak (494mb)
sysnet.gpak (9mb)

I'll assume netpack contains all the juicy stuff, but for now I've uploaded sysnet for you to have a crack at.

[http://www.mediafire.com/?5aqwz2o8rtaz5y0](http://www.mediafire.com/?5aqwz2o8rtaz5y0)

Many Thanks,

Kenny
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-11T12:11:44+00:00
- Post Title: Chrono Tales: gpak files

The files are definitely encrypted.
The main file is also dynamically growing and only sends the data when you see the items / characters in game.
## Post #3
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-17T12:36:30+00:00
- Post Title: Chrono Tales: gpak files

@chrrox no offense but I think you are wrong about the netpak.gpak file - it's downloaded in the background until you have all of it weather you have seen the items or not.

After looking at the lm.gbox file I found some interesting strings:
inflate 1.1.3 Copyright 1995-1998 Mark Adler
unzip 0.15 Copyright 1998 Gilles Vollant
E:\GBox2\src\pub\base\RSA.cpp

And a file I believe is not encrypted like the netpak.gpak file that you can get yourself (inside lm.gbox) or download ZIP-ed version from: [http://www.filedropper.com/system](http://www.filedropper.com/system)

P.S. I'll also appreciate some help in getting access to the files content.
P.P.S. I also believe they use the same format for there other games: Dragon`s Call, Dragon`s Call II, Serenia Fantasy and Soul of Guardian.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-17T13:49:22+00:00
- Post Title: Chrono Tales: gpak files

try clearing your data and create a new character you will see the game does not increase in size until you start switching characters and using new abilities . items.
also those strings you found are present in almost every exe ever made that uses compression.
also that file you mention defiantly looks encrypted what makes you say it is not.
## Post #5
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-17T16:00:16+00:00
- Post Title: Chrono Tales: gpak files

Probably all the text plainly seen in it, for example the one at the end of the file:

```
void CreateDefShadow()
{
	obj p;
	p=FindInterface("_ShadowObj");
	if (!p.isobj()) {
		p=new GObj3DShadowSSM;
		p.m_nShow=0;
		RegInterface(p,"_ShadowObj");

#ifdef _GBOX_MON
		obj page;
		if (GSysCtrlBoard::s_pCtrl.isobj()) {
			page=GSysCtrlBoard::s_pCtrl.GetCtrlPage("ТхУ°");

			page.AddCheck("¶ЇМ¬ТхУ°",p,"g_nShadow");
			page.AddCheck("ПФКѕТхУ°Нј",p,"m_nShow",0);
			page.AddCheck("ИнТхУ°",p,"m_nSoftness",0);
			page.AddCheck("ёфЦЎдЦИѕ",p,"m_nSkipRender",0);
			page.AddHSwitch("МщНјіЯґз",p,"m_nTextLevel",0,3);
			page.CrLine();
			page.AddHSwitch("ЧоґуѕаАл",p,"m_fMaxDis",1,200);
			page.AddHSwitch("m_fFov",p,"m_fFov",5,180);
			page.AddHSwitch("DepthBias",p,"m_fDepthBias",0,0.001);
			page.AddHSwitch("BiasSlope",p,"m_fBiasSlope",0,8);
			page.CrLine();
			page.AddHSwitch("m_fT0",p,"m_fT0",0,20);
			page.AddHSwitch("m_fT1",p,"m_fT1",-10,10);
			page.AddHSwitch("m_fT2",p,"m_fT2",0,0.5);
			page.AddHSwitch("m_fT3",p,"m_fT3",-1,1);

			page.AddObj(p.GetWidth(),p.GetHeight(),p);
		}
#endif _GBOX_MON
		
	}
	if (FindInterface("_ЦчПа»ъ").isobj()) {
		m_i_ЦчПа»ъ.m_pShadowObj=p;
	}
}
class _SysOcean:GObj3DWaterEx
{
#ifdef _GBOX_MON
	void OnCreate(){
		//SetRefract(0.17,9);
		InitWater(_SYSFXPATH+"GObj3DWaterEx.fx",_SYSFXPATH+"sysfx/wave0.jpg",_SYSFXPATH+"sysfx/wave1.jpg");
		obj page;
		if (GSysCtrlBoard::s_pCtrl.isobj()) {
			page=GSysCtrlBoard::s_pCtrl.GetCtrlPage("єЈСу");
			page.AddCheck("Л®Гж·ґЙд",this,"m_nReflectMap");
			page.AddCheck("Йо¶ИНёГч",this,"m_nDepthFade");
			page.AddCheck("µчКФПЯїт",this,"m_nWireframe");
			page.CrLine();
			page.AddHSwitch("·ґЙд±ИАэ",this,"m_fRefractBias",0,1);
			page.AddHSwitch("ёЯ№вЦёКэ",this,"m_fRefractPower",2,200);
			page.AddHSwitch("НёКУѕаАл",this,"m_fLookalphaDis",0.01,1);
			page.AddHSwitch("Жр·ь±ИАэ",this,"m_fZscale",0.0001,2);
			page.CrLine();
			page.AddHSwitch("СХЙ«_R",this,"m_nWater_R",1,255);
			page.AddHSwitch("СХЙ«_G",this,"m_nWater_G",1,255);
			page.AddHSwitch("СХЙ«_B",this,"m_nWater_B",1,255);
			page.CrLine();
			page.AddHSwitch("Alpha",this,"m_nAlpha",0,255);
		}
	}
#endif _GBOX_MON
}
void CreateDefWorldCamera(string mainworldstyle,string sky="")
{
	obj p,pworld;
	obj pca=new _SysDefMainCamera;
	pworld=new _SysDefworld;
	m_i_MainSky.SefSky(sky);
	pca.SetLootWorld(m_i_MainWorld);
	pworld.UseStyle(mainworldstyle);
//	CreateDefShadow();
};
//g_pDeskTop.CopyModelFiles(this);
void CopyModelFiles(obj pmodel)
{
	string fname;
	var filesz,sz;
	var allinfo=pmodel.GetCreateInfo();
	int i;
	i=0;
	//µИґэready
	while(allinfo.isnull() && i<5) {
		Wait(100);
		allinfo=pmodel.GetCreateInfo();
		i++;
	}
	if (allinfo.size()<4) {
		Err("not get GetCreateInfo");
		return;
	}
	string destpath;
	destpath=file::BrPathDlg("СЎФсcopyВ·ѕ¶");
	if (destpath.GetLength()<1) return;

	fname=allinfo[0];
	filesz.AddSz(fname);
	sz=allinfo[1];
	for(i=0;i<sz.size;i++) {
		?fname=sz[i];
		filesz.AddSz(fname);
	}
	sz=allinfo[2];
	for(i=0;i<sz.size;i++) {
		?fname=sz[i][1];
		filesz.AddSz(fname);
	}
	string path,name;
	for(i=0;i<filesz.size;i++){
		fname=filesz[i];
		if (fname.GetLength()>0) {
			file::SlipFileName(path,name,fname);
			if (file::CopyFile(fname,destpath+name)) {
				?"Copy "+destpath+name;
			}
		}
	}
}

#endif// _SYSTEM3D_
SetBkColor(0xFFA0A0A0);
class ViewModel:GObj2DShape
{
	class GViewWorld:_SysDefworld
	{
		GObj3DCoordinate m_pC;
		GObj3DSkMesh m_pViewObj{
			m_nCanMouse=1;
			void OnPopAniMenu()
			{
				var v;
				int i=GetAni(v);
				if (i<1) return;
				MENU_BEGIN;
					for(i=0;i<v.size();i++) {
						MENU_ITEM(v[i],this,"OnPlayAni",(v[i]));
					}
				MENU_ENDPOP;
			}
			void OnPopMatMenu()
			{
				var v;
				int i=GetAllTextureName(v);
				if (i<1) return;
				MENU_BEGIN;
					for(i=0;i<v.size();i++) {
						MENU_ITEM(v[i][0],this,"OnMat",(v[i]));
					}
				MENU_ENDPOP;
			}
			void OnPlayAni(string aniname)
			{
				SetAniKind(aniname);
				PlayAni(15);
			}
			void OnMeshReady()
			{
				vector3 p=(m_vCullBoxMax+m_vCullBoxMin)/2;
				m_i_ЦчПа»ъ.SetLootOffset(0,0,p.z);
			}
			g_pDeskTop.RegInterface(this, "_focusMan");
		};
	};
	class GViewCamera:_SysDefMainCamera{
		m_fFov=23;
		m_nClearBk=3;
		SetLootWorld(pid.m_pWorld);
		SetLootAt(pid.m_pWorld);
		SetLootOffset(0,0,1);
		m_fRotoZ=230;m_fLookDis=8;
		new BkRect(#FF505050);
		SetPos(100,24);
		AutoSize(100,100,-100,-24);
		m_nCanMouse=m_nCanMouse|FINDMOUSE_MK_DROPFILE;
		void OnDropFiles(var v)
		{
			string name;
			name=v[0];
			?name;
			string ext=file::GetFileExtName(name);
			switch(ext) {
			case "cmz":
			case "fw3":
			case "gmesh":
				pid.m_pWorld.m_pViewObj.LoadMesh(name);
				break;
			case "zip":
				pid.m_pWorld.m_pViewObj.ImportAni(name);
				break;
			}
		}
	}
	obj m_pWorld,m_pCamera;
	GSysImgBtn m_pBtnAct:SetDefText(148,2,"¶ЇЧч"){
		void OnClick()
		{
			m_i_focusMan.OnPopAniMenu();
		}
	}
	GSysImgBtn m_pBtnMat:SetDefText(248,2,"ІДЦК"){
		void OnClick()
		{
			m_i_focusMan.OnPopMatMenu();
		}
	}
	style:AutoSize;
	AutoSize(100,100,0,0);
	void Open(string fullname)
	{
		?fullname;
		m_pWorld=new GViewWorld;
		m_pWorld.m_pViewObj.LoadMesh(fullname);
		m_pCamera=new GViewCamera;
	}
}
class ViewVideo:GObj2DShape
{
	GVideoPlay m_player;
	RegInterface(m_player,"Player");
	class VideoCtrls:GObj2DShape
	{
		//SetAutoSize(1);
		FillColor(#8F999999,0);
		m_nCanMouse=3;
		m_nZpos=1000;
		GObj2DTextEx m_pShowInfo{
			SetText("?");
			SetFont("ЛОМе",6,12,400,0,0,1);
			SetPos(220,32);
			SetColor(#FFFFFFCC);
			void Update()
			{
				SetText(m_iPlayer.GetCurInfo());
			}
			SetShowFun("Update");
		};
		GSysHSwitch m_Prog:(20,10,700,18,0,100,pid.m_player,"m_fCurPosPer",0){
			m_pBk.m_pBk.FillColor(#AF403369,0);
		}
		GSysImgBtn m_pPlayBtn:SetDefText(20,30,"Play")
		{
			void OnClick()
			{
				m_iPlayer.Play();
			}
		}
		GSysImgBtn m_pPauseBtn:SetDefText(80,30,"||")
		{
			void OnClick()
			{
				m_iPlayer.Pause();
			}
		}
		GSysImgBtn m_pStopBtn:SetDefText(140,30,"Stop")
		{
			void OnClick()
			{
				m_iPlayer.Stop();
			}
		}
		GSysHSwitch m_pPlayScale:SetDef(500,32,200,18,0.001,3,m_iPlayer,"m_fTimerScale",0);
		GSysImgBtn m_pExportBtn:SetDefText(740,30,"Export")
		{
			void OnClick()
			{
				string pathname;
				pathname=GSysInputBox::Input("Enter Export path","Export:","e:/vexp/v%07d.jpg");
				if (pathname.GetLength()>1) {
					m_iPlayer.ExportAll(pathname);
				}
			}
		}
		void OnSetSize(int w,int h)
		{
			SetPos(0,h-60);
			SetSize(w,60);
			m_Prog.SetSize(w-40,12);
		}
		void OnTimer()
		{
			m_nShow=1;
			int x,y;
			GetMouseInObjPos(x,y);
			m_nShow=IsPointOn(x,y);
		}
		SetTimer(20,"OnTimer");
	};
	VideoCtrls m_pCtrl;
	void OnSizeChgNoti(obj p,int w,int h)
	{
		SetSize(w,h);
		m_player.SetSize(w,h);
		m_pCtrl.OnSetSize(w,h);
	}
	void OnCreate()
	{
		pid.RegSizeMsg(this);
	}
	void Open(string fullname)
	{
		m_player.LoadFile(fullname);
		m_player.Play();
	}
}
obj m_pViewWnd;
void OnOpenFile(string fullname,string extname)
{
	if (m_pViewWnd.isobj()) m_pViewWnd.DelThis();
	switch(extname) {
	case "fw3":
	case "c3d":
	case "cmz":
	case "gmesh":
		m_pViewWnd=new ViewModel;
		m_pViewWnd.Open(fullname);
		break;
	case "gvideo":
		m_pViewWnd=new ViewVideo;
		m_pViewWnd.Open(fullname);
		break;
	case "zmap":
		m_pViewWnd=new ViewZmap;
		m_pViewWnd.Open(fullname);
		break;
	default:
		GMsgBox(this,"Unkown file","Err");
		return;
	}
	DragAcceptFiles(1);
	m_nCanMouse=FINDMOUSE_MK_DROPFILE;
}
void OnDropFiles(var v)
{
	string name;
	name=v[0];
	OnOpenFile(name,file::GetFileExtName(name));
}

```

[EDIT]
I just created a new character (a class not used by my other characters) and spend few minutes leveling it, the netpak.gpak file size, last modify date and MD5 haven't changed from the ones it had before that (my file is 506 052 608 bytes long and MP5: 590bc13c628443bb5b19abc58d0563c9).
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-17T17:18:05+00:00
- Post Title: Chrono Tales: gpak files

i mean delete your entire game content re install game and create a new char
it wont change size.
also i have the game and do not see that text.
mabee 1 or 2 files are not encrypted not sure but most everything is.
## Post #7
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-18T18:08:06+00:00
- Post Title: Chrono Tales: gpak files

The size might stay the same but the MD5 will change.
As previously stated the file is inside lm.gbox you can extract it or download it from: [http://www.filedropper.com/system](http://www.filedropper.com/system) (SYSTEM is it's name in the lm.gbox executable).
I think we should first find the archive structure and then try to find how to decrypt it's contents. The unencrypted file I found should make that easier.

P.S. If you can't get the file and are not wiling to risk with the one I provided I can explain how I did it.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-18T18:53:45+00:00
- Post Title: Chrono Tales: gpak files

the file structure is super easy you can see the file sizes clearly then the data is just encrypted.
I am not going to spend time looking for a browser mmo encryption routine.
if someone else wants to help they can no problem you might just want to try generic directx / opengl rippers and see if anyone of them work with the mmo they would get you textures and models.
also that file lm.gbox is an exe not an archive.
the files look like they might be xored.
I see a sentence like pattern containing something like rush of hedgehog
## Post #9
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-02-24T19:47:09+00:00
- Post Title: Chrono Tales: gpak files

Nothing really complicated,
here a tool to extract the gpak files: [http://www.mediafire.com/download.php?bmu9wdj2obpsjy3](http://www.mediafire.com/download.php?bmu9wdj2obpsjy3)
you will need .NET Framework 4.0 or 4.5, and your OS should support Unicode, many files have chinese letters.

Please post any error.

here some info:

```
//--- 010 Editor v4.0.2 Binary Template
//
// File: Chrono Tales *.gpak
// Author:
// Revision:
// Purpose:
//--------------------------------------
local int Const1 = 8, Const2 = 64, maxdir = 536, pageSize = 1 << 12;

struct{
    char sig[4]; // KAPG
    int ofsData; // always 0x54
    int szUnk1; // always 0x64
    int empty;
    
    int datacounter; // default = 1000 // it counts data changes
    int filesnum; // default = 0
    time_t timestamp;
    int filebufsize;
    int headpagenum; // = (maxdir * filebufsize + 4179) / pageSize
    int unk2; // default = 0
    int maxpageno; // = gpak size >> 12
    int unk3; // default = 0
    int unk4; // default = 0

    FSeek(ofsData);
    struct FILE_NAME FileTable[filesnum]<optimize=false>;

    //FSeek(422<<12);
    //struct PAGE_HEADER page1;
}Header;

struct FILE_NAME{ // size = maxdir
    uint hash;
    time_t timestamp;
    uint unk2;
    uint unk3;
    uint Size;
    uint startPage;
    ushort ident<format=hex>; // always 0xFA21 -> encrypted string
    ushort key1<format=hex>;
    ushort length<format=hex>; // xor with 0x96AC
    ushort key2<format=hex>;
	ubyte enc_name[504]; // encrypted unicode string
	
    // init key = (ushort)(key1 + (ushort)Header.timestamp)
    //Printf("len: %d\n",length^0x96AC);
};

struct PAGE_HEADER{
    uint type<format=hex>; // always 0xADAE
    int prevPage;
    int nextPage;
    int empty;
    int pageID;
    uint decryptkey<format=hex>;
    uint checksum<format=hex>;
    int szData; // if < 4060 = last page
    byte bData[4060]; // encrypted
    int unk1;

    if(nextPage) struct PAGE_HEADER nextPage;
};
```


Decrypting the path:

```
		{
			ushort temp_key1, temp_key2, temp_key3;
			byte[] temp_buf = new byte[2];

			if (this.Type == 0xFA21)
			{
				this.Length = (short)(this.ELength ^ (ushort)0x96AC);
				if (this.Length <= 253)
				{
					temp_key2 = (ushort)((ushort)(TimeStamp & 0xFFFF) +  BitConverter.ToUInt16(this.EBuffer, 26));
					temp_key3 = temp_key2;

					if (this.Length > 0)
					{
						this.Buffer = new byte[this.Length*2];

						for (int i = 0; i < this.Length; i++)
						{
							temp_key1 = BitConverter.ToUInt16(this.EBuffer, 30 + (i*2));
							temp_key3 = (ushort)(0x34401 * temp_key2 + 0x269EC3);
							temp_buf = BitConverter.GetBytes((ushort)((0x4401 * temp_key2 - 0x613D) ^ temp_key1));

							this.Buffer[(i * 2)] = temp_buf[0];
							this.Buffer[(i * 2) + 1] = temp_buf[1];

							temp_key2 = temp_key3;
						}
						this.Name = Encoding.Unicode.GetString(this.Buffer);
					}
				}
			}
		}
```


Decrypting a file page fragment:

```
		{
			byte[] result = new byte[this.Size];

			uint key = this.DecryptKey;

			for (int i = 0; i < this.Size; i++)
			{
				key <<= 1;
				key &= 0xE7BD2160;
				key++;

				result[i] = (byte)(this.Data[i] ^ (key & 0xFF));
			}

			return result;
		}
```
## Post #10
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-25T22:16:56+00:00
- Post Title: Chrono Tales: gpak files

Thanks Falo, any chance you can explain/point me to a tutorial explaining how you found the encryption algorithm?

P.S. I've got an error while extracting the netpak.gpak file, also do you intend to add support for the SYSTEM object found in the lm.gbox executable with the KAPF file header (probably the unencrypted version of the KAPG ones) in the tool?



error on file name ID:05433 05433.PNG (48.4 KiB) Viewed 90 times
## Post #11
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-02-26T00:50:25+00:00
- Post Title: Chrono Tales: gpak files

> Reply from PCto
>
> Thanks Falo, any chance you can explain/point me to a tutorial explaining how you found the encryption algorithm?

P.S. I've got an error while extracting the netpak.gpak file, also do you intend to add support for the SYSTEM object found in the lm.gbox executable with the KAPF file header (probably the unencrypted version of the KAPG ones) in the tool?

You don't have chinese support in your OS, this is how it should look like:
[](http://www.imagebanana.com/view/sijmdyma/gpak_unicode.jpg)

The error is simple, my tool doesn't check the filename or path, so if some unsupported letter is inside it will fail and show an error, what's the full filename ?

The Encryption algo is easy to find with ida pro, there are some debug messages inside of gbox3dmain.dll/lm.gbox, example:
"GCacheFile::_WriteData name too long!" the function which triggers that message is at ".text:10017D0E"
so sub_100172E0 = GCacheFile::_WriteData, that function writes data, than it's easy to find the rest:
sub_10016810 = DecryptPath, 
sub_100168B0 = EncryptPath, 
sub_10016970 = EncryptPage,
sub_100169F0 = DecryptPage
## Post #12
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-26T20:30:28+00:00
- Post Title: Chrono Tales: gpak files

Running the tool on Unicode OS and a new file (deleted the previous one and let it download a fresh copy) doesn't help: 


05448.png (95.6 KiB) Viewed 82 times



P.S. Would IDA Pro v5.0 (the one that's currently free) or the demo version do the job or do I have to buy the full version?
## Post #13
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-02-27T17:38:19+00:00
- Post Title: Chrono Tales: gpak files

Here is the template for the SYSTEM object found in the lm.gbox executable with the KAPF file header:

```
//--- 010 Editor Binary Template
// File: Chrono Tales FPAK
// Author: PCto
//--------------------------------------
struct HEADER {
     char sig[4]; // KAPF
     int szUnk1;
     int szUnk2;
     int szEntryes;
     int empty1;
     int empty2;
     int szUnk3;
     int szUnk4;
     int szUnk5;
     int szUnk6;
     int szUnk7;
     int szUnk8;
     int szUnk9;
     int empty3;

struct Entry {
     int szUnk; // always 0x90
     char filename[128]; // NULL terminated up to 128 symbols
     int szSize;
     time_t timestamp;
     int szOfset;
} entries[szEntryes]<optimize=false>;

} header <bgcolor=cLtGray>;
```

P.S. If any one can improve it or if Falo decide to implement support for it in his tool.
## Post #14
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2013-03-01T16:52:43+00:00
- Post Title: Chrono Tales: gpak files

```

idstring "KAPF"
get Unk1 long           // 0x38
get Unk2 long           // 0x01
get Entryes long        // Number of files contained
get empty1 long
get empty2 long
get Unk3 long
get Unk4 long
get Unk5 long
get Unk6 long
get szUnk7 long
get szUnk8 long
get szUnk9 long
get empty3 long

for i = 0 < Entryes
    get DUMMY long      // 0x90
    GetDString PATH 128 // 128 characters for Path and/or filename
    get Size long       // Size of file
    get TMstamp time    // TimeStamp
    get OFSET long      // File Start Ofset
    
    Log PATH OFSET Size // Save File
next i
```
