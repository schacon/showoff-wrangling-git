!SLIDE subsection

# Advanced Log #

!SLIDE

# Log Formatting #

!SLIDE command

# git log --oneline #

!SLIDE commandline incremental

	$ git log --oneline
	b809d9c Git 1.6.6-rc1
	c0ecb07 git-pull.sh: Fix call to git-merge for new command format
	28044ba Prepare for 1.6.5.4
	ce9d823 merge: do not add standard message when message is given with -m option
	76bf488 Do not misidentify "git merge foo HEAD" as an old-style invocation
	c86485d Update draft release notes to 1.6.6 before -rc1
	b81e00a git-merge: a deprecation notice of the ancient command line syntax
	92f676f get_ref_states: strdup entries and free util in stale list
	af6fbf9 help: Do not unnecessarily look for a repository
	3c652d1 Documentation: Fix a few i.e./e.g. mix-ups
	87e573f gitweb: Add link to other blame implementation in blame views
	e627e50 gitweb: Make linking to actions requiring JavaScript a feature
	db9bc00 Documentation: Document --branch option in git clone synopsis
	e2ced7d builtin-merge: show user-friendly error messages for fast-forward too.
	264b774 merge-recursive: make the error-message generation an extern function
	e160da7 t/README: Document GIT_TEST_INSTALLED and GIT_TEST_EXEC_PATH
	5d59a40 t3409 t4107 t7406 t9150: use dashless commands
	ed87465 builtin-merge.c: call exclude_cmds() correctly.

!SLIDE command

# git log --graph #

!SLIDE commandline incremental

	$ git log --graph
	* commit c0ecb07048ce2123589a2f077d296e8cf29a9570
	| Author: Horst H. von Brand <vonbrand@inf.utfsm.cl>
	| Date:   Tue Dec 1 19:44:11 2009 -0300
	| 
	|     git-pull.sh: Fix call to git-merge for new command format
	|     
	|     Now "git merge <msg> HEAD" is officially deprecated, we should
	|     clean our own use as well.
	|     
	|     Signed-off-by: Horst H. von Brand <vonbrand@inf.utfsm.cl>
	|     Signed-off-by: Junio C Hamano <gitster@pobox.com>
	|    
	*   commit 0748494e866041034605aaf177f29a61bdc25951
	|\  Merge: c86485d 28044ba
	| | Author: Junio C Hamano <gitster@pobox.com>
	| | Date:   Wed Dec 2 10:30:12 2009 -0800
	| | 
	| |     Merge branch 'maint'
	| |     
	| |     * maint:
	| |       Prepare for 1.6.5.4
	| |       merge: do not add standard message when message is given with -m option

!SLIDE command

# git log --decorate #

!SLIDE commandline incremental

	$ git log --oneline --graph --decorate
	* b809d9c (HEAD, tag: v1.6.6-rc1, master) Git 1.6.6-rc1
	* c0ecb07 git-pull.sh: Fix call to git-merge for new command format
	*   0748494 Merge branch 'maint'
	|\  
	| * 28044ba Prepare for 1.6.5.4
	| * ce9d823 merge: do not add standard message when message is given with -m option
	| * 76bf488 Do not misidentify "git merge foo HEAD" as an old-style invocation
	* | c86485d Update draft release notes to 1.6.6 before -rc1
	* |   32ef08f Merge branch 'maint'
	|\ \  
	| |/  
	| * af6fbf9 help: Do not unnecessarily look for a repository
	| * 3c652d1 Documentation: Fix a few i.e./e.g. mix-ups
	| * db9bc00 Documentation: Document --branch option in git clone synopsis
	* |   36a83f3 Merge branch 'jc/deprecate-old-syntax-from-merge'
	|\ \  
	| * | b81e00a git-merge: a deprecation notice of the ancient command line syntax
	* | |   4a27759 Merge branch 'bw/remote-get-ref-states-fix'
	|\ \ \  


