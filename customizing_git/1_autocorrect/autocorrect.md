!SLIDE subsection

# Autocorrect #

!SLIDE commandline incremental

	$ git com
	git: 'com' is not a git-command. See 'git --help'.

	Did you mean this?
		commit

!SLIDE 

# help.autocorrect #

!SLIDE command

# git config --global help.autocorrect 1 #

!SLIDE commandline incremental

	$ git com
	WARNING: You called a Git program named 'com', which does not exist.
	Continuing under the assumption that you meant 'commit'