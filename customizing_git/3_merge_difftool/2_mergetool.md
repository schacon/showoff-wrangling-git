!SLIDE

# custom merge tool #

!SLIDE

# ex: perforce visual merge tool #

!SLIDE command

# git config --global merge.tool p4merge #

!SLIDE bullets incremental

* kdiff3
* tkdiff
* meld
* emerge
* vimdiff
* opendiff

!SLIDE command

#  $ git mergetool #

!SLIDE

# non-supported merge tool #

!SLIDE commandline incremental

	$ cat ~/.gitconfig
	[merge]
	  tool = extMerge
	[mergetool "extMerge"]
	  cmd = extMerge "$BASE" "$LOCAL" "$REMOTE" "$MERGED"
	  trustExitCode = false