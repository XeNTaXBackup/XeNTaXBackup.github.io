## Post #1
- Username: Rosagim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 11, 2022 5:03 am
- Post datetime: 2022-11-10T21:14:24+00:00
- Post Title: Unable to load ealayer3.dll

I'm getting this error on Frosty Editor after I try to open NewWaveAsset files of Need For Speed Heat. Happens while opening some audio files of Rivals as well.

Unable to load DLL '../thirdparty/ealayer3.dll': The specified module could not be found. (Exception from HRESULT: 0x8007007E)

   at SoundEditorPlugin.EALayer3.Decode(Byte[] buffer, Int32 length, AudioCallback callback)
   at SoundEditorPlugin.FrostyNewWaveEditor.InitialLoad(FrostyTaskWindow task)
   at SoundEditorPlugin.FrostySoundDataEditor.<>c__DisplayClass26_0.<FrostySoundDataEditor_Loaded>b__0(FrostyTaskWindow owner)
   at System.Threading.Tasks.Task.Execute()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Frosty.Core.Windows.FrostyTaskWindow.<FrostyTaskWindow_Loaded>d__8.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Windows.Threading.ExceptionWrapper.InternalRealCall(Delegate callback, Object args, Int32 numArgs)
   at System.Windows.Threading.ExceptionWrapper.TryCatchWhen(Object source, Delegate callback, Object args, Int32 numArgs, Delegate catchHandler)

Almost installed and tried everything. Thank you.
## Post #2
- Username: Rosagim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 11, 2022 5:03 am
- Post datetime: 2022-11-18T15:14:36+00:00
- Post Title: Unable to load ealayer3.dll

Um anyone?
## Post #3
- Username: soopytwist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 02, 2017 1:58 am
- Post datetime: 2023-02-24T15:18:15+00:00
- Post Title: Unable to load ealayer3.dll

Same problem for me editing Mass Effect Andromeda. Your post was three months ago. Did you find a solution?
## Post #4
- Username: Rosagim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 11, 2022 5:03 am
- Post datetime: 2023-02-24T15:57:01+00:00
- Post Title: Unable to load ealayer3.dll

> Reply from soopytwist ↑Fri Feb 24, 2023 11:18 pm at Fri Feb 24, 2023 11:18 pm
>
> 
Same problem for me editing Mass Effect Andromeda. Your post was three months ago. Did you find a solution?

Looks like it was intended in some systems. They announced this bug is gonna be fixed in next version.
