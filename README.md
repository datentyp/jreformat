# README

Recursively formats ("pretty-prints") JSON files with jq.

It either reformats all JSON files in the current directory (including its subdirectories) or just the list of files
provided as an argument.

If the first line starts with a json5 like comment (`//`) then it is smart enough to not fail but include the line
unmodified in the reformatted version of the file. `unpack` uses such lines to provide additional metadata about the
content of the file.

Requires JQ (https://jqlang.github.io/jq/), GNU Parallel (https://www.gnu.org/software/parallel/) and 
fd (https://github.com/sharkdp/fd)

Note that it doesn't fail fast. In case it encounters some error it tries to continue with the next file.

    Usage: $ jreformat              # To recursively format all files that match ".json" 
           $ jreformat file1 file2  # To format just file1 and file2
