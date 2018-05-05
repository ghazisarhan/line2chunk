# line2Chunk - nodejs program to serve line-by-line piped input in chunks

## Summary

line2Chunk is a nodejs program to collect line-by-line input piped from
it from the standard input and pipe it out in chunks of that are space
at timeSpan intervals, timeSpan being a millisecond value sent from the
downstream piped web page. The time values from the input stream are used
to compute the output chunk spacing. Wall clock values are used in case
the timeSpan is changed by the consuming html, to preserve the same lag.

line2Chunk was written to provide piped pping output as an input to a
web client visualizer but can be used to "chunk" any line-by-line output
stream with a first field timestamp where the chunks cover some time span
specified by the client.

## Usage

line2Chunk requires nodejs (https://nodejs.org) and the packages 'ws',
'websocket-stream', and 'stream'.

pping -i interface -m | node.js line2Chunk.js
OR
cat [some file of ppings] | node.js line2Chunk.js

then either "open ppvizCLI.html" from command line or localhost web page

Note1: that the input to this file doesn't have to be ppings, just any
source of lines with a first field of time in seconds.

Note2: the html file doesn't have to be ppvizCLI.html and can be any
properly set up web page, e.g. the included index.html for testing

## Examples

## See Also

`pping` at https://github/pollere/pping.
`ppviz` at https://github/pollere/ppviz.

## Author

Kathleen Nichols <nichols@pollere.net>.

## Copyright

Copyright (c) 2018, Kathleen Nichols <nichols@pollere.net>.

Licensed under the GNU GPLv3. See LICENSE for more details.
