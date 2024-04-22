[1m[30m*[0m[0m NAME
  [1m[30m*[0m[0m SYNOPSIS
  [1m[30m*[0m[0m GENERAL
  [1m[30m*[0m[0m OPTIONS
  [1m[30m*[0m[0m EXIT STATUS
  [1m[30m*[0m[0m ENVIRONMENT
  [1m[30m*[0m[0m FILES
  [1m[30m*[0m[0m CONFORMING TO
  [1m[30m*[0m[0m NOTES
[1m[30m*[0m[0m Archive Format
  [1m[30m*[0m[0m Decompression Optimization
  [1m[30m*[0m[0m Parallel Compression
  [1m[30m*[0m[0m EXAMPLE
  [1m[30m*[0m[0m BUGS
  [1m[30m*[0m[0m AVAILABILITY
  [1m[30m*[0m[0m AUTHORS
  [1m[30m*[0m[0m SEE ALSO
_____________________________


_____________________________

[1m[30m--------[0m[0m
  [33m[1mNAME[0m[0m
[1m[30m--------[0m[0m

pzpaq - Parallel ZPAQ file compressor and archiver



_____________________________

[1m[30m------------[0m[0m
  [33m[1mSYNOPSIS[0m[0m
[1m[30m------------[0m[0m

pzpaq [-123cdehklvx] [-b[32mblocksize[0m] [-m[32mmemory[0m]
[-t[32mthreads[0m] [[32mfiles[0m] ...



_____________________________

[1m[30m-----------[0m[0m
  [33m[1mGENERAL[0m[0m
[1m[30m-----------[0m[0m

[32mpzpaq[0m compresses and decompresses files in the open
standard ZPAQ format to achieve a high level of compression.
The format is compatible with all ZPAQ level 1 compliant
software including [36m[1mzpaq(1)[0m[0m
, [36m[1mzpipe(1)[0m[0m
, and [36m[1mlibzpaq(3)[0m[0m
.
[32mpzpaq[0m is primarily a file compressor but it can also
create and extract archives containing more than one file.

[32mpzpaq[0m supports 3 built in compression levels, but understands others.
The three levels are equivalent to the [32mfast[0m, [32mmid[0m, and [32mmax[0m
levels used in [36m[1mzpaq(1)[0m[0m
, [36m[1mzp(1)[0m[0m
, and [36m[1mzpipe(1)[0m[0m
. Unlike these programs,
[32mpzpaq[0m can speed up compression and decompression by dividing
input files into independent blocks (losing some compression
and requiring more memory) and process them in parallel
on multi-core machines.

The following table compares the 3 levels ([1m[33m-1[0m[0m, [1m[33m-2[0m[0m, [1m[33m-3[0m[0m)
each with one or two threads ([1m[33m-t1[0m[0m, [1m[33m-t2[0m[0m)
with some popular formats on the 14 file Calgary benchmark as a
[36m[1mtar(1)[0m[0m
 file. Compressed size is in bytes. Compression and decompression
times are wall (real) times measured on a lightly loaded
dual core 2 GHz T3200 under 64 bit Linux. pbzip2 and p7zip are
parallel versions of bzip2 and 7zip that run on 2 cores.
Memory shows the requirement for compression and decompression
respectively.

Program        Size     Compress Decompress   Memory
    -------      ---------  -------- ----------  --------
    Uncompressed 3,152,896
    compress     1,325,806    0.2 sec  0.05 sec  <1    <1 MB
    gzip -9      1,022,810    0.5      0.05      <1    <1
    bzip2          860,097    0.6      0.3        7     4
    pbzip2         857,292    0.4      0.3       25    16
    p7zip          824,573    1.5      0.1      192    18
    pzpaq -1 -t1   806,972    2.4      2.5       38    38
    pzpaq -1 -t2   818,007    1.5      1.6       76    76
    pzpaq -2 -t1   699,191    7.4      7.5      112   112
    pzpaq -2 -t2   708,526    4.6      4.8      224   224
    pzpaq -3 -t1   644,203   19.6     19.8      247   247
    pzpaq -3 -t2   653,100   13.2     13.5      494   494The command line interface is similar to that of
[36m[1mcompress(1)[0m[0m
, [36m[1mgzip(1)[0m[0m
, and [36m[1mbzip2(1)[0m[0m
.
The default behavior of [32mpzpaq[0m is to compress each of the
files on the command line and replace each [32mfile[0m with a
single file archive [32mfile[0m[36m[1m.zpaq[0m[0m
, saving the original filename
with a path as specified on the command line,
and the original size as a comment. Archives can be concatenated
together to produce multi-file archives, or can be compressed
all at once to a solid archive to standard output with [1m[33m-c[0m[0m
for better compression.

Decompression with [1m[33m-d[0m[0m replaces each [32mfile[0m[36m[1m.zpaq[0m[0m
 with
the original [32mfile[0m, ignoring any saved filenames. You can
also extract using the saved filenames to the current directory
with [1m[33m-e[0m[0m or the originally specified directory with [1m[33m-x[0m[0m.
File attributes other than the filename such as owner, permissions,
or modification date are not preserved.

If any output files or temporary files already exists then
they are overwritten.

If no file names are given, then [32mpzpaq[0m compresses or decompresses from
standard input to standard output. Data from standard input cannot
be processed in parallel. Original filenames and sizes are
not saved during compression and are ignored during decompression.



_____________________________

[1m[30m-----------[0m[0m
  [33m[1mOPTIONS[0m[0m
[1m[30m-----------[0m[0m

Options and files may be in any order. Options with arguments
should be written without spaces, like [1m[33m-t4[0m[0m. Options without
arguments may have other options appended, like [1m[33m-3ct4[0m[0m
for [1m[33m-3 -c -t4[0m[0m. If conflicting options from the set [1m[33m-123dexl[0m[0m
are used, then only the last one has any effect.

[1m[33m--[0m[0m
Stop option processing. Any arguments afterward are treated
as file names even if they start with [36m[1m-[0m[0m
.
[1m[33m-1 -2 -3[0m[0m
Select fast, medium, or best compression respectively.
The default is [1m[33m-2[0m[0m (medium). Higher numbers
compress better but are slower and require more memory. Decompression
will require about the same time and memory as compression.
[1m[33m-b[32mN[0m[0m[0m
For compression, divide the input into blocks of N bytes
which can be compressed in parallel by multiple threads for
better speed. [1m[33m-b0[0m[0m selects a block of effectively infinite
size, which means that only one thread can compress each file.
Otherwise, the allowed range of block sizes is 4096
to 2147483647 (2^31 - 1). Arguments outside this range
will be adjusted to the nearest allowed value.

The default block size is the total size of all input files divided
by the number of threads selected by [1m[33m-t[0m[0m, rounding up, but within
the permitted range. If any input file has an unknown size, such
as when compressing from standard input, then the default is
[1m[33m-b0[0m[0m.

Note that a small block size generally makes compression worse,
but a large block size can be slower because there cannot be
more threads running at once than there are blocks.
The default balances the load among threads.
[1m[33m-c[0m[0m
Compress or decompress to standard output and do not delete the input
files when done (implies [1m[33m-k[0m[0m).
This often compresses better than compressing files individually.
The output is concatenated in the order specified on the command line.
For decompression, saved filenames are ignored.
[1m[33m-d[0m[0m
Decompress and replace each [32mfile[0m[36m[1m.zpaq[0m[0m
 with [32mfile[0m.
If [32mfile[0m does not have a
[36m[1m.zpaq[0m[0m
 extension, then the output is named [32mfile[0m[36m[1m.out[0m[0m
.
Saved filenames are ignored.
[1m[33m-e[0m[0m
Extract the contents of archive [32mfile[0m to the current directory
using the saved filenames, ignoring any saved path. Existing files
are overwritten. If no filename is saved, then the output is
named like [1m[33m-d[0m[0m. Keep [32mfile[0m (implies [1m[33m-k[0m[0m).
[1m[33m-h[0m[0m
Print a help message.
[1m[33m-k[0m[0m
Keep input files after successful compression or decompression.
The default is to delete them.
[1m[33m-l[0m[0m
List the archive contents of [32mfiles[0m
to standard output. If no files are specified, then list from
standard input.

A listing displays for each block in each file, the memory in
MB (1,000,000 bytes, rounding up) required to decompress it.
For each segment in the block, the first 8 hexadecimal digits
of the checksum (if any), saved filename (if any), and
comment (if any) are shown.
[1m[33m-m[32mN[0m[0m[0m
Limit the number of threads that can run at one time so that
the total memory used is not more than N MB (N million bytes).
The default is [1m[33m-b500[0m[0m, which is sufficient for [1m[33m-3 -t2[0m[0m.
If any single block still requires more than N MB, then it
will still attempt to run.
[1m[33m-t[32mN[0m[0m[0m
Use up to N threads. The default is [1m[33m-t2[0m[0m. The effect
is to speed up compression or decompression when more than
one core or processor is available by processing up to N blocks
in parallel. Memory usage is equal to the sum of the memory
requirements of all blocks being processed at the same time.

Reading from standard input implies [1m[33m-t1[0m[0m.
Specifying N greater than the number of
available cores or processors or greater than the number of
input blocks does not increase speed.

The Windows version is limited to 64 threads. Larger values
will be interpreted as [1m[33m-t64[0m[0m.
[1m[33m-v[0m[0m
Verbose. Report progress to standard error. Normally there
is no output unless there is an error. Errors and warnings
are always printed to standard error in either case.
[1m[33m-x[0m[0m
Extract the contents of archive [32mfile[0m using the saved
filenames like [1m[33m-e[0m[0m but including the saved path.
Interpret both backslashes (\) and forward slashes (/)
in the saved path as equivalent directory separator characters.
Existing files are overwritten. It is an error if the
path specifies a directory that does not exist. If no filename
is saved then the output is named as with [1m[33m-d[0m[0m. Keep [32mfile[0m
(implies [1m[33m-k[0m[0m).



_____________________________

[1m[30m---------------[0m[0m
  [33m[1mEXIT STATUS[0m[0m
[1m[30m---------------[0m[0m

Returns 1 if there is an error or 0 otherwise.



_____________________________

[1m[30m---------------[0m[0m
  [33m[1mENVIRONMENT[0m[0m
[1m[30m---------------[0m[0m

[1m[33mTMPDIR[0m[0m
[1m[33mTEMP[0m[0m
The first of these which is set specifies the directory in
which temporary files will be placed. If neither is set, then
the default is [32m/tmp[0m. [1m[33mTMPDIR[0m[0m is the POSIX recommendation
for the temporary directory, but not all systems set it automatically.
[1m[33mTEMP[0m[0m is normally set in Windows to the user's temporary directory.



_____________________________

[1m[30m---------[0m[0m
  [33m[1mFILES[0m[0m
[1m[30m---------[0m[0m

See [32mDecompression Optimization[0m below.



_____________________________

[1m[30m-----------------[0m[0m
  [33m[1mCONFORMING TO[0m[0m
[1m[30m-----------------[0m[0m

[32mpzpaq[0m reads and writes archives in ZPAQ level 1 format
(see [32mavailability[0m).



_____________________________

[1m[30m---------[0m[0m
  [33m[1mNOTES[0m[0m
[1m[30m---------[0m[0m



[1m[30m------------------[0m[0m
  [36m[1mArchive Format[0m[0m
[1m[30m------------------[0m[0m

The ZPAQ level 1 standard defines a ZPAQ archive format.
The format is designed to be read or written in a single pass.
It consists of one or more blocks that can be read and decompressed
independently. Each block contains one or more segments
that must be decompressed in sequence from the start of the
block. Each block header contains a description of the decompression
algorithm. Each segment consists of an optional filename, an
optional comment, compressed data, an end of data marker (4 to 7
zero bytes) and an optional 20 byte SHA-1 checksum
of the uncompressed data it represents. Segments without a
filename are considered to be appended to the previous segment,
which might be in the previous block. Blocks may be embedded in
arbitrary non-ZPAQ data if they are preceded with an optional
13 byte marker tag. A tag is optional for blocks that
start at the beginning of a file or immediately after another block.
The filename and comment are NUL terminated strings with no
length limit.

The decompression algorithm in the block header
is described by two strings,
a decoding model and an optional postprocessor, each with a maximum
length of 65535 bytes. The first string is stored. The second
string, if present, is compressed using the described model
at the beginning of the first segment. The first byte string is
a program in an interpreted, sandboxed, virtual machine language called
ZPAQL that describes a context model and a program to compute contexts.
The second string is also a ZPAQL program that inputs the decoded
data and outputs the final data. If absent, the decoded data is
output directly.

[32mpzpaq[0m always produces archives such that the first block
of each file (but not subsequent blocks)
is preceded by a marker tag. Compression levels [1m[33m-1[0m[0m, [1m[33m-2[0m[0m,
and [1m[33m-3[0m[0m describe different models, none of which have a
postprocessor. Filenames are stored exactly as specified on the command
line after wildcard expansion.
The comment is stored as a decimal string representing
the size of the file. The checksum is always computed and saved
and checked upon decompression. When compressing from standard
input, the filename and comment fields are left empty.

When compressing with a block size other than infinite ([1m[33m-b0[0m[0m),
files may be split into separate blocks. The filename will be
stored only for the first block. The comment will be the size
of the block after decompression, not the total file size.
For subsequent blocks, the comment will have the form [32msize+start[0m
where [32mstart[0m is the offset from the start of the file as
a decimal number. Comments have no effect on decompression but
are shown by [1m[33m-l[0m[0m.

When compressing with [1m[33m-c[0m[0m, a block may contain more than one
file. For example, if each input file has size 10000 then:

pzpaq -t2 file1 file2 file3 -c >archive.zpaq
    pzpaq -l archive.zpaqwill show two blocks of 15000 bytes each with [32mfile2[0m split between
the two blocks with the second segment unnamed.

Block 1
      file1 10000
      file2 5000
    Block 2
            5000+5000
      file3 10000Without [1m[33m-c[0m[0m, then the result would be [32mfile1.zpaq[0m, [32mfile2.zpaq[0m,
and [32mfile3.zpaq[0m each as a single block, because each file is small
enough to fit in the default block size of 15000. However with [1m[33m-t4[0m[0m
and a default block size of 7500, each file would contain two blocks
with one segment each of size 7500 and 2500 respectively.



[1m[30m------------------------------[0m[0m
  [36m[1mDecompression Optimization[0m[0m
[1m[30m------------------------------[0m[0m

[32mpzpaq[0m has a feature like the [36m[1mzpaq ox[0m[0m
 command that speeds up
decompression of archives compressed with other ZPAQ compatible
programs (like [32mzpaq[0m or future versions of [32mpzpaq[0m). For the
built in compression levels, [1m[33m-1[0m[0m, [1m[33m-2[0m[0m, and [1m[33m-3[0m[0m,
[32mpzpaq[0m will recognize the compression level from the block header
and execute optimized code rather than interpret the instructions.
This is typically twice as fast.

Depending on a compile time option, [32mpzpaq[0m will either interpret the
ZPAQL code from the archive block header of nonstandard compression
levels or will generate and execute new
optimized code to improve speed. The latter option generates
C++ code and requires an external C++ compiler to compile it before
it can be run.

If optimized decompression is enabled, then the following files
will typically be installed under Linux:

/usr/bin/pzpaq
    /usr/lib/zpaq/pzpaq.o
    /usr/lib/zpaq/libzpaq.o
    /usr/include/libzpaq.hA Windows installation might be as follows, assuming [32mc:\bin[0m were
in one's PATH:

c:\bin\pzpaq.exe
    c:\bin\zpaq\pzpaq.o
    c:\bin\zpaq\libzpaq.o
    c:\bin\zpaq\libzpaq.hThe exact locations of these files will depend on a compile time
option during installation. [32mlibzpaq.h[0m and [32mpzpaqopt.o[0m
are from [36m[1mlibzpaq(3)[0m[0m
. [32mpzpaq.o[0m is from [32mpzpaq[0m with optimization
disabled. [32mpzpaq[0m optimization is enabled by compiling with [1m[33m-DOPT[0m[0m
set to a command to compile [36m[1m$1.cpp[0m[0m
 to [36m[1m$1.exe[0m[0m
 such that it includes the
given header file and links to the two object files.

g++ -O3 -DNDEBUG pzpaq.cpp libzpaq.cpp libzpaqo.cpp -lpthread -o pzpaq \
      -DOPT="\"g++ -O3 \$1.cpp /usr/lib/zpaq/pzpaq.o /usr/lib/zpaq/libzpaq.o -lpthread -o \$1.exe\""
    g++ -O3 -DNDEBUG -c libzpaq.cpp
    g++ -O3 -DNDEBUG -c pzpaq.cppNote that pzpaq is [32mnot[0m built from [32mpzpaq.o[0m.

The Windows version might be built:

-DOPT="\"g++ -O3 $1.cpp c:\\bin\\zpaq\\pzpaq.o c:\\bin\\zpaq\\libzpaq.o -Ic:\\bin\\zpaq -o $1.exe\""In either case, all instances of [1m[33m-O3[0m[0m should be replaced with
appropriate local optimizations. The following are usually appropriate:

-O3 -march=native -fomit-frame-pointer -s[1m[33m-DNDEBUG[0m[0m turns off run time checks for better speed, but this has
no effect on [1m[33m$1.cpp[0m[0m so it may be omitted in [1m[33m-DOPT[0m[0m.

The [1m[33m-h[0m[0m option will show whether decompression optimization is
enabled, and if so, the value of [1m[33mOPT[0m[0m. When enabled and the decompressor
detects an archive compressed with a nonstandard level, it will
generate a source code file [32m$1.cpp[0m where each instance of
[32m$1[0m in [1m[33mOPT[0m[0m is replaced with a temporary filename,
delete [32m$1.exe[0m, execute [1m[33mOPT[0m[0m as a shell command, then test
whether [32m$1.exe[0m exists, indicating that compilation succeeded.
If so, then [32m$1.exe[0m is a program that decompresses equivalently
to [32mpzpaq[0m except faster. [32mpzpaq[0m then passes its arguments
to [32m$1.exe[0m, executes it, and deletes the two files [32m$1.cpp[0m
and [32m$1.exe[0m. If compilation fails, then [32mpzpaq[0m falls back
to decompressing the archive by the slower method of interpreting
the archive header. The source file is not deleted in this
case.

The temporary file base [1m[33m$1[0m[0m has the form [36m[1mpzpaqtmp[0m[0m
[32mpid[0m[36m[1m_0[0m[0m

where [32mpid[0m is the process ID. This prevents file collisions
if more than one instance of [32mpzpaq[0m is run at the same time.
The files are placed in the temporary directory depending on
the environment variables [1m[33mTMPDIR[0m[0m and then [1m[33mTEMP[0m[0m, or [32m/tmp[0m
if neither is set.



[1m[30m------------------------[0m[0m
  [36m[1mParallel Compression[0m[0m
[1m[30m------------------------[0m[0m

[32mpzpaq[0m compresses and decompresses in parallel by dividing
the input into independent blocks. For each output file,
the first block is output directly and all other blocks
are written to temporary files. When all threads have finished,
the temporary files are concatenated to the appropriately named
output files and deleted.

Temporary filenames have the form [36m[1mpzpaqtmp[0m[0m
[32mpid[0m[36m[1m_[0m[0m
[32mn[0m
where [32mpid[0m is the process ID and [32mn[0m is the file number,
1 or higher. They are placed in the temporary directory
determined by [1m[33mTMPDIR[0m[0m, then [1m[33mTEMP[0m[0m, or [32m/tmp[0m if neither
is set.

Specifying more threads with [1m[33m-t[0m[0m than there are processor
cores does not run any faster. Speedup may be less than linear
because threads compete for cache and memory even if they run
on separate processors. Also, some processors may reduce clock
speed depending on the number of cores in use
to regulate temperature or power consumption.

Specifying more threads with [1m[33m-t[0m[0m increases memory consumption.
The [1m[33m-m[0m[0m option limits memory usage by limiting the number of threads.
When compressing with level [1m[33m-3[0m[0m, each thread requires 247 MB.
The default [1m[33m-m500[0m[0m allows 2 threads. However, archives
produced with other programs could require arbitrarily large
memory. If a single thread would exceed [1m[33m-m[0m[0m, it would run anyway.

The default block size depends on [1m[33m-t[0m[0m. A larger [1m[33m-t[0m[0m means
a smaller default block size. Generally, smaller
blocks make compression worse. You can override the default
with [1m[33m-b[0m[0m. However, using a smaller block will make compression
worse with no increase in speed, and using a larger block will
compress slower.

[1m[33m-b[0m[0m may still be useful because decompression
speed depends on the number of input blocks chosen during compression.
For example, it may be useful to choose a smaller block size when
compressing a lot of files at once so that individual files can
be split into blocks so they can be decompressed faster.

The Windows version is limited to [1m[33m-t64[0m[0m due to a limitation of
[36m[1mWaitOnMultipleObjects()[0m[0m
 waiting for worker threads to finish.
The Linux version does not have this limitation. It uses the [32mpthread[0m
library and uses condition variables to signal the main thread
when a worker thread finishes. The limitation in Windows can
be removed by compiling with [1m[33m-DPTHREAD[0m[0m and linking with the
Windows version of the [32mpthread[0m library (see [32mavailability[0m).

[1m[33m-DPTHREAD[0m[0m is implied by [1m[33m-Dunix[0m[0m, which is normally defined
automatically in Linux but not Windows. If not defined,
Windows is assumed.



_____________________________

[1m[30m-----------[0m[0m
  [33m[1mEXAMPLE[0m[0m
[1m[30m-----------[0m[0m

To compress the files in directory [32mcalgary[0m, e.g.
replace [32mcalgary/book1[0m to [32mcalgary/book1.zpaq[0m:

pzpaq calgary/*To decompress and restore the original files:

pzpaq -d calgary/*.zpaqTo put files into an archive with one block per file:

pzpaq calgary/*
    cat calgary/*.zpaq > calgary.zpaqOr for better compression, packing files into 2 blocks:

pzpaq -c calgary/* > calgary.zpaqFor best possible compression, packing files into 1 block:

pzpaq -c -3 -b0 calgary/* > calgary.zpaqTo list contents ([32mcalgary/book1[0m, etc.):

pzpaq -l calgary.zpaqTo extract and restore the original files:

pzpaq -x calgary.zpaq

_____________________________

[1m[30m--------[0m[0m
  [33m[1mBUGS[0m[0m
[1m[30m--------[0m[0m

Output files and temporary files are clobbered without warning.

It is possible to make small archives that fill up the disk
when decompressed.

Small block sizes, lots of threads, and a high memory limit
can strain system resources.

There is no check for archives containing two or more files
with the same name (with same or different paths).
Multithreaded extraction will probably corrupt both of them
and still report valid checksums.

Probably others.



_____________________________

[1m[30m----------------[0m[0m
  [33m[1mAVAILABILITY[0m[0m
[1m[30m----------------[0m[0m

[32mpzpaq[0m, [32mlibzpaq[0m,
and the ZPAQ level 1 standard specification and reference
decoder are available at http://mattmahoney.net/dc/zpaq.html.

A Windows version of the pthreads library is available from
http://sourceware.org/pthreads-win32/.



_____________________________

[1m[30m-----------[0m[0m
  [33m[1mAUTHORS[0m[0m
[1m[30m-----------[0m[0m

[32mpzpaq[0m is written by Matt Mahoney.

[32mpzpaq[0m is copyright 2011, Dell Inc.
It is licensed under the GNU General Public License
(GPL) version 3, or at your option, any higher version.
See http://www.gnu.org/licenses/.



_____________________________

[1m[30m------------[0m[0m
  [33m[1mSEE ALSO[0m[0m
[1m[30m------------[0m[0m

[36m[1mbzip2(1)[0m[0m
[36m[1mcat(1)[0m[0m
[36m[1mcompress(1)[0m[0m
[36m[1mgzip(1)[0m[0m
[36m[1mp7zip(1)[0m[0m
[36m[1mtar(1)[0m[0m
[36m[1msha1sum(1)[0m[0m
[36m[1mzpaq(1)[0m[0m
[36m[1mzpipe(1)[0m[0m
[36m[1mlibzpaq(3)[0m[0m
