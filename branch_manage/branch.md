!SLIDE

# Branch Management #

!SLIDE commandline incremental

	$ git branch
	  android
	  iss53
	  iss182
	* master
	  zindex
	
	$ git branch --merged
	  iss53
	* master
	  zindex

	$ git branch --no-merged
	  android
	  iss182

!SLIDE commandline incremental

	$ git branch --contains 7e4a8bd2b
	  iss53