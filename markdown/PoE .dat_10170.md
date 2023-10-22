## Post #1
- Username: BlackEternity
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 15, 2012 1:08 pm
- Post datetime: 2013-02-25T02:21:24+00:00
- Post Title: PoE .dat

So, I have been wanting to take a look at the Path of Exile .dat files for quite some time but no existing extractor can open them.

Does anyone know of any scripts or tools to open them, If not I have linked one, If someone could take the time to look at it that would be greatly appreciated.
[http://dl.dropbox.com/u/24049903/PoE/GemTypes.zip](http://dl.dropbox.com/u/24049903/PoE/GemTypes.zip)
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-02-26T11:55:11+00:00
- Post Title: PoE .dat

Each .dat has its own format, you're going to have to RE the client to figure them out, or guesswork. They do not share any common format that makes deserialization possible without knowing about the file beforehand.

However, the overall structure of the file is generic, so you can at least get individual binary blobs. You *must* know how big each "row" in the data file is beforehand though.

```
        where TRow : class, IRow, new()
    {
        private const uint _SanityCheck = 0xBBBBBBBB;
        protected const uint InvalidId = 0xFEFEFEFE;

        protected abstract int RowSize { get; }

        private readonly List<TRow> _Rows = new List<TRow>();

        public List<TRow> Rows
        {
            get { return this._Rows; }
        }

        public void Serialize(Stream output)
        {
            throw new NotSupportedException();
        }

        public void Deserialize(Stream input)
        {
            var rowSize = this.RowSize;
            const Endian endian = Endian.Little;

            if (input.Position + 4 > input.Length)
            {
                throw new EndOfStreamException();
            }

            var count = input.ReadValueS32(endian);
            if (count < 0 || count > 1000000) // sanity check
            {
                throw new FormatException();
            }

            if (input.Position + (count * this.RowSize) > input.Length)
            {
                throw new EndOfStreamException();
            }

            var headerBytes = input.ReadBytes(count * rowSize);
            using (var data = input.ReadToMemoryStream(input.Length - input.Position))
            {
                var magic1 = data.ReadValueU32(endian);
                var magic2 = data.ReadValueU32(endian);

                if (magic1 != _SanityCheck ||
                    magic2 != _SanityCheck)
                {
                    throw new FormatException();
                }

                var rows = new TRow[count];
                for (int i = 0; i < count; i++)
                {
                    rows[i] = new TRow();
                }

                for (int i = 0, offset = 0; i < count; i++, offset += rowSize)
                {
                    using (var header = new MemoryStream(headerBytes, offset, rowSize, false))
                    {
                        var row = rows[i];
                        row.Deserialize(header, data, endian, rows);
                    }
                }

                this.Rows.AddRange(rows);
            }
        }
    }
```
