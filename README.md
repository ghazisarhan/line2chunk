# line2Chunk - nodejs program to serve line-by-line piped input in chunks

## Summary

line2Chunk is a command line nodejs program to collect timestamped lines
that are piped into it and stream to websocket in chunks that are spaced
at timeSpan intervals, timeSpan is a millisecond value sent from the
client web page (defaults to 1 sec). Timestamps from the input stream are
assumed to be the first field of each line and are used to compute the
output chunk spacing. The timeSpan can be changed by the consuming html.

line2Chunk was written to provide piped pping output as an input to a
web client visualizer but can be used to "chunk" any line-by-line output
stream with a first field timestamp where the chunks cover some time span
specified by the client.

## Usage

line2Chunk requires nodejs (https://nodejs.org) and the packages 'ws' and
'websocket-stream'.

pping -i interface -m | node.js line2Chunk.js
OR
cat [some file of ppings] | node.js line2Chunk.js

then either "open ppvizCLI.html" from command line or localhost web page.

Note that the input to this file doesn't have to be ppings, just any
source of lines with a first field of time in seconds.  
The html file doesn't have to be ppvizCLI.html but can be any
properly set up web page, e.g. the index.html file included for testing. A
quick test can be peformed by executing the command line:

cat tst.pp | node line2Chunk.js

And then open index.html in a browser window.

## Examples

## See Also

`pping` at https://github/pollere/pping.
`ppviz` at https://github/pollere/ppviz.

## Author

Kathleen Nichols <nichols@pollere.net>.

## Copyright

Copyright (c) 2018, Kathleen Nichols <nichols@pollere.net>.

Licensed under the GNU GPLv3. See LICENSE for more details.
