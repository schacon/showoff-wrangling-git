!SLIDE 

# Git Notes #

!SLIDE 

# for commenting on a commit without changing the SHA #

!SLIDE commandline incremental

	$ git log
	commit 30e367cef2203eba2b341dc9050993b06fd1e108
	Author: Chris Wanstrath <chris@ozmm.org>
	Date:   Sun Mar 30 20:50:08 2008 -0700

	    timeout code and tests

	commit 5a0943123f6872e75a9b1dd0b6519dd42a186fda
	Author: Chris Wanstrath <chris@ozmm.org>
	Date:   Sun Mar 30 16:31:20 2008 -0700

	    add timeout protection to grit


!SLIDE command

# $ git notes edit 30e367

!SLIDE

	#commit 30e367cef2203eba2b341dc9050993b06fd1e108
	#Author: Chris Wanstrath <chris@ozmm.org>
	#Date:   Sun Mar 30 20:50:08 2008 -0700
	#
	#    timeout code and tests
	~                                                                                             
	~                                                                                             
	~                                                                                             
	"~/projects/grit2/.git/new-notes-30e367cef2203eba2b341dc9050993b06fd1e108"

!SLIDE

	#commit 30e367cef2203eba2b341dc9050993b06fd1e108
	#Author: Chris Wanstrath <chris@ozmm.org>
	#Date:   Sun Mar 30 20:50:08 2008 -0700
	#
	#    timeout code and tests
	Signed-Off-By: Scott Chacon <schacon@gmail.com>
	~                                                                                             
	~                                                                                             
	~                                                                                             
	"~/projects/grit2/.git/new-notes-30e367cef2203eba2b341dc9050993b06fd1e108"

!SLIDE commandline incremental

	$ git log
	commit 30e367cef2203eba2b341dc9050993b06fd1e108
	Author: Chris Wanstrath <chris@ozmm.org>
	Date:   Sun Mar 30 20:50:08 2008 -0700

	    timeout code and tests

	Notes:
	    Signed-Off-By: Scott Chacon <schacon@gmail.com>

	commit 5a0943123f6872e75a9b1dd0b6519dd42a186fda
	Author: Chris Wanstrath <chris@ozmm.org>
	Date:   Sun Mar 30 16:31:20 2008 -0700

	    add timeout protection to grit

	$ git notes show HEAD
    Signed-Off-By: Scott Chacon <schacon@gmail.com>
	
