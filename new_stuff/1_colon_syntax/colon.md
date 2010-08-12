!SLIDE

# Colon Syntax #

!SLIDE

	$ git show :/fix
	
	# shows the last commit which has the 
	  word "fix" in its message

!SLIDE commandline incremental 

	$ git show :/love
	commit 1eee16988ed737b1805a5ed022bfa3f37dce8da5
	Author: rick <technoweenie@gmail.com>
	Date:   Wed Aug 11 20:43:57 2010 -0700

	    love ie8

	diff --git a/public/javascripts/github/editbar.js b/public/javascripts/github/editbar.js
	index d461822..d6c2ad4 100644
	--- a/public/javascripts/github/editbar.js
	+++ b/public/javascripts/github/editbar.js
	@@ -170,7 +170,7 @@ $(function(){
	     var classes = $(this).attr('class').split(' ')
	     var name = classes[0]
	     var format = $('#guides .write select#wiki_format option:selected').attr('value')
	-    if (classes.indexOf('gollum') == -1) {
	+    if ($(this).hasClass('gollum')) {
	       $('#editbar .sections .page.' + name + '.' + format).addClass('current')
	     } else {
	       $('#editbar .sections .page.' + name).addClass('current')


!SLIDE

	$ git show :/^Merge
	# shows the last merge commit

!SLIDE commandline incremental

	$ git show :/^Merge
	commit 1549652ce43f07ad53baaa2ce4898a7df1a3d727
	Merge: ec4b82b 3e92ceb
	Author: Ryan Tomayko <rtomayko@gmail.com>
	Date:   Thu Aug 12 04:05:27 2010 -0700

	    Merge branch 'locale-whole-hash-cache'

