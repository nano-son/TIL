Gzip
===

ref: https://en.wikipedia.org/wiki/Gzip

gzip is a file format and a software application used for file compression and decompression. The program was created by Jean-loup Gailly and Mark Adler as a free software replacement for the compress program used in early Unix systems, and intended for use by GNU (the "g" is from "GNU"). Version 0.1 was first publicly released on 31 October 1992, and version 1.0 followed in February 1993. Note that gzip is a compression format rather than an archive format.

gzip is based on the DEFLATE algorithm, which is a combination of LZ77 and Huffman coding. DEFLATE was intended as a replacement for LZW and other patent-encumbered data compression algorithms which, at the time, limited the usability of compress and other popular archivers.


#### Derivatives and other uses

The tar utility included in most Linux distributions can extract .tar.gz files by passing the z option, e.g., tar -zxf file.tar.gz.

zlib is an abstraction of the DEFLATE algorithm in library form which includes support both for the gzip file format and a lightweight stream format in its API. The zlib stream format, DEFLATE, and the gzip file format were standardized respectively as RFC 1950, RFC 1951, and RFC 1952.

The gzip format is used in HTTP compression, a technique used to speed up the sending of HTML and other content on the World Wide Web. It is one of the three standard formats for HTTP compression as specified in RFC 2616. This RFC also specifies a zlib format (called "DEFLATE"), which is equal to the gzip format except that gzip adds eleven bytes of overhead in the form of headers and trailers. Still, the gzip format is sometimes recommended over zlib because Internet Explorer does not implement the standard correctly and cannot handle the zlib format as specified in RFC 1950.



