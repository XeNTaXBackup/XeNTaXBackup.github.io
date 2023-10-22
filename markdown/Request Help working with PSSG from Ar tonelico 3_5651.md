## Post #1
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2010-12-28T11:57:33+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

Hi there,

Recently I started playing with the data on the [Ar tonelico 3](http://en.wikipedia.org/wiki/Ar_tonelico_Qoga:_Knell_of_Ar_Ciel) PS3 disk.

Interestingly most of the files there aren't archived, so it's easy to browse to folders containing the images, sounds, etc.

I've had success working with some of the files (DDS images, AFS audio), but some are still a mystery.

- SFD movies, seem to be in version 2 of the Sofdec video format (which plays back very blocky and incorrect colors at the moment), but hopefully some tools will be released at some point that can support it (ffmpeg also has an open bug for Sofdec v2 support, I hope they can figure it out). I'm going to keep an eye on that. But does anyone have any more info about the progress with SFD v2?

- 3D models, which is the main point of this post. They all seem to have a PSSG file extension, eg:

BOSS00.PSSG.gz

(decompresses fine with gunzip, to BOSS00.PSSG).

I searched for some tools, and found "PSSG utility" (for extracting and repacking DDS files), and also 3dsimed (used the latest version, from their website).

Neither of them seem to be able to open the file. I think that those tools are geared more towards the PSSG files found in some car games, rather than being general-purpose PSSG-extracting tools.

I also checked for the DDS magic number "DDS " in the PSSG file, but it's not there (though there are the file names of some .dds files in plain text in the PSSG file). There's also a bunch of other english text in there that seem to be related to 3D rendering

Here is a 7zipped version of BOSS00.PSSG from the At3 game files. Could someone take a look at the file, and let me know if it's possible to work with this file in some way? (ie: extract textures or 3D models).

[http://wizzardx.isisview.org/uploads2/a ... 00.PSSG.7z](http://wizzardx.isisview.org/uploads2/at3/BOSS00.PSSG.7z)

Thanks.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-28T12:35:42+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

PSSG is a common ps3 resource file, I'm surprised there isnt more support for the format. cause it's seen on a few games....

as for getting models, each section of data is described in english. its just a matter of someone actually doing it.. cause as far as figuring out where all the data is concerned, its already detailed within the file.

EDIT

I notice it says float3.. I think thats a 24bit float O-o.. never seen one of those before

```
 * ---------------------------------------------------------------------------------------------------- 
 * ----- 習作的なバーテックスシェーダ ----- 
 * ---------------------------------------------------------------------------------------------------- 
 */
/* ----- バーテックスシェーダ入力情報 ----- */
struct    ExampleVertexIn
{
    float3    Vertex        : POSITION;        /* ----- 頂点の位置 ----- */
    float3    Normal        : NORMAL0;        /* ----- 頂点の法線 ----- */
    float2    TexCoord    : TEXCOORD0;    /* ----- 頂点のテクスチャ座標 ----- */
    float4    Color        : COLOR;        /* ----- 頂点のカラー ----- */
};    /* ----- ExampleVertexIn ----- */


/* ----- バーテックスシェーダ出力情報 ----- */
struct    ExampleVertexOut
{
    float4    HPosition        : POSITION;        /* ----- スクリーン座標に変換された頂点の位置(->ＧＰＵへ) ----- */
    float4    Color            : COLOR;        /* ----- 頂点のカラー ----- */
    float4    TexCoord        : TEXCOORD0;    /* ----- 頂点のテクスチャ座標 ----- */
    float4    Normal            : TEXCOORD1;    /* ----- カメラ空間にマッピングされた頂点の法線 ----- */
    float4    Position        : TEXCOORD2;    /* ----- カメラ空間にマッピングされた頂点の位置 ----- */
};    /* ----- ExampleVertexOut ----- */

float4x4    modelviewproj : WorldViewProjection < string UIWidget="None"; >;
float4x4    modelview : WorldView < string UIWidget="None"; >;
float4x4    model : World < string UIWidget="None"; >;
float4x4    lightviewproj < string UIWidget="None"; > ;

/* ----- ＵＶスクロール値 ----- */
float2    scrollTexCoord <
 string UIName   = "uv scroll";
 float2 UIMin = float2( 0.0, 0.0);
 float2 UIMax = float2( 1000.0, 1000.0);
> = { 0.0, 0.0 };    /* ----- { u0, v0 } ----- */

/* ----- シャドウ深度バイアス ----- */
float    shadowDepthBias < string UIWidget = "None"; > = 0.0005;

ExampleVertexOut
ExampleVp(
    /* -----入力情報 ----- */
    const    ExampleVertexIn    vin
)
{
    ExampleVertexOut    vout;

    /* ----- スクリーン座標へ変換 ----- */
    vout.HPosition    = mul( modelviewproj, float4( vin.Vertex, 1.f));
    /* ----- 頂点と法線をカメラ空間にマッピング ----- */
    vout.Position    = mul( modelview, float4( vin.Vertex, 1.f));
    vout.Normal        = mul( modelview, float4( vin.Normal, 0.f));
    /* ----- 頂点位置のｗ成分に距離を保存 ----- */
    vout.Position.w    = length( vout.Position.xyz);
    /* ----- テクスチャ座標と頂点カラー ----- */
    vout.TexCoord    = float4( vin.TexCoord + scrollTexCoord, 0.f, 0.f);
    vout.Color        = vin.Color * diffuse;
    /* ----- フェアリーシェードパワーの計算 ----- */
    vout.Normal.w    = max( 0.0, dot( normalize( -vout.Position.xyz), lightDirectionCS.xyz));

    /* ----- フラグメントプログラムに送る ----- */
    return    vout;
}    /* ----- ExampleVp ----- */


```
## Post #3
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-30T23:44:29+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

> Reply from mariokart64n
>
> I notice it says float3.. I think thats a 24bit float O-o.. never seen one of those before
Actually float3 is just 3 normal floats. IE: x,y,z.
## Post #4
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2010-12-31T12:19:18+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

Thanks for the replies   

I mainly wanted to confirm that there weren't some obvious tools I was missing that could work with these files.

Hopefully at some point more tools will come out with better support for the PS3 file formats, since it's only fairly recently that PS3 game modding became practical.

I'm tempted to poke around with the files myself, but I know next to nothing about 3D model formats, or what things like "vector in" and "vector out" are   

I might also try getting hold of the developers of those tools I tried before, and see what they have to say about the At3 model files.
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-31T15:04:02+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

I was looking at these for a bit, studying the patterns of data. but got discouraged, cause they start invoking compression inside the files on certain sectors of data.. so hell knows if you'll be able to decompress the data inside
## Post #6
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2010-12-31T15:54:42+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

> Reply from mariokart64n
>
> I was looking at these for a bit, studying the patterns of data. but got discouraged, cause they start invoking compression inside the files on certain sectors of data.. so hell knows if you'll be able to decompress the data inside

Thanks for trying   
The compression seems redundant, since the files are already gzipped on the PS3 disc  

How did you determine that some parts are compressed?

Not sure if it helps, but in theory there should be DDS images in the compressed data, with a "DDS " magic number at the start of the image data (after decompressing).

Also, it might help to compare against some PSSG files, which the racing game tools are able to work with (possibly some of them use the same compression, or at least a similar structure - I've also seen some other Xentax forum threads which deal with them).
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-31T16:07:00+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

no the file is all commented with text, and when I said it invoked compression, I meant just that. in the file some sections say <compressed package./> then a bunch of compressed data. 

your right it is redundant, but they do it alot like all the time. although DDS is considered compressed, its not. its a lossy format, so what happens is detail is removed during an encoding process. try and think of it as jpeg vs bmp.. jpegs compressed.. but not in the same idea as zip or something

and it makes sense that they can invoke compression like that being thats the purpose of the PSSG format.
## Post #8
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2010-12-31T17:23:01+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

In case others are interested, I found some information about lossy DDS image compression over here:
[http://www.ogre3d.org/forums/viewtopic. ... 45&start=0](http://www.ogre3d.org/forums/viewtopic.php?f=5&t=55245&start=0)

Could you tell me what editor you're using, and what text encoding setting? 
I'm having a few problems on my side:

- Can't find the string "compressed" in the data
- Don't have those Japanese characters (in your first post's text)
- I have mostly random ascii gibberish on my side (with the English text mixed in), rather than tidily-formatted plain text (like you posted earlier, and what you seem to be describing).

(I'm new to this: Have barely touched a hex editor before, and rarely deal with unusual text encodings).

I won't be able to do anything interesting analysis-wise, but I'm interested in viewing the plain text more clearly.

Thanks.
## Post #9
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2010-12-31T21:40:35+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

Sorry for the double post, but some interesting news:

I was in contact with Pavcules, who developed one of the PSSG tools (the first on listed on [this](http://ego-engine.wikispaces.com/PSSG_Utilities) page). And while he's no longer involved in the game modding scene, he did give me a copy of his code, and permission to use it freely.

So, I'm going to post the PSSG utility source code over here, in the hope that it will be useful to others:

[http://wizzardx.isisview.org/uploads/mi ... e_Code.rar](http://wizzardx.isisview.org/uploads/misc/pssg_tools/pavcules/PSSG_Utility_Soruce_Code.rar)

And here are some sample PSSG files that work with the tool:

[http://wizzardx.isisview.org/uploads/mi ... g_file.rar](http://wizzardx.isisview.org/uploads/misc/pssg_tools/pavcules/grid_pssg_file.rar)
[http://wizzardx.isisview.org/uploads/mi ... event.pssg](http://wizzardx.isisview.org/uploads/misc/pssg_tools/pavcules/sponsor_event.pssg)

The project source code is in VB.NET 2008, and the file format (for finding and replacing DDS images) was figured out by some reverse engineering (apparently the algorithm is a bit rough, and it has some trouble with larger images).

I haven't tried building the code yet myself (it's been many years since I worked with VB or Windows development in general). But I did check the PSSG files, and they do look very similar in structure to the At3 file that I uploaded, which is good news.

If someone who knows a bit of VB.NET has some free time, could you perhaps try experimenting with the code, and seeing if it can be made to work with the PSSG file that I uploaded before?

Or failing that, perhaps at least some logic in the tool can be adapted for one of the multi extractor tools, for the PC racing games that it currently supports.
## Post #10
- Username: Ryder25
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 01, 2011 6:43 am
- Post datetime: 2010-12-31T23:37:48+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-01-01T00:30:57+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

guessing he did not release any PSSG tools publicly for model viewing?

guess its only a matter of time until that happens, if wizardx really posted the format specs for the format.

EDIT
chrrox was asking me where I saw compressed data, so just to show I'm not crazy here's the PSSG that has the compressed sectors in it.

at offset 0x3455
str=compressedStreamK

EDIT2
ok found that tool, but it doesnt work on character files just a few weaps
[http://www.sim-garage.co.uk/tools_version_history.htm](http://www.sim-garage.co.uk/tools_version_history.htm)
[Model01.zip](https://xentaxbackup.github.io/file/3747_Model01.zip)
## Post #12
- Username: wizzardx
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jun 14, 2009 8:34 pm
- Post datetime: 2011-01-01T15:09:36+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

Thanks Ryder, the updated tool works for me   .
Hopefully it will also work for many other PS3 game, though other people will need to confirm this.

(The main extra feature that I'd find really useful, is a way to mass-extract DDS files, eg a command-line option on the tool, for batch processing).

mariokart64n, I don't think that Pavcules worked on a project for 3D model viewing, and at this time the main person who has a PSSG 3D viewer is the 3DSimEd guy. I left a message on his board, with some luck he may take a look at viewing the models sometime.
## Post #13
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-04-07T16:53:12+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

hi, all

I want get Totori model for use garrymod or someting

but sadly, Ryder25's tool doesnt work  at Totori no atelier

3DSimED212 can extract dds but doest make obj.

Anybody interested in Atelier series?



FreeImageNET, Version=3.13.1.1, Culture=neutral, PublicKeyToken=null' 
: 'FreeImageNET, Version=3.13.1.1, Culture=neutral, PublicKeyToken=null'
   위치: PSSGParameters.Form1.createPreview()
   위치: PSSGParameters.Form1.editButton_Click(Object sender, EventArgs e)
   위치: PSSGParameters.Form1.textureTreeView_AfterSelect(Object sender, TreeViewEventArgs e)
   위치: System.Windows.Forms.TreeView.OnAfterSelect(TreeViewEventArgs e)
   위치: System.Windows.Forms.TreeView.TvnSelected(NMTREEVIEW* nmtv)
   위치: System.Windows.Forms.TreeView.WmNotify(Message& m)
   위치: System.Windows.Forms.TreeView.WndProc(Message& m)
   위치: System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   위치: System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   위치: System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
## Post #14
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-04-28T00:57:50+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-14T00:49:59+00:00
- Post Title: Request: Help working with PSSG from Ar tonelico 3

PSSG is serialized collada format.
It is the official format of the ps3 PhyreEngine(TM).
the PhyreEngine sdk contains tools to convert collada to pssg but not the other way around.
I have gotten textures extracting in max and should have models shortly.
but if you are a ps3 developer and have the tools you can export any model and animation to any game using this engine.
a few of the games that use the format are listed here
[http://en.wikipedia.org/wiki/PhyreEngine](http://en.wikipedia.org/wiki/PhyreEngine)
## Post #16
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-14T02:17:19+00:00
- Post Title: Re: Request: Help working with PSSG from Ar tonelico 3

> Reply from chrrox
>
> PSSG is serialized collada format.
It is the official format of the ps3 PhyreEngine(TM).
the PhyreEngine sdk contains tools to convert collada to pssg but not the other way around.
I have gotten textures extracting in max and should have models shortly.
but if you are a ps3 developer and have the tools you can export any model and animation to any game using this engine.
a few of the games that use the format are listed here
http://en.wikipedia.org/wiki/PhyreEngine

That's awesome news. Thank you very much for your awesome work chrrox.
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-16T02:57:27+00:00
- Post Title: Re: Request: Help working with PSSG from Ar tonelico 3

Ill post the script soon its getting late.
[model01.png](https://xentaxbackup.github.io/file/4336_model01.png)
## Post #18
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-16T03:13:36+00:00
- Post Title: Re: Request: Help working with PSSG from Ar tonelico 3

> Reply from chrrox
>
> Ill post the script soon its getting late.
 you did it again. Thank you very much =)
