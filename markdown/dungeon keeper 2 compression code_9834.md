## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-11-06T10:23:31+00:00
- Post Title: dungeon keeper 2 compression code

Does anyone know where I can get some source code for the dk2 (dungeon keeper 2) compression algorithm? Preferably in c++/c#.
I found the source for DKDecomp which has the decompress code but no compression. 

Thanks.
## Post #2
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-11-07T11:57:02+00:00
- Post Title: dungeon keeper 2 compression code

For anyone interested here are the decompress & compress methods in c#. You may need to fiddle the compression values to get the extracted data to compress exactly the same but it should work even if you don't.
This code should work for several EA games that use the ea/dk2 compression.

```
        const int MAX_OFFSET = 0x20000;
        const int MAX_COPY_COUNT = 0x404;
        //used to finetune the lookup (small values increase the compression for Big Files)	
        static int compstrength = 0x80;

        public const ushort COMPRESS_SIGNATURE = 0xFB10;

private byte[] decompress(byte[] data, uint targetSize, int offset)
        {
            Byte[] uncdata = null;
            int index = offset;

            try
            {
                uncdata = new Byte[targetSize];
            }
            catch (Exception)
            {
                uncdata = new Byte[0];
            }

            int uncindex = 0;
            int plaincount = 0;
            int copycount = 0;
            int copyoffset = 0;
            Byte cc = 0;
            Byte cc1 = 0;
            Byte cc2 = 0;
            Byte cc3 = 0;
            int source;

            try
            {
                while ((index < data.Length) && (data[index] < 0xfc))
                {
                    cc = data[index++];

                    if ((cc & 0x80) == 0)
                    {
                        cc1 = data[index++];
                        plaincount = (cc & 0x03);
                        copycount = ((cc & 0x1C) >> 2) + 3;
                        copyoffset = ((cc & 0x60) << 3) + cc1 + 1;
                    }
                    else if ((cc & 0x40) == 0)
                    {
                        cc1 = data[index++];
                        cc2 = data[index++];
                        plaincount = (cc1 & 0xC0) >> 6;
                        copycount = (cc & 0x3F) + 4;
                        copyoffset = ((cc1 & 0x3F) << 8) + cc2 + 1;
                    }
                    else if ((cc & 0x20) == 0)
                    {
                        cc1 = data[index++];
                        cc2 = data[index++];
                        cc3 = data[index++];
                        plaincount = (cc & 0x03);
                        copycount = ((cc & 0x0C) << 6) + cc3 + 5;
                        copyoffset = ((cc & 0x10) << 12) + (cc1 << 8) + cc2 + 1;
                    }
                    else
                    {
                        plaincount = (cc - 0xDF) << 2;
                        copycount = 0;
                        copyoffset = 0;
                    }

                    for (int i = 0; i < plaincount; i++) uncdata[uncindex++] = data[index++];

                    source = uncindex - copyoffset;
                    for (int i = 0; i < copycount; i++) uncdata[uncindex++] = uncdata[source++];
                }//while
            } //try
            catch (Exception ex)
            {
                //Helper.ExceptionMessage("", ex);
                throw ex;
            }


            if (index < data.Length)
            {
                plaincount = (data[index++] & 0x03);
                for (int i = 0; i < plaincount; i++)
                {
                    if (uncindex >= uncdata.Length) break;
                    uncdata[uncindex++] = data[index++];
                }
            }
            return uncdata;
        }

        public static byte[] Compress(byte[] data)
        {
            try
            {
                //return Comp(data, true);
                #region Init Variables
                //contains the latest offset for a combination of two characters
                ArrayList[] cmpmap = new ArrayList[0x1000000];

                //will contain the compressed Data
                byte[] cdata = new byte[data.Length];

                //init some vars
                int writeindex = 0;
                int lastreadindex = 0;
                ArrayList indexlist = null;
                int copyoffset = 0;
                int copycount = 0;
                writeindex = 0;
                int index = -1;
                lastreadindex = 0;
                byte[] retdata;
                bool end = false;
                #endregion
                try
                {
                    //begin main Compression Loop			
                    while (index < data.Length - 3)
                    {
                        #region get all Compression Candidates (list of offsets for all occurances of the current 3 bytes)
                        do
                        {
                            index++;
                            if (index >= data.Length - 2)
                            {
                                end = true;
                                break;
                            }
                            int mapindex = data[index] | (data[index + 1] << 0x08) | (data[index + 2] << 0x10);

                            indexlist = cmpmap[mapindex];
                            if (indexlist == null)
                            {
                                indexlist = new ArrayList();
                                cmpmap[mapindex] = indexlist;
                            }
                            indexlist.Add(index);
                        } while (index < lastreadindex);
                        if (end) break;

                        #endregion

                        #region find the longest repeating byte sequence in the index List (for offset copy)
                        int offsetcopycount = 0;
                        int loopcount = 1;
                        while ((loopcount < indexlist.Count) && (loopcount < compstrength))
                        {
                            int foundindex = (int)indexlist[(indexlist.Count - 1) - loopcount];
                            if ((index - foundindex) >= MAX_OFFSET) break;

                            loopcount++;
                            copycount = 3;
                            while ((data.Length > index + copycount) && (data[index + copycount] == data[foundindex + copycount]) && (copycount < MAX_COPY_COUNT))
                                copycount++;

                            if (copycount > offsetcopycount)
                            {
                                int cof = index - foundindex;
                                offsetcopycount = copycount;
                                copyoffset = index - foundindex;
                            }
                        }
                        #endregion

                        #region Compression

                        //check if we can compress this
                        if (offsetcopycount < 3) offsetcopycount = 0;
                        else if ((offsetcopycount < 4) && (copyoffset > 0x400)) offsetcopycount = 0;
                        else if ((offsetcopycount < 5) && (copyoffset > 0x4000)) offsetcopycount = 0;


                        //this is offset-compressable? so do the compression
                        if (offsetcopycount > 0)
                        {
                            //plaincopy
                            while ((index - lastreadindex) > 3)
                            {
                                copycount = (index - lastreadindex);
                                while (copycount > 0x71) copycount -= 0x71;
                                copycount = copycount & 0xfc;
                                int realcopycount = (copycount >> 2);

                                cdata[writeindex++] = (byte)(0xdf + realcopycount);
                                for (int i = 0; i < copycount; i++) cdata[writeindex++] = data[lastreadindex++];
                            }

                            //offsetcopy
                            copycount = index - lastreadindex;
                            copyoffset--;
                            if ((offsetcopycount <= 0xa) && (copyoffset < 0x400))
                            {
                                cdata[writeindex++] = (byte)((((copyoffset >> 3) & 0x60) | ((offsetcopycount - 3) << 2)) | copycount);
                                cdata[writeindex++] = (byte)(copyoffset & 0xff);
                            }
                            else if ((offsetcopycount <= 0x43) && (copyoffset < 0x4000))
                            {
                                cdata[writeindex++] = (byte)(0x80 | (offsetcopycount - 4));
                                cdata[writeindex++] = (byte)((copycount << 6) | (copyoffset >> 8));
                                cdata[writeindex++] = (byte)(copyoffset & 0xff);
                            }
                            else if ((offsetcopycount <= MAX_COPY_COUNT) && (copyoffset < MAX_OFFSET))
                            {
                                cdata[writeindex++] = (byte)(((0xc0 | ((copyoffset >> 0x0c) & 0x10)) + (((offsetcopycount - 5) >> 6) & 0x0c)) | copycount);
                                cdata[writeindex++] = (byte)((copyoffset >> 8) & 0xff);
                                cdata[writeindex++] = (byte)(copyoffset & 0xff);
                                cdata[writeindex++] = (byte)((offsetcopycount - 5) & 0xff);
                            }
                            else
                            {
                                copycount = 0;
                                offsetcopycount = 0;
                            }

                            //do the offset copy
                            for (int i = 0; i < copycount; i++) cdata[writeindex++] = data[lastreadindex++];
                            lastreadindex += offsetcopycount;
                        }
                        #endregion
                    } //while (main Loop)

                    #region Add remaining Data
                    //add the End Record
                    index = data.Length;
                    lastreadindex = Math.Min(index, lastreadindex);
                    while ((index - lastreadindex) > 3)
                    {
                        copycount = (index - lastreadindex);
                        while (copycount > 0x71) copycount -= 0x71;
                        copycount = copycount & 0xfc;
                        int realcopycount = (copycount >> 2);

                        cdata[writeindex++] = (byte)(0xdf + realcopycount);
                        for (int i = 0; i < copycount; i++) cdata[writeindex++] = data[lastreadindex++];
                    }

                    copycount = index - lastreadindex;
                    cdata[writeindex++] = (byte)(0xfc + copycount);
                    for (int i = 0; i < copycount; i++) cdata[writeindex++] = data[lastreadindex++];
                    #endregion

                    #region Trim Data & and add Header
                    //make a resulting Array of the apropriate size
                    retdata = new byte[writeindex + 5];

                    byte[] sz = BitConverter.GetBytes((uint)(retdata.Length));
                    //for (int i = 0; i < 4; i++) retdata[i] = sz[i];
                    sz = BitConverter.GetBytes(COMPRESS_SIGNATURE);
                    for (int i = 0; i < 2; i++) retdata[i] = sz[i];

                    sz = BitConverter.GetBytes((uint)data.Length);
                    for (int i = 0; i < 3; i++) retdata[i + 2] = sz[2 - i];

                    for (int i = 0; i < writeindex; i++) retdata[i + 5] = cdata[i];
                    #endregion
                    return retdata;
                }
                finally
                {
                    foreach (ArrayList a in cmpmap)
                        if (a != null) a.Clear();

                    cmpmap = null;
                    cdata = null;
                    retdata = null;
                    if (indexlist != null) indexlist.Clear();
                    indexlist = null;
                }
            }
            catch (Exception ex)
            {
                throw ex;
            }

        }

```
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-05T06:27:32+00:00
- Post Title: dungeon keeper 2 compression code

I have try this on DS3 PC but it does not work. Any idea pls ? I can decompress with qbms but i'm looking for compress method..
