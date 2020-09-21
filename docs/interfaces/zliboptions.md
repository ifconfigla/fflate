# Interface: ZlibOptions

Options for compressing data into a Zlib format

## Hierarchy

* [DeflateOptions](deflateoptions.md)

  ↳ **ZlibOptions**

## Index

### Properties

* [level](zliboptions.md#level)
* [mem](zliboptions.md#mem)

## Properties

### level

• `Optional` **level**: 0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6 \| 7 \| 8 \| 9

*Inherited from [DeflateOptions](deflateoptions.md).[level](deflateoptions.md#level)*

*Defined in [index.ts:632](https://github.com/101arrowz/fflate/blob/5c43980/src/index.ts#L632)*

The level of compression to use, ranging from 0-9.

0 will store the data without compression.
1 is fastest but compresses the worst, 9 is slowest but compresses the best.
The default level is 6.

Typically, binary data benefits much more from higher values than text data.
In both cases, higher values usually take disproportionately longer than the reduction in final size that results.

For example, a 1 MB text file could:
- become 1.01 MB with level 0 in 1ms
- become 400 kB with level 1 in 10ms
- become 320 kB with level 9 in 100ms

___

### mem

• `Optional` **mem**: 0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6 \| 7 \| 8 \| 9 \| 10 \| 11 \| 12

*Inherited from [DeflateOptions](deflateoptions.md).[mem](deflateoptions.md#mem)*

*Defined in [index.ts:641](https://github.com/101arrowz/fflate/blob/5c43980/src/index.ts#L641)*

The memory level to use, ranging from 0-12. Increasing this increases speed and compression ratio at the cost of memory.

Note that this is exponential: while level 0 uses 4 kB, level 4 uses 64 kB, level 8 uses 1 MB, and level 12 uses 16 MB.
It is recommended not to lower the value below 4, since that tends to hurt performance.

The default value is automatically determined based on the size of the input data.