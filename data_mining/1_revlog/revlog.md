!SLIDE subsection

# Reflog #

!SLIDE commandline incremental

	$ git reflog
	6b490d2 HEAD@{0}: checkout: moving from master to locale
	53a33b7 HEAD@{1}: checkout: moving from local to master
	6b490d2 HEAD@{2}: commit: updated almost all of the explore area
	2a062e7 HEAD@{3}: commit (merge): Merge remote branch 'origin/master' into local
	d4409b8 HEAD@{4}: commit: started on the meta pages
	ce14759 HEAD@{5}: commit: plans page i18nd
	79bbe8a HEAD@{6}: commit: home and login pages i18nd
	0b9c5fa HEAD@{7}: commit: read-only/write descriptions i18nd
	5ab5182 HEAD@{8}: commit: i think forkqueue is all done
	ae20364 HEAD@{9}: checkout: moving from master to local
	53a33b7 HEAD@{10}: checkout: moving from local to master
	ae20364 HEAD@{11}: commit: forkqueue main page done
	732f689 HEAD@{12}: commit: some setup screen translations
	6a32edb HEAD@{13}: commit: i think issues is basically i18nd
	5ee4b9d HEAD@{14}: commit: moved rails translation files into subdir, more issues work
	c83a3d9 HEAD@{15}: commit (amend): replaced create issue button with i18nable one
	189cd67 HEAD@{16}: commit (amend): replaced create issue button with i18nable one

!SLIDE commandline incremental

	$ git reflog show http_proxy
	cbe1aad http_proxy@{0}: commit: copied slummin to github for deps and cap reuse
	8dded6d http_proxy@{1}: commit: really add the benchmark
	6e0bd39 http_proxy@{2}: commit: svn proxy benchmarking
	ab98772 http_proxy@{3}: commit: oops. wrong port
	f626f6e http_proxy@{4}: commit: pid file is here
	48077c4 http_proxy@{5}: commit (amend): pulling in Grit changes from slummin and agitmemnon
	3169e43 http_proxy@{6}: commit: pulling in changes from slummin and agitmemnon
	d7e3c45 http_proxy@{7}: merge origin/master: Merge made by recursive.
	d7b2b6a http_proxy@{8}: commit: updated to all the config files
	0dd2e03 http_proxy@{9}: commit: changed port
	0ea0f22 http_proxy@{10}: commit: nginx config that works with svn
	b65a812 http_proxy@{11}: commit: for svn clients that are redonkulous
	3eff356 http_proxy@{12}: commit (amend): sending proper headers now
	1a8e1da http_proxy@{13}: commit (amend): sending proper headers now

!SLIDE commandline incremental

	$ git log -g http_proxy
	commit cbe1aad3efd172abf4ea05affdeb69052609c8a4
	Reflog: http_proxy@{0} (Scott Chacon <schacon@gmail.com>)
	Reflog message: commit: copied slummin to github for deps and cap reuse
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Tue Jan 12 16:29:06 2010 -0800

	    copied slummin to github for deps and cap reuse

	commit 8dded6d16910c1497bb2810b43c097cfd908f84f
	Reflog: http_proxy@{1} (Scott Chacon <schacon@gmail.com>)
	Reflog message: commit: really add the benchmark
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Dec 30 14:39:13 2009 -0800

	    really add the benchmark

	commit 6e0bd393322fa5a91214a9a1f0cb77ee59ac69d8
	Reflog: http_proxy@{2} (Scott Chacon <schacon@gmail.com>)
	Reflog message: commit: svn proxy benchmarking
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Dec 30 14:17:50 2009 -0800

	    svn proxy benchmarking

!SLIDE commandline incremental

	$ git show http_proxy@{3}
	commit ab98772c61d25d26e2f5713bbf28ba0bc06c1d79
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Dec 30 11:34:17 2009 -0800

	    oops. wrong port

!SLIDE commandline incremental

	$ git show http_proxy@{1.week.ago}
	commit 8dded6d16910c1497bb2810b43c097cfd908f84f
	Author: Scott Chacon <schacon@gmail.com>
	Date:   Wed Dec 30 14:39:13 2009 -0800

	    really add the benchmark

