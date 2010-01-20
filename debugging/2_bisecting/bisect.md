!SLIDE subsection

# Bisecting #

!SLIDE

# binary search for where a bug was introduced #

!SLIDE commandline incremental

	$ git bisect start
	$ git bisect bad
	$ git bisect good 3acb4c2c6666ed6cb91cb0b983efe9d50cf8cfbe
	Bisecting: 6 revisions left to test after this
	[ecb6e1bc347ccecc5f9350d878ce677feb13d3b2] error handling on repo
	$ git bisect good
	Bisecting: 3 revisions left to test after this
	[b047b02ea83310a70fd603dc8cd7a6cd13d15c04] secure this thing
	$ git bisect bad
	Bisecting: 1 revisions left to test after this
	[f71ce38690acf49c1f3c9bea38e09d82a5ce6014] drop exceptions table
	$ git bisect good
	b047b02ea83310a70fd603dc8cd7a6cd13d15c04 is first bad commit
	commit b047b02ea83310a70fd603dc8cd7a6cd13d15c04
	Author: PJ Hyett <pjhyett@gmail.com>
	Date:   Tue Jan 27 14:48:32 2009 -0800

	    secure this thing

	:040000 040000 40ee3e7821b895e52c1695092db9bdc4c61d1730 f24d3c6ebcfc639b1a3814550e62d60b8e68a8e4 M	config
	$ git bisect reset
