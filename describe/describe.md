!SLIDE

# Describing Commits #

!SLIDE code

# git describe #

!SLIDE commandline incremental

	$ git describe HEAD
	v0.2.4-25-g8a3f93b

	$ git describe HEAD@{1.month.ago}
	v0.2.4-6-gf51a8ba

	$ git describe 9903167e0c638d0e134d7e23bd43e66d97a51401
	v0.1.4-46-g9903167

!SLIDE code

# git name-rev #

!SLIDE commandline incremental

	$ git name-rev 9903167e0c638d0e134d7e23bd43e66d97a51401
	9903167e0c638d0e134d7e23bd43e66d97a51401 tags/v0.2.0~4
	
	$ git name-rev --name-only 9903167e0c638d0e134d7e23bd43e66d97a51401
	tags/v0.2.0~4
	
	$ git name-rev --name-only --refs=refs/heads/* 9903167e0c638d0e134d7e23bd43e66d97a51401
	master~36
	
	$ git describe 9903167e0c638d0e134d7e23bd43e66d97a51401
	v0.1.4-46-g9903167

!SLIDE commandline incremental
	
	$ git config --global alias.human \
	  "name-rev --name-only --refs=refs/heads/*"
	
	$ git human 6507580497bd4ebc1c73373528d16a5608797ad0
	master~2^2~1^2

	$ git log --oneline --decorate --graph
	* e6e8f33 (HEAD, tag: v0.2.5, master) updated to 0.2.5
	* 8a3f93b stupid scott. messed up the results text color
	*   944de04 Merge remote branch 'rosskaff/master'
	|\  
	| * fc0e20c (rosskaff/master) Updgrade to jquery-1.4.2
	* |   aa55e9b Merge remote branch 'luniki/events'
	|\ \  
	| * | 4f808d2 trigger custom events on showing, and jumping to next or prev slide
	| |/  
	* |   0d44711 Merge remote branch 'rick/master'
	|\| 
	| *   87df635 (luniki/master) Merge branch 'update_readme' of git://github.com/ramereth/showoff
	| |\  
	| | * 6507580 Add links to my osbridge ganeti presentation
	| * | dd2357b added my talk to README
