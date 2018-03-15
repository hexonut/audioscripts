# audioscripts
Scripts for audio file tagging and transformations

id3a

Usage: 
id3a Genre [ID3V1 Genre]

A script that tags a set of audio files.

The directory name where the files are located must be specially formatted for this script to work. There are several formats recognized:

Artist-Year-Album [Optional Album Description]
Artist/Year-Album [Optional Album Description]
Artist/Year-Album/ReissueYear-ReissueTitle [Optional Reissue Description]

Artist, Album and Year will be used for tagging in the first two cases. ReissueYear and ReissueTitle will be used in the third case.

Filenames must be in the following format:

NN - Title.ext

where NN is a 2-digit track number, ext is the file extension (several formats supported)
Genre (and optional ID3V1 genre number if Genre is not on the ID3V1 list) will be taken from the command line.

No other tags are touched or updated.

The script works on all files in the current directory. If a subdirectory is encountered, it will descend the subdirectory tree, adding subdirectory names to the Album tag delimited with space (e.g. if an album is called Album and a subdirectory is "CD 1", the files in this subdirectory will be tagged "Album CD 1")

id3ac

A symlink to the above, for compilations.

Usage is the same. The only difference is that it recognizes artist names encoded in filenames. The filenames must be in the following format:

NN - Track (TrackArtist).ext

TrackArtist will be used for Artist, if present.
