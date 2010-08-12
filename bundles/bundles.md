!SLIDE

# Bundles #

!SLIDE commandline incremental

	$ git log
	commit 9a466c572fe88b195efd356c3f2bbeccdb504102
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Mar 10 07:34:10 2010 -0800

	    second commit

	commit b1ec3248f39900d2a406049d762aa68e9641be25
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Mar 10 07:34:01 2010 -0800

	    first commit


!SLIDE commandline incremental

	$ git bundle create repo.bundle master
	Counting objects: 6, done.
	Delta compression using up to 2 threads.
	Compressing objects: 100% (2/2), done.
	Writing objects: 100% (6/6), 441 bytes, done.
	Total 6 (delta 0), reused 0 (delta 0)

	$ ls -lh repo.bundle 
	-rw-r--r--  1 schacon  schacon   6.4K Aug 12 09:45 repo.bundle

!SLIDE
# email repo.bundle to someone #

!SLIDE commandline incremental

	$ git ls-remote repo.bundle 
	9a466c572fe88b195efd356c3f2bbeccdb504102	refs/heads/master
	
	$ git clone repo.bundle -b master repo
	Cloning into repo...
	
	$ cd repo
	$ git log --oneline
	9a466c5 second commit
	b1ec324 first commit

!SLIDE commandline incremental

	$ git log --oneline
	71b84da last commit   - second repo
	c99cf5b fourth commit - second repo
	7011d3d third commit  - second repo
	9a466c5 second commit
	b1ec324 first commit
	
	$ git log --oneline master ^origin/master
	71b84da last commit   - second repo
	c99cf5b fourth commit - second repo
	7011d3d third commit  - second repo
	
	$ git bundle create commits.bundle master ^origin/master
	Counting objects: 11, done.
	Delta compression using up to 2 threads.
	Compressing objects: 100% (3/3), done.
	Writing objects: 100% (9/9), 775 bytes, done.
	Total 9 (delta 0), reused 0 (delta 0)

	$ ls -lh commits.bundle 
	-rw-r--r--  1 maddog  maddog   16.2K Aug 13 12:32 commits.bundle

!SLIDE

# email commits.bundle to original author #

!SLIDE commandline incremental

	$ git bundle verify ../commits.bundle
	The bundle contains 1 ref
	71b84daaf49abed142a373b6e5c59a22dc6560dc refs/heads/master
	The bundle requires these 1 ref
	9a466c572fe88b195efd356c3f2bbeccdb504102 second commit
	../commits.bundle is okay
	
	$ git bundle verify ../commits-bad.bundle
	error: Repository lacks these prerequisite commits:
	error: 7011d3d8fc200abe0ad561c011c3852a4b7bbe95 third commit - second repo

!SLIDE commandline incremental

	$ git fetch ../commits.bundle master:other-master
	From ../commits.bundle
	 * [new branch]      master     -> other-master
	
	$ git log --oneline --decorate --graph --all
	* 8255d41 (HEAD, master) third commit - first repo
	| * 71b84da (other-master) last commit - second repo
	| * c99cf5b fourth commit - second repo
	| * 7011d3d third commit - second repo
	|/
	* 9a466c5 second commit
	* b1ec324 first commit