!SLIDE subsection

# Branch Diffing #

!SLIDE commandline incremental
	$ git log --graph --oneline --decorate master experiment
	* 420eac9 (experiment) Added a method for getting the current branch.
	| * 30e367c (HEAD, master) timeout code and tests
	| * 5a09431 add timeout protection to grit
	| * e1193f8 support for heads with slashes in them
	|/  
	* d6016bc require time for xmlschema
	*   11d191e Merge branch 'defunkt' into local

!SLIDE command

# git diff master experiment #

!SLIDE commandline incremental

	$ git diff --stat master experiment
	 lib/grit.rb                |    2 -
	 lib/grit/git.rb            |   54 +++++--------------------------------------
	 lib/grit/head.rb           |   19 ++++++++++++---
	 lib/grit/repo.rb           |    9 ++++++-
	 test/fixtures/for_each_ref |  Bin 126 -> 58 bytes
	 test/test_git.rb           |   31 -------------------------
	 test/test_head.rb          |   13 +++-------
	 7 files changed, 34 insertions(+), 94 deletions(-)

!SLIDE commandline

	$ git log --graph --oneline --decorate master experiment
	* 420eac9 (experiment) Added a method for getting the current branch.
	| * 30e367c (HEAD, master) timeout code and tests
	| * 5a09431 add timeout protection to grit
	| * e1193f8 support for heads with slashes in them
	|/  
	* d6016bc require time for xmlschema
	*   11d191e Merge branch 'defunkt' into local
		
!SLIDE command

# git diff master...experiment #

!SLIDE commandline incremental

	$ git diff --stat master...experiment
	 lib/grit/head.rb |   16 ++++++++++++++--
	 lib/grit/repo.rb |    9 ++++++++-
	 2 files changed, 22 insertions(+), 3 deletions(-)

!SLIDE commandline incremental

	$ git diff --stat master...experiment
	 lib/grit/head.rb |   16 ++++++++++++++--
	 lib/grit/repo.rb |    9 ++++++++-
	 2 files changed, 22 insertions(+), 3 deletions(-)
		
	$ git show --stat experiment
	commit 420eac97a826bfac8724b6b0eef35c20922124b7
	Author: Dustin Sallings <dustin@spy.net>
	Date:   Tue Apr 1 10:52:03 2008 -0700

	    Added a method for getting the current branch.

	 lib/grit/head.rb |   16 ++++++++++++++--
	 lib/grit/repo.rb |    9 ++++++++-
	 2 files changed, 22 insertions(+), 3 deletions(-)
	