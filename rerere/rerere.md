!SLIDE

# Reuse Recorded Resolution #

## rerere ##


!SLIDE code

## git config --global rerere.enabled 1 ##

!SLIDE code

	@@@ruby
	#! /usr/bin/env ruby

	def hello
	  puts 'hello world'
	end

!SLIDE commandline incremental

	$ git merge i18n-world
	Auto-merging hello.rb
	CONFLICT (content): Merge conflict in hello.rb
	Recorded preimage for 'hello.rb'
	Automatic merge failed; fix conflicts and then commit the result.

	$ git rerere status
	hello.rb

!SLIDE

<pre>
$ git rerere diff
--- a/hello.rb
+++ b/hello.rb
@@ -1,11 +1,11 @@
 #! /usr/bin/env ruby

 def hello
<span class="red">-<<<<<<<
-  puts 'hello mundo'
-=======</span>
<span class="green">+<<<<<<< HEAD</span>
   puts 'hola world'
<span class="red">->>>>>>></span>
<span class="green">+=======
+  puts 'hello mundo'
+>>>>>>> i18n-world</span>
 end
</pre>

!SLIDE commandline incremental

	$ git ls-files -u
	100644 39804c942a9c1f2c03dc7c5ebcd7f3e3a6b97519 1	hello.rb
	100644 a440db6e8d1fd76ad438a49025a9ad9ce746f581 2	hello.rb
	100644 54336ba847c3758ab604876419607e9443848474 3	hello.rb
	
	$ echo 'hola mundo' > hello.rb
	$ git add hello.rb
	
!SLIDE
<pre>
$ git rerere diff
--- a/hello.rb
+++ b/hello.rb
@@ -1,11 +1,7 @@
 #! /usr/bin/env ruby

 def hello
<span class="red">-<<<<<<<
-  puts 'hello mundo'
-=======
-  puts 'hola world'
->>>>>>></span>
<span class="green">+  puts 'hola mundo'</span>
 end
</pre>

!SLIDE code

	$ git commit
	Recorded resolution for 'hello.rb'.
	[master 68e16e5] Merge branch 'i18n'
	
!SLIDE commandline incremental

	$ git reset --hard HEAD^
	HEAD is now at ad63f15 i18n the hello

	$ git checkout i18n-world
	Switched to branch 'i18n-world'
	
	$ git rebase master
	First, rewinding head to replay your work on top of it...
	Applying: i18n one word
	Using index info to reconstruct a base tree...
	Falling back to patching base and 3-way merge...
	Auto-merging hello.rb
	CONFLICT (content): Merge conflict in hello.rb
	Resolved 'hello.rb' using previous resolution.
	Failed to merge in the changes.
	Patch failed at 0001 i18n one word
	
!SLIDE commandline incremental

	$ cat hello.rb
	#! /usr/bin/env ruby

	def hello
	  puts 'hola mundo'
	end
	
	$ git diff
	diff --cc hello.rb
	index a440db6,54336ba..0000000
	--- a/hello.rb
	+++ b/hello.rb
	@@@ -1,7 -1,7 +1,7 @@@
	  #! /usr/bin/env ruby

	  def hello
	-   puts 'hola world'
	 -  puts 'hello mundo'
	++  puts 'hola mundo'
	  end

!SLIDE commandline incremental

	$ git checkout --conflict=merge hello.rb
	$ cat hello.rb
	#! /usr/bin/env ruby

	def hello
	<<<<<<< ours
	  puts 'hola world'
	=======
	  puts 'hello mundo'
	>>>>>>> theirs
	end
	
	$ git rerere
	Resolved 'hello.rb' using previous resolution.
	$ cat hello.rb
	#! /usr/bin/env ruby

	def hello
	  puts 'hola mundo'
	end

	$ git add hello.rb
	$ git rebase --continue
	Applying: i18n one word
	
!SLIDE code

## git merge --rerere-autoupdate ##

!SLIDE code

## git config --global rerere.autoupdate 1 ##