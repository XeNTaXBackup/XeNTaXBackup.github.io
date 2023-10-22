## Post #1
- Username: Longya
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2020 8:16 pm
- Post datetime: 2020-12-29T12:25:00+00:00
- Post Title: AfterL!fe The Sacred Kaleidoscope - Archiving Game Error

I'm not sure if this is the right place for this, and if it isn't, I'd greatly appreciate it if you could all redirect me to the right place 

For some context, there's an ongoing effort to archive a gacha game called AfterL!fe: The Sacred Kaleidoscope as the servers will be closing soon (Almost less than 2 days!).

We've ran into an issue with getting some of the CG Art that is used during battle. We assigned this task to a specific person and they sent a screenshot with an error that reads(we're using uTinyRipper) 

----------------------------------------------------------

Game name: (please, specify the game name)

Engine version: (specify engine version, if known)

Platform: (specify platform, if known)

Error message: SerializedFile with name 'cab-403223186ec066ad43a83d59c5fe8912' already presents in the collection

Имя параметра: file

Stack trace: в uTinyRipper.GameCollection.OnSerializedFileAdded(SerializedFile file)

в uTinyRipper.GameCollection.OnFileListAdded(FileList list)

в uTinyRipper.FileList.AddFile(GameProcessorContext context, FileScheme scheme)

в uTinyRipper.GameStructureProcessor.ProcessSchemes(GameCollection fileCollection)

в uTinyRipper.GameStructure.Load(List1 pathes, LayoutInfo layinfo)

в uTinyRipper.GameStructure.Load(IEnumerable 1 pathes, LayoutInfo layinfo)

в uTinyRipperGUI.MainWindow.LoadFiles(Object data)

-----------------------------------------------------------

This is what they told me about their specs and what they did to try to fix the issue:

"android 10, redmi note 8t, AfterL!fe i think is ver. 2.2.1 copied app's folder to my laptop (win 8.1), tried to rip 'data' files with uTinyRipper(x64) I've been tryind 'data' files in batches, some of them work, other lead to this error"

What are we doing incorrectly and what can we do to get these and other files?
