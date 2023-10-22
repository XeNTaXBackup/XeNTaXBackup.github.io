## Post #1
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-08-16T23:50:51+00:00
- Post Title: 终末阵线：伊诺贝塔/Quantum Maki (Android/PC) - encrypted/compressed files

The game's files uses some kind of encrypted/compressed format and this prevents from AssetStudio loading these files up.
[Download here.](https://cdn.discordapp.com/attachments/493153303551541258/1009242874552000553/0af78bec0f2e3977.ab)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-08-17T02:35:53+00:00
- Post Title: 终末阵线：伊诺贝塔/Quantum Maki (Android/PC) - encrypted/compressed files

This is the method I call bilibili encrypt.
From the part 0x20 is XORed with 0xA6, and from there 0x1000 bytes are encrypted, probably with AES or some other method.
This encryption is probably done using some kind of packaging system, and games that use this encryption are 100% likely to be obfuscated, making them impossible to analyze using normal means.
## Post #3
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-09-07T01:48:35+00:00
- Post Title: 终末阵线：伊诺贝塔/Quantum Maki (Android/PC) - encrypted/compressed files

> Reply from einherjar007 ↑Wed Aug 17, 2022 10:35 am at Wed Aug 17, 2022 10:35 am
>
> 
From the part 0x20 is XORed with 0xA6, and from there 0x1000 bytes are encrypted, probably with AES or some other method.

I've found refences to AES encryption in its global-metadata.dat file.

I've tried to decrypt the libil2cpp.so file with the latest version of Auto-Il2cppDumper which it sadly results with the game crashing in a few seconds without giving me dump.cs whatso ever.

Here is a download link containing multiple .so files and a global-metadata.dat file all taken from the latest version of the apk.
[https://www.mediafire.com/file/qxmo0on2 ... s.zip/file](https://www.mediafire.com/file/qxmo0on2xegopaf/Quantum_Maki_CN_files.zip/file)

EDIT:
Looks like I found what it appears to be a AES key from livNetHTProtect.so (the one highlighted in yellow), I don't think that this goes with the encrypted/compressed files.
## Post #4
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-09-16T17:15:30+00:00
- Post Title: 终末阵线：伊诺贝塔/Quantum Maki (Android/PC) - encrypted/compressed files

I got to dump the Japanese PC version of Quantum Maki with Il2CppDumper without any issues whatso ever, here is a download link to these successfully dumped files.
[Dumped files](https://www.mediafire.com/file/weu9kxf8kpku2jq/Quantum_Maki_Japanese_PC_version_dump.zip/file)
I also provided download link to a .ab file which it is also taken from the same version of the game as the dumped files,
[.ab file](https://www.mediafire.com/file/5x2e4722hk2gwe2/9b752c2270151bd0.ab/file)
## Post #5
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-09-20T16:53:49+00:00
- Post Title: 终末阵线：伊诺贝塔/Quantum Maki (Android/PC) - encrypted/compressed files

Seems like they left out a build_log.txt in the pc version and revealed stuff about the file decompression and keys in this game.
Here is a part of the build_log.txt file:

```
Default Shader: DefaultShaders, Assembly-CSharp-firstpass, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null

<1> 2022-09-08 00:02:29 
ApplicationStreamingAssetsLoader.Config.Load: 'EditorPrefs'
Item _Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 179)
JSONObject Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 44)
JSONObject ReadGlobalConfigValue(System.String, System.String, System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\Common\EditorUtils.cs: 3384)
Int32 ProjectEditorPrefs_GetInt(System.String, Int32)(at H:\Jp_20220709_110\Client\Assets\Editor\Common\EditorUtils.cs: 3528)
Boolean get_enabled()(at H:\Jp_20220709_110\Client\Assets\Editor\Common\UnityAssetDependenceCache.cs: 27)
Void InitHooks()(at H:\Jp_20220709_110\Client\Assets\Editor\Common\UnityAssetDependenceCache.cs: 250)
Void .cctor()(at H:\Jp_20220709_110\Client\Assets\Editor\Common\UnityAssetDependenceCache.cs: 206)
Void RunClassConstructor(IntPtr)(at : 0)
Void RunClassConstructor(System.RuntimeTypeHandle)(at : 0)
Void ProcessInitializeOnLoadAttributes(System.Type[])(at : 0)


<2> 2022-09-08 00:02:29 
Locale.Initialize
	Locale[.cctor] : (1359)
	H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs


<3> 2022-09-08 00:02:29 
ApplicationStreamingAssetsLoader.Config.Load: 'Locale'
Item _Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 179)
JSONObject get_locale()(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 39)
Boolean ReadLocaleInfoFromCfg(System.String ByRef, System.String ByRef, System.String ByRef)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1515)
Void ReadLocaleInfo(Localization.LocaleInfo ByRef)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1543)
Void Initialize(System.String, System.String, Int32)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1386)
Void .cctor()(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1359)
System.String ModifiedKey(System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 151)
System.String ModifiedKey(System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 321)
Boolean HasKey(System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 231)
Void InitGraphicSetting()(at H:\Jp_20220709_110\Client\Assets\Plugins\Scripts\Graphic\Editor\CuteGraphicEditor.cs: 173)
Void .cctor()(at H:\Jp_20220709_110\Client\Assets\Plugins\Scripts\Graphic\Editor\CuteGraphicEditor.cs: 33)
Void RunClassConstructor(IntPtr)(at : 0)
Void RunClassConstructor(System.RuntimeTypeHandle)(at : 0)
Void ProcessInitializeOnLoadAttributes(System.Type[])(at : 0)


<4> 2022-09-08 00:02:34 
FindType( "UWA.UWATarget", "UWAEditor" ) failed!

<5> 2022-09-08 00:02:34 
LuaTasker.Initialize, IntPtr size: 8

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<6> 2022-09-08 00:02:34 
lua_State: 0x2797440149832

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<7> 2022-09-08 00:02:34 
LuaTasker.OpenLibs

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<8> 2022-09-08 00:02:34 
LuaThread.OpenLib

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<9> 2022-09-08 00:02:34 
RegisterGlobalApi

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<10> 2022-09-08 00:02:34 


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<11> 2022-09-08 00:02:34 
LuaStartup end, stack size = 0

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<12> 2022-09-08 00:02:35 
ApplicationStreamingAssetsLoader.Config.Load: 'Global'
Item _Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 179)
JSONObject get_global()(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 33)
JSONObject ReadGlobalConfigValue(System.String, System.String, System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\Common\EditorUtils.cs: 3384)
Void OnEditorGUI()(at H:\Jp_20220709_110\Client\Assets\Editor\Buildbot\AppBuildbot.cs: 1280)
Void OnGUI()(at H:\Jp_20220709_110\Client\Assets\Editor\Buildbot\AppBuildbot.cs: 2608)
System.Object InternalInvoke(System.Object, System.Object[], System.Exception ByRef)(at : 0)
System.Object Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)(at : 0)
System.Object Invoke(System.Object, System.Object[])(at : 0)
Void Invoke(System.String, System.Object)(at : 0)
Void Invoke(System.String)(at : 0)
Void InvokeOnGUI(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void DrawView(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void OldOnGUI()(at : 0)
Void DoOnGUI(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, Boolean, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Boolean HandleIMGUIEvent(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Void DoIMGUIRepaint()(at : 0)
Void ExecuteNonDrawMesh(UnityEngine.UIElements.UIR.DrawParams, Boolean, Single, System.Exception ByRef)(at : 0)
Void EvaluateChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void DrawChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void Render(UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags)(at : 0)
Void DrawChain(UnityEngine.Rect, UnityEngine.Matrix4x4)(at : 0)
Void Update()(at : 0)
Void UpdateVisualTreePhase(UnityEngine.UIElements.VisualTreeUpdatePhase)(at : 0)
Void UpdateForRepaint()(at : 0)
Void Repaint(UnityEngine.Event)(at : 0)
Boolean DoDispatch(UnityEngine.UIElements.BaseVisualElementPanel)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<13> 2022-09-08 00:02:35 
LocalVersion.LoadFile: H:/Jp_20220709_110/Client/Assets/StreamingAssets/LocalVersion.xml

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<14> 2022-09-08 00:02:35 
LocalVersion.LoadFile: H:/Jp_20220709_110/Client/Assets/StreamingAssets/LocalVersion.xml

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<15> 2022-09-08 00:02:44 
SetWaitTimeoutHandler: System.Func`2[System.Threading.WaitHandle,System.Boolean]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<16> 2022-09-08 00:02:44 
OSMessageBox Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<17> 2022-09-08 00:02:44 
ABM: GetNativeRequireDiskSpaceCallback

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<18> 2022-09-08 00:02:44 
DiskSpaceRequireHandler Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<19> 2022-09-08 00:02:44 
Obtain the system encoding.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<20> 2022-09-08 00:02:44 
DiskSpaceRequireHandler Setup OK.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<21> 2022-09-08 00:02:44 
RegisterRequireDiskSpaceHook usage:12 System.Func`3[System.Int32,System.IntPtr,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<22> 2022-09-08 00:02:44 
NULL NativeSigHandler Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<23> 2022-09-08 00:02:44 
AssetBundleUtil.Setup, Has C bundle decoder : true

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<24> 2022-09-08 00:02:44 
ABM: SetNativeBundleDecompressor: System.Func_ByRef`7[System.String,System.String,System.Int32,System.Int32,System.IntPtr,System.IntPtr,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<25> 2022-09-08 00:02:44 
ABM: SetNativeBundleOffsetParser: System.Func_ByRef`3[System.String,System.Int32,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<26> 2022-09-08 00:02:44 
ABM: SetupNativeBundleDecompressMask: System.Func`2[System.Int32,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<27> 2022-09-08 00:02:44 
ABM: SetNativeBundleDecompressMask: 2 -> 2

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<28> 2022-09-08 00:02:44 
TestArrayHacker: ArraySize_t size = 4, Succeeded = True

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<29> 2022-09-08 00:02:44 
DiskFreeSpace : 6.99 GB

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<30> 2022-09-08 00:02:44 
Launcher.Glue

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<31> 2022-09-08 00:02:44 
FGDKit.Core.NativeAPI.Setup

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<32> 2022-09-08 00:02:44 
NativeCommon Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<33> 2022-09-08 00:02:44 
SystemInfo:
batteryLevel = -1
batteryStatus = Charging
operatingSystem = Windows 10  (10.0.19043) 64bit
operatingSystemFamily = Windows
processorType = Intel(R) Core(TM) i7-10700F CPU @ 2.90GHz
processorFrequency = 2904
processorCount = 16
systemMemorySize = 32668
deviceUniqueIdentifier = d1f2679582463e40dd36f630098d58324abb571f
deviceName = DESKTOP-CUB1PTK
deviceModel = System Product Name (ASUS)
supportsAccelerometer = False
supportsGyroscope = False
supportsLocationService = False
supportsVibration = False
supportsAudio = False
deviceType = Desktop
graphicsMemorySize = 5980
graphicsDeviceName = NVIDIA GeForce RTX 2060
graphicsDeviceVendor = NVIDIA
graphicsDeviceID = 7944
graphicsDeviceVendorID = 4318
graphicsDeviceType = Direct3D11
graphicsUVStartsAtTop = True
graphicsDeviceVersion = Direct3D 11.0 [level 11.1]
graphicsShaderLevel = 50
graphicsMultiThreaded = True
renderingThreadingMode = MultiThreaded
hasHiddenSurfaceRemovalOnGPU = False
hasDynamicUniformArrayIndexingInFragmentShaders = True
supportsShadows = True
supportsRawShadowDepthSampling = True
supportsMotionVectors = False
supports3DTextures = True
supports2DArrayTextures = True
supports3DRenderTextures = True
supportsCubemapArrayTextures = True
copyTextureSupport = Basic, Copy3D, DifferentTypes, TextureToRT, RTToTexture
supportsComputeShaders = True
supportsGeometryShaders = True
supportsTessellationShaders = True
supportsInstancing = True
supportsHardwareQuadTopology = False
supports32bitsIndexBuffer = True
supportsSparseTextures = True
supportedRenderTargetCount = 8
supportsSeparatedRenderTargetsBlend = True
supportedRandomWriteTargetCount = 8
supportsMultisampledTextures = 1
supportsMultisampleAutoResolve = False
supportsTextureWrapMirrorOnce = 1
usesReversedZBuffer = True
npotSupport = Full
maxTextureSize = 16384
maxCubemapSize = 16384
maxRenderTextureSize = 16384
maxComputeBufferInputsVertex = 128
maxComputeBufferInputsFragment = 128
maxComputeBufferInputsGeometry = 128
maxComputeBufferInputsDomain = 128
maxComputeBufferInputsHull = 128
maxComputeBufferInputsCompute = 32
maxComputeWorkGroupSize = 1024
maxComputeWorkGroupSizeX = 1024
maxComputeWorkGroupSizeY = 1024
maxComputeWorkGroupSizeZ = 64
supportsAsyncCompute = False
supportsGraphicsFence = True
supportsAsyncGPUReadback = True
supportsRayTracing = False
supportsSetConstantBuffer = True
minConstantBufferOffsetAlignment = False
hasMipMaxLevel = True
supportsMipStreaming = True
usesLoadStoreActions = False
supportsStoreAndResolveAction = True
supportsRenderTextures = True
supportsRenderToCubemap = True
supportsImageEffects = True
supportsStencil = 1
graphicsPixelFillrate = -1
supportsVertexPrograms = True
supportsGPUFence = False


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<34> 2022-09-08 00:02:44 
SupportsRenderTextureFormat:
ARGB32, Depth, ARGBHalf, Shadowmap, RGB565, ARGB4444, ARGB1555, Default, ARGB2101010, DefaultHDR, ARGB64, ARGBFloat, RGFloat, RGHalf, RFloat, RHalf, R8, ARGBInt, RGInt, RInt, BGRA32, RGB111110Float, RG32, RGBAUShort, RG16, BGRA10101010_XR, BGR101010_XR, R16

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<35> 2022-09-08 00:02:44 
SupportsTextureFormat:
Alpha8, ARGB4444, RGB24, RGBA32, ARGB32, RGB565, R16, DXT1, DXT5, RGBA4444, BGRA32, RHalf, RGHalf, RGBAHalf, RFloat, RGFloat, RGBAFloat, YUY2, RGB9e5Float, BC6H, BC7, BC4, BC5, DXT1Crunched, DXT5Crunched, RG16, R8, RG32, RGB48, RGBA64

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<36> 2022-09-08 00:02:44 
QualitySettings:
asyncUploadBufferSize = 4
asyncUploadTimeSlice = 2
anisotropicFiltering = Enable


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<37> 2022-09-08 00:02:44 
ShaderCache.Setup

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<38> 2022-09-08 00:02:44 
LayerUtils.Setup

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<39> 2022-09-08 00:02:44 
Enable GlobalPreUpdateRegister.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<40> 2022-09-08 00:02:44 
Enable GlobalUpdateRegister.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<41> 2022-09-08 00:02:44 
Enable GlobalLateUpdateRegister.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<42> 2022-09-08 00:02:44 
ABM: GetNativeRequireDiskSpaceCallback

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<43> 2022-09-08 00:02:44 
RegisterRequireDiskSpaceHook usage:12 System.Func`3[System.Int32,System.IntPtr,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<44> 2022-09-08 00:02:44 
ABM: SetNativeBundleDecompressor: System.Func_ByRef`7[System.String,System.String,System.Int32,System.Int32,System.IntPtr,System.IntPtr,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<45> 2022-09-08 00:02:44 
ABM: SetNativeBundleOffsetParser: System.Func_ByRef`3[System.String,System.Int32,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<46> 2022-09-08 00:02:44 
ABM: SetupNativeBundleDecompressMask: System.Func`2[System.Int32,System.Int32]

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<47> 2022-09-08 00:02:44 
ABM: SetNativeBundleDecompressMask: 2 -> 2

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<48> 2022-09-08 00:02:44 
TestArrayHacker: ArraySize_t size = 4, Succeeded = True

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<49> 2022-09-08 00:02:44 
DiskFreeSpace : 6.99 GB

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<50> 2022-09-08 00:02:44 
RflxSetValue _ClearBundleCachedFiles = True

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<51> 2022-09-08 00:02:44 
DynamicLayers Dump begin:
[0]: 'LAYER_CUSTOM0', has been used as 'Reflectable', 'LevelflowTriggerOnly'
[1]: 'LAYER_CUSTOM1', has been used as 'Far', 'PhysicsLayer1'
[2]: 'LAYER_CUSTOM2', has been used as 'Reflectable | Far', 'PhysicsLayer2'
[3]: 'LAYER_CUSTOM3', has been used as 'Near', 'PhysicsLayer3'
[4]: 'LAYER_CUSTOM4', has been used as 'Reflectable | Near', 'PhysicsLayer4'
[5]: 'LAYER_CUSTOM5', has been used as 'Far | Near', 'PhysicsLayer5'
[6]: 'LAYER_CUSTOM6', has been used as 'Reflectable | Far | Near', 'PhysicsLayer6'
[7]: 'LAYER_CUSTOM7', has been used as 'PhysicsLayer7'
DynamicLayers Dump end.


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<52> 2022-09-08 00:02:44 
UserLayers Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<53> 2022-09-08 00:02:44 
DynamicTags Dump begin:
[0]: 'TAG_CUSTOM0', has been used as 'A'
[1]: 'TAG_CUSTOM1', has been used as 'B'
[2]: 'TAG_CUSTOM2', has been used as 'C'
[3]: 'TAG_CUSTOM3', has been used as 'D'
[4]: 'TAG_CUSTOM4', has been used as 'E'
[5]: 'TAG_CUSTOM5', has been used as 'F'
[6]: 'TAG_CUSTOM6', has been used as 'G'
[7]: 'TAG_CUSTOM7'
[8]: 'TAG_CUSTOM8'
[9]: 'TAG_CUSTOM9'
[10]: 'TAG_CUSTOM10'
[11]: 'TAG_CUSTOM11'
[12]: 'TAG_CUSTOM12'
[13]: 'TAG_CUSTOM13'
[14]: 'TAG_CUSTOM14'
DynamicTags Dump end.


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<54> 2022-09-08 00:02:44 
UserTags Setup.

sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<55> 2022-09-08 00:02:44 
Locale.Initialize
	Locale[Ensure] : (1371)
	H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<56> 2022-09-08 00:02:44 
ApplicationStreamingAssetsLoader.Config.Load: 'Locale'
Item _Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 179)
JSONObject get_locale()(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 39)
Boolean ReadLocaleInfoFromCfg(System.String ByRef, System.String ByRef, System.String ByRef)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1515)
Void ReadLocaleInfo(Localization.LocaleInfo ByRef)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1543)
Void Initialize(System.String, System.String, Int32)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1386)
Boolean Ensure()(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1371)
Void Refresh()(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1364)
Localization.DistributionRegion GetCurrentRegion(Localization.Language ByRef)(at H:\Jp_20220709_110\Client\Assets\Plugins\Localized\Localization.cs: 1261)
System.String ModifiedKey(System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 151)
System.String ModifiedKey(System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 321)
Boolean GetBool(System.String, Boolean)(at H:\Jp_20220709_110\Client\Assets\Editor\CommonEditor\Data\PlayerPrefsHook.cs: 243)
Boolean GetBool(System.String)(at : 0)
Boolean GetBool(BehaviorDesigner.Editor.BDPreferences)(at : 0)
Void HierarchyWindowItemOnGUI(Int32, UnityEngine.Rect)(at : 0)
Void OnRowGUICallback(Int32, UnityEngine.Rect)(at : 0)
Void DoItemGUI(UnityEditor.IMGUI.Controls.TreeViewItem, Int32, Single, Boolean)(at : 0)
Void IterateVisibleItems(Int32, Int32, Single, Boolean)(at : 0)
Void OnGUI(UnityEngine.Rect, Int32)(at : 0)
Void DoTreeView(Single)(at : 0)
Void OnGUI(UnityEngine.Rect)(at : 0)
Void DoSceneHierarchy()(at : 0)
Void OnGUI()(at : 0)
System.Object InternalInvoke(System.Object, System.Object[], System.Exception ByRef)(at : 0)
System.Object Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)(at : 0)
System.Object Invoke(System.Object, System.Object[])(at : 0)
Void Invoke(System.String, System.Object)(at : 0)
Void Invoke(System.String)(at : 0)
Void InvokeOnGUI(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void DrawView(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void OldOnGUI()(at : 0)
Void DoOnGUI(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, Boolean, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Boolean HandleIMGUIEvent(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Void DoIMGUIRepaint()(at : 0)
Void ExecuteNonDrawMesh(UnityEngine.UIElements.UIR.DrawParams, Boolean, Single, System.Exception ByRef)(at : 0)
Void EvaluateChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void DrawChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void Render(UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags)(at : 0)
Void DrawChain(UnityEngine.Rect, UnityEngine.Matrix4x4)(at : 0)
Void Update()(at : 0)
Void UpdateVisualTreePhase(UnityEngine.UIElements.VisualTreeUpdatePhase)(at : 0)
Void UpdateForRepaint()(at : 0)
Void Repaint(UnityEngine.Event)(at : 0)
Boolean DoDispatch(UnityEngine.UIElements.BaseVisualElementPanel)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)


sign = {
    platform = "WindowsEditor"
    version = "branch-198183"
    location = "卢建, 192.168.40.82"
    uuid = "d1f2679582463e40dd36f630098d58324abb571f"
}


<57> 2022-09-08 00:02:44 
ApplicationStreamingAssetsLoader.Config.Load: 'Global'
Item _Get(System.String)(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 179)
JSONObject get_global()(at H:\Jp_20220709_110\Client\Assets\Plugins\Launcher\Source\ApplicationStreamingAssetsLoader.cs: 33)
JSONObject ReadGlobalConfigValue(System.String, System.String, System.String)(at H:\Jp_20220709_110\Client\Assets\Editor\Common\EditorUtils.cs: 3384)
Void OnEditorGUI()(at H:\Jp_20220709_110\Client\Assets\Editor\Buildbot\AppBuildbot.cs: 1280)
Void OnGUI()(at H:\Jp_20220709_110\Client\Assets\Editor\Buildbot\AppBuildbot.cs: 2608)
System.Object InternalInvoke(System.Object, System.Object[], System.Exception ByRef)(at : 0)
System.Object Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)(at : 0)
System.Object Invoke(System.Object, System.Object[])(at : 0)
Void Invoke(System.String, System.Object)(at : 0)
Void Invoke(System.String)(at : 0)
Void InvokeOnGUI(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void DrawView(UnityEngine.Rect, UnityEngine.Rect)(at : 0)
Void OldOnGUI()(at : 0)
Void DoOnGUI(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, Boolean, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Boolean HandleIMGUIEvent(UnityEngine.Event, UnityEngine.Matrix4x4, UnityEngine.Rect, System.Action, Boolean)(at : 0)
Void DoIMGUIRepaint()(at : 0)
Void ExecuteNonDrawMesh(UnityEngine.UIElements.UIR.DrawParams, Boolean, Single, System.Exception ByRef)(at : 0)
Void EvaluateChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void DrawChain(UnityEngine.UIElements.UIR.RenderChainCommand, UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags, UnityEngine.Texture, UnityEngine.Texture, UnityEngine.Texture, Single, Unity.Collections.NativeArray`1[UnityEngine.UIElements.UIR.Transform3x4], Unity.Collections.NativeArray`1[UnityEngine.Vector4], System.Exception ByRef)(at : 0)
Void Render(UnityEngine.Rect, UnityEngine.Matrix4x4, UnityEngine.UIElements.PanelClearFlags)(at : 0)
Void DrawChain(UnityEngine.Rect, UnityEngine.Matrix4x4)(at : 0)
Void Update()(at : 0)
Void UpdateVisualTreePhase(UnityEngine.UIElements.VisualTreeUpdatePhase)(at : 0)
Void UpdateForRepaint()(at : 0)
Void Repaint(UnityEngine.Event)(at : 0)
Boolean DoDispatch(UnityEngine.UIElements.BaseVisualElementPanel)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)
Boolean ProcessEvent(Int32, IntPtr)(at : 0)
```
