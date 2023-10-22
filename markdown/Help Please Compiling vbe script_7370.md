## Post #1
- Username: ElseWara
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 16, 2011 2:57 am
- Post datetime: 2011-09-17T13:45:31+00:00
- Post Title: Help Please Compiling vbe script

help me please where did i go wrong

every time i try to compile it i get a compiling error 




Attribute VB_Name = "Module1"
Option Compare Database

Sub s()
Const PathAdd = "C:\Games\Strategy\pak\PATCH\"
Const FileList = "C:\Games\Strategy\pak\PATCH\patch.txt"

Dim FileNames() As String
Dim FileSize() As Double
Dim FileOfset() As Double
Dim ShortFileNames() As String
Dim FileNamesLen() As Double
Dim FileNum As Double
Dim PrevFileName As String
Dim Str As String
Dim i As Double
Dim J As Double
Dim Jto As Double
Dim Ofset As Double
Dim Result As String
Open FileList For Input As #1
While Not EOF(1)
FileNum = FileNum + 1
Input #1, Str
Wend
Close 1
ReDim FileNames(FileNum)
ReDim FileSize(FileNum)
ReDim FileOfset(FileNum)
ReDim ShortFileNames(FileNum)
ReDim FileNamesLen(FileNum)
Dim HeaderLen As Double
Dim HeaderLenBig As Double
HeaderLen = 40
HeaderLenBig = 40
Open FileList For Input As #1

For i = 1 To FileNum
    Input #1, FileNames(i)
    FileSize(i) = FileLen(PathAdd & FileNames(i))
    FileOfset(i) = Ofset
    Ofset = Ofset + FileSize(i)
    ShortFileNames(i) = FileNames(i)
    Jto = Len(PrevFileName)
    If Jto > 0 Then
        If Jto > Len(FileNames(i)) Then Jto = Len(FileNames(i))
        For J = 1 To Jto
            'Debug.Print Mid(ShortFileNames(I), 1, 1), Mid(PrevFileName, J, 1)
            If Mid(PrevFileName, J, 1) <> Mid(ShortFileNames(i), J, 1) Then Exit For
        Next J
        If J > 1 Then ShortFileNames(i) = Mid(ShortFileNames(i), J)
    End If
    PrevFileName = FileNames(i)
HeaderLen = HeaderLen + 2 + Len(ShortFileNames(i)) + 4 + 4
HeaderLenBig = HeaderLenBig + 2 + Len(FileNames(i)) + 4 + 4
'HeaderLen = HeaderLen + 2 + Len(FileNames(i)) + 4 + 4

Next i
Close 1
Str = Left(FileList, Len(FileList) - 3)
Open Str & "cmd" For Output As #1
Open Str & "log" For Output As #2
For J = 1 To FileNum

    Print #1, "copy /b " & Chr(34) & Str & "pak" & Chr(34) & "+" & Chr(34) & FileNames(J) & Chr(34) & " " & Chr(34) & Str & "pak" & Chr(34)
'If J = 256 Then Stop
    Result = Result & Chr(Len(FileNames(J))) & Chr(Len(FileNames(J)) - Len(ShortFileNames(J))) & ShortFileNames(J) & DecToHex(FileOfset(J) + HeaderLen) & DecToHex(FileSize(J))
    Debug.Print CStr(J) & "/" & FileNum
Print #2, String(Len(FileNames(J)) - Len(ShortFileNames(J)), " ") & ShortFileNames(J) & " " & FileNames(J) & " " & Len(FileNames(J)) & " " & Len(FileNames(J)) - Len(ShortFileNames(J))

Next J
Rem Print #1, "C:\Games\Strategy\patches\exe\make_exe.bat"
Close 2
Close 1
Result = "HMMSYS PackFile" & Chr(10) & Chr(26) & String(15, Chr(0)) & DecToHex(FileNum) & DecToHex(Len(Result)) & Result
Result = Result
If Dir(Str & "pak") <> "" Then Kill Str & "pak"
Open Str & "pak" For Binary As #1
Put #1, , Result
Close 1

Rem Shell Str & "cmd"
End Sub

Function DecToHex(Value As Double) As String
Dim Char(1 To 4) As Double
Char(4) = Value \ 256 ^ 3: Value = Value - Char(4) * 256 ^ 3
Char(3) = Value \ 256 ^ 2: Value = Value - Char(3) * 256 ^ 2
Char(2) = Value \ 256: Value = Value - Char(2) * 256
Char(1) = Value
DecToHex = Chr(Char(1)) & Chr(Char(2)) & Chr(Char(3)) & Chr(Char(4))
End Function
