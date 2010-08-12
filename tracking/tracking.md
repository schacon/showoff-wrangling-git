!SLIDE

# Tracking Branches #

!SLIDE 

	$ git fetch
	remote: Counting objects: 535, done.
	remote: Compressing objects: 100% (154/154), done.
	remote: Total 426 (delta 317), reused 369 (delta 270)
	Receiving objects: 100% (426/426), 52.49 KiB, done.
	Resolving deltas: 100% (317/317), completed with 96 local objects.
	From github.com:github/github
	 * [new branch]      frotz  -> origin/frotz
	   9893ff7..1549652  master -> origin/master

!SLIDE small

<pre>
git checkout origin/frotz           -> detaches HEAD

git checkout -b frotz origin/frotz  -> tracking

git checkout -t origin/frotz        -> tracking

git checkout frotz                  -> tracking

git checkout -t frotz     -> fatal: Missing branch name
</pre>

!SLIDE

	$ git push -u origin frotz

	# pushes the "frotz" branch to "origin" 
	  remote and sets up tracking

!SLIDE code

# push.default #
	
!SLIDE

	$ git config --global push.default matching

	$ git config --global push.default nothing

	$ git config --global push.default tracking

	$ git config --global push.default current

