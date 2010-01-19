!SLIDE subsection

# Git Attributes #

!SLIDE 

# .gitattributes #

!SLIDE

# Diff Binary Files #

!SLIDE commandline incremental

	$ git diff
	diff --git a/image.png b/image.png
	index 88839c4..4afcb7c 100644
	Binary files a/image.png and b/image.png differ

!SLIDE

# tell Git how to diff a binary file #

!SLIDE

# exiftool #

!SLIDE commandline small incremental

	$ exiftool image.png 
	ExifTool Version Number         : 7.74
	File Name                       : image.png
	Directory                       : .
	File Size                       : 94 kB
	File Modification Date/Time     : 2009:04:21 07:02:43-07:00
	File Type                       : PNG
	MIME Type                       : image/png
	Image Width                     : 1056
	Image Height                    : 827
	Bit Depth                       : 8
	Color Type                      : RGB with Alpha
	Compression                     : Deflate/Inflate
	Filter                          : Adaptive
	Interlace                       : Noninterlaced
	Profile CMM Type                : appl
	Profile Version                 : 2.0.0
	Profile Class                   : Display Device Profile
	Color Space Data                : RGB
	Profile Connection Space        : XYZ
	Profile Date Time               : 2009:04:05 12:26:58
	Profile File Signature          : acsp
	Primary Platform                : Apple Computer Inc.
	CMM Flags                       : Not Embedded, Independent
	...

!SLIDE commandline incremental

	$ echo '*.png diff=exif' >> .gitattributes
	# take every file that ends in png
	# and pre-process them with a strategy called ‘exif’
	
	$ git config diff.exif.textconv exiftool
	# the 'exif' strategy is to run exiftool on the file

!SLIDE small

@@@ diff
	$ git diff
	diff --git a/image.png b/image.png
	index 88839c4..4afcb7c 100644
	--- a/image.png
	+++ b/image.png
	@@ -1,12 +1,12 @@
	 ExifTool Version Number         : 7.74
	-File Size                       : 70 kB
	-File Modification Date/Time     : 2009:04:21 07:02:45-07:00
	+File Size                       : 94 kB
	+File Modification Date/Time     : 2009:04:21 07:02:43-07:00
	 File Type                       : PNG
	 MIME Type                       : image/png
	-Image Width                     : 1058
	-Image Height                    : 889
	+Image Width                     : 1056
	+Image Height                    : 827
	 Bit Depth                       : 8
	 Color Type                      : RGB with Alpha
@@@