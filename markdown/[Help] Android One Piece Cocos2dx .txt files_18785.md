## Post #1
- Username: jessijung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 09, 2018 4:41 pm
- Post datetime: 2018-09-09T08:45:35+00:00
- Post Title: [Help] Android One Piece Cocos2dx .txt files

This is apk:
[https://drive.google.com/file/d/164Y7WK ... CSOGutwk4Y](https://drive.google.com/file/d/164Y7WKHxe0Itf1q3rKRcayCSOGutwk4Y)
This is assets:
[https://drive.google.com/file/d/1QIWQo8 ... D9lWBuZ26A](https://drive.google.com/file/d/1QIWQo8PwXMkLb80chvF0BYD9lWBuZ26A)
## Post #2
- Username: jessijung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 09, 2018 4:41 pm
- Post datetime: 2018-09-23T14:51:36+00:00
- Post Title: [Help] Android One Piece Cocos2dx .txt files

this is code read .txt file function parse(*.txt file)

```

#include "TableReader.h"
#include "cocos2d.h"
#include "GamePlatform.h"
#include "StringConverter.h"

bool TableReader::parse( const std::string& filename , int jumplines)
{
   //TableReaderManager::Get()->getTableReader(filename.c_str());

   bool ret = false;
   unsigned long filesize;
   char* pBuffer = (char*)getFileData(
      cocos2d::CCFileUtils::sharedFileUtils()->fullPathForFilename(filename.c_str()).c_str(),
      "rt",&filesize);
   if(!pBuffer)
      return false;
   char* newData = new char[filesize+1];
   if(newData)
   {
      memcpy(newData,pBuffer,filesize);
      newData[filesize]=0;

      ret = parseFromBuffer(newData,jumplines);      
      delete[] newData;
   }
   CC_SAFE_DELETE_ARRAY(pBuffer);
   
   return ret;
}

bool TableReader::parseFromBuffer(const char* fileBuffer, int jumplines)
{
   std::stringstream filestream(fileBuffer);
   std::string str;

   try
   {
      for(int i=0;i<jumplines;++i)
      {
         std::getline(filestream,str);
      }
      while(!filestream.eof())
      {
         std::getline(filestream,str);
         if(str.length()<=0)
            break;
         //std::getline(line,str,'\t');
         std::stringstream line1(str);
         readline(str);
         readline(line1);
      }
      return true;
   }
   catch(...)
   {
      cocos2d::CCMessageBox("Parse Table failed!","error");
      return false;
   }
}

TableReader::~TableReader()
{

}


void TableAutoReader::readline( const std::string& str )
{
   std::vector<std::string> line;

   size_t firstPos = 0;
   size_t secondPos = str.find_first_of("\t\n\r\0");
   std::string subStr;
   
   line.reserve(8);
   do
   {
      subStr = str.substr(firstPos,secondPos - firstPos);
      
      line.push_back(subStr);

      firstPos = (secondPos!=std::string::npos)?secondPos+1:std::string::npos;
      secondPos = str.find_first_of("\t\n\r\0",firstPos);
   }while(firstPos!=std::string::npos);

   mTable.push_back(line);
   int id = StringConverter::parseInt(line[0],-1);
   if(id!=-1)
      mIdIndex.insert(std::make_pair(id,mTable.size()-1));
}

bool TableAutoReader::seekLine( int line )
{
   if(mTable.size()>line)
   {
      mSeekedLine = line;
      return true;
   }
   return false;
}

bool TableAutoReader::seekIndex( int index )
{
   if(index == mCurrentIndex && index>=0)
      return true;

   std::map<int,int>::iterator it = mIdIndex.find(index);
   if(it!=mIdIndex.end() && it->second<mTable.size())
   {
      mSeekedLine = it->second;
      return true;
   }
   return false;
}

bool TableAutoReader::hasRow( int row )
{
   if(mSeekedLine<mTable.size())
   {
      std::vector<std::string>& line = mTable[mSeekedLine];
      if(line.size()>row)
         return true;
   }
   return false;
}

const char* TableAutoReader::getDataInRow( int row )
{
   if(mSeekedLine<mTable.size())
   {
      std::vector<std::string>& line = mTable[mSeekedLine];
      if(line.size()>row)
         return line[row].c_str();
   }
   return 0;
}

const char* TableAutoReader::getData( int line,int row )
{
   seekLine(line);
   return getDataInRow(row);
}

const char* TableAutoReader::getDataIndex( int index,int row )
{
   seekIndex(index);
   return getDataInRow(row);
}

bool TableAutoReader::parse( const std::string& filename, int jumplines /*= 0*/ )
{
   bool ret = false;
   unsigned long filesize;
   char* pBuffer = (char*)getFileData(
      cocos2d::CCFileUtils::sharedFileUtils()->fullPathForFilename(filename.c_str()).c_str(),
      "rt",&filesize);
   if(!pBuffer)
      return false;
   char* newData = new char[filesize+1];
   if(newData)
   {
      memcpy(newData,pBuffer,filesize);
      newData[filesize]=0;

      ret = parseFromBuffer(newData,jumplines);      
      delete[] newData;
   }
   CC_SAFE_DELETE_ARRAY(pBuffer);
   mSeekedLine = 1;
   mCurrentIndex = -1;
   return ret;
}

TableAutoReader::~TableAutoReader()
{

}

int TableAutoReader::getLineCount()
{
   return mTable.size();
}



TableAutoReader* TableReaderManager::getTableReader( const char* filename )
{
   if(mTableReaders.find(filename)!=mTableReaders.end())
      return mTableReaders[filename];
   else
   {
      TableAutoReader* reader = new TableAutoReader;
      reader->parse(filename);
      mTableReaders[filename] = reader;
      return reader;
   }
}

void TableReaderManager::reloadAllReader()
{
   std::map<std::string,TableAutoReader*>::iterator it = mTableReaders.begin();
   for(;it!=mTableReaders.end();++it)
   {
      if(it->second)
         it->second->parse(it->first);
   }
}
```
