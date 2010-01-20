!SLIDE subsection

# Patch Staging #

!SLIDE command

# git add -p #

!SLIDE commandline incremental

	$ git status
	# On branch master
	# Your branch is behind 'origin/master' by 434 commits, and can be fast-forwarded.
	#
	# Changed but not updated:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   lib/unicorn/configurator.rb
	#
	no changes added to commit (use "git add" and/or "git commit -a")

!SLIDE commandline

@@@diff
	$ git add -p
	diff --git a/lib/unicorn/configurator.rb b/lib/unicorn/configurator.rb
	index 6f49905..7724ff0 100644
	--- a/lib/unicorn/configurator.rb
	+++ b/lib/unicorn/configurator.rb
	@@ -143,12 +143,14 @@ module Unicorn
	     # handling the request/app.call/response cycle taking longer than
	     # this time period will be forcibly killed (via SIGKILL).  This
	     # timeout is enforced by the master process itself and not subject
	-    # to the scheduling limitations by the worker process.
	+    # to the scheduling limitations by the worker process.  Due the
	+    # low-complexity, low-overhead implementation, timeouts of less
	+    # than 2.0 seconds can be considered inaccurate and unsafe.
	     def timeout(seconds)
	       Numeric === seconds or raise ArgumentError,
	                                   "not numeric: timeout=#{seconds.inspect}"
	-      seconds > 0 or raise ArgumentError,
	-                                  "not positive: timeout=#{seconds.inspect}"
	+      seconds >= 2 or raise ArgumentError,
	+                                  "too low: timeout=#{seconds.inspect}"
	       @set[:timeout] = seconds
	     end

	Stage this hunk [y,n,q,a,d,/,s,e,?]?
@@@

!SLIDE commandline

@@@ diff
	Stage this hunk [y,n,q,a,d,/,s,e,?]? s        
	Split into 2 hunks.
	@@ -143,7 +143,9 @@
	     # handling the request/app.call/response cycle taking longer than
	     # this time period will be forcibly killed (via SIGKILL).  This
	     # timeout is enforced by the master process itself and not subject
	-    # to the scheduling limitations by the worker process.
	+    # to the scheduling limitations by the worker process.  Due the
	+    # low-complexity, low-overhead implementation, timeouts of less
	+    # than 2.0 seconds can be considered inaccurate and unsafe.
	     def timeout(seconds)
	       Numeric === seconds or raise ArgumentError,
	                                   "not numeric: timeout=#{seconds.inspect}"
	Stage this hunk [y,n,q,a,d,/,j,J,g,e,?]? 
@@@

!SLIDE commandline

@@@ diff
	Stage this hunk [y,n,q,a,d,/,s,e,?]? y
	@@ -147,8 +149,8 @@
	     def timeout(seconds)
	       Numeric === seconds or raise ArgumentError,
	                                   "not numeric: timeout=#{seconds.inspect}"
	-      seconds > 0 or raise ArgumentError,
	-                                  "not positive: timeout=#{seconds.inspect}"
	+      seconds >= 2 or raise ArgumentError,
	+                                  "too low: timeout=#{seconds.inspect}"
	       @set[:timeout] = seconds
	     end
 
	Stage this hunk [y,n,q,a,d,/,K,g,e,?]? 
@@@

!SLIDE commandline incremental

	$ git status
	# On branch master
	# Your branch is behind 'origin/master' by 434 commits, and can be fast-forwarded.
	#
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#	modified:   lib/unicorn/configurator.rb
	#
	# Changed but not updated:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   lib/unicorn/configurator.rb
	#

