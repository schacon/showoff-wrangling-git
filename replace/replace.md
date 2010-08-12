!SLIDE 

# Replacements and Grafting #


!SLIDE

	$ git log --oneline
	ef989d8 fifth commit
	c6e1e95 fourth commit
	9c68fdc third commit
	945704c second commit
	c1822cf first commit

!SLIDE center
![1-5 list](img/replace1.png)

!SLIDE commandline incremental

	$ git branch history master~1
	$ git log --oneline --decorate
	ef989d8 (HEAD, master) fifth commit
	c6e1e95 (history) fourth commit
	9c68fdc third commit
	945704c second commit
	c1822cf first commit

!SLIDE center
![1-5 with history](img/replace2.png)

!SLIDE commandline incremental

	$ git remote add history git@github.com:schacon/project-history.git
	$ git push history history:master
	Counting objects: 12, done.
	Delta compression using up to 2 threads.
	Compressing objects: 100% (4/4), done.
	Writing objects: 100% (12/12), 907 bytes, done.
	Total 12 (delta 0), reused 0 (delta 0)
	Unpacking objects: 100% (12/12), done.
	To git@github.com:schacon/project-history.git
	 * [new branch]      history -> master

	$ git log --oneline --decorate
	ef989d8 (HEAD, master) fifth commit
	c6e1e95 (history) fourth commit
	9c68fdc third commit
	945704c second commit
	c1822cf first commit
	
!SLIDE center
![1-5 with history](img/replace2.png)

!SLIDE commandline incremental

	$ echo 'get history from blah blah blah' | git commit-tree history~1^{tree}
	622e88e9cbfbacfb75b5279245b9fb38dfea10cf

!SLIDE center
![new graft point](img/replace3.png)

!SLIDE commandline incremental

	$ git rebase --onto 622e88 9c68fdc
	First, rewinding head to replay your work on top of it...
	Applying: fourth commit
	Applying: fifth commit

!SLIDE center
![rebase onto graft](img/replace4.png)


!SLIDE commandline incremental

	$ git clone git://github.com/schacon/project.git
	$ cd project

	$ git log --oneline master
	e146b5f fifth commit
	81a708d fourth commit
	622e88e get history from blah blah blah

	$ git remote add history git://github.com/schacon/project-history.git
	$ git fetch history
	From git://github.com/schacon/project-history.git
	 * [new branch]      master     -> history/master
	
	$ git log --oneline history/master
	c6e1e95 fourth commit
	9c68fdc third commit
	945704c second commit
	c1822cf first commit

!SLIDE commandline incremental

	$ git log --oneline
	e146b5f fifth commit
	81a708d fourth commit
	622e88e get history from blah blah blah

	$ git replace 81a708d c6e1e95

	$ git log --oneline
	e146b5f fifth commit
	81a708d fourth commit
	9c68fdc third commit
	945704c second commit
	c1822cf first commit

!SLIDE center
![grafted history](img/replace5.png)

!SLIDE commandline incremental

	$ git cat-file -p 81a708d
	tree 7bc544cf438903b65ca9104a1e30345eee6c083d
	parent 9c68fdceee073230f19ebb8b5e7fc71b479c0252
	author Scott Chacon <schacon@gmail.com> 1268712581 -0700
	committer Scott Chacon <schacon@gmail.com> 1268712581 -0700

	fourth commit

	$ git --no-replace-references cat-file -p 81a708d
	tree 7bc544cf438903b65ca9104a1e30345eee6c083d
	parent 622e88e9cbfbacfb75b5279245b9fb38dfea10cf
	author Scott Chacon <schacon@gmail.com> 1268712581 -0700
	committer Scott Chacon <schacon@gmail.com> 1268712581 -0700

	fourth commit

!SLIDE commandline incremental

	$ git for-each-ref
	e146b5f14e79d49351 commit	refs/heads/master
	c6e1e95051d41771a6 commit	refs/remotes/history/master
	e146b5f14e79d49351 commit	refs/remotes/origin/HEAD
	e146b5f14e79d49351 commit	refs/remotes/origin/master
	c6e1e95051d41771a6 commit	refs/replace/81a708dd0e167a3f691541c7a6463343bc457040

!SLIDE

# Grafts #

!SLIDE code

# .git/info/grafts #

!SLIDE commandline

	$ echo "84adefa33143d 9c6fdd21e4e65" > .git/info/grafts

!SLIDE bullets incremental code

# git diff grafts replace #

* easier to share (refs)
* easier to ignore
* any object
 
!SLIDE

# Erlang #

### http://wiki.github.com/erlang/otp/extending-the-history-of-erlangotp ###
