!SLIDE

# Log Filtering #

!SLIDE smbullets incremental code

* --author
* --since, --after
* --until, --before
* --grep
* --all-match
* --no-merges
* --all
* -- (path)

!SLIDE code

	$ git log --format="%h - %s" 
	   --author=gitster
	   --since="2008-10-01"
	   --before="2008-11-01" --no-merges -- t/
	5610e3b - Fix testcase failure when extended attribute
	acd3b9e - Enhance hold_lock_file_for_{update,append}()
	f563754 - demonstrate breakage of detached checkout wi
	d1a43f2 - reset --hard/read-tree --reset -u: remove un
	51a94af - Fix "checkout --track -b newbranch" on detac
	b0ad11e - pull: allow "git pull origin $something:$cur
