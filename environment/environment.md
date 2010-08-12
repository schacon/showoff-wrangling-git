!SLIDE

# Environment Variables #

!SLIDE 

## moving around your git pieces ##

!SLIDE bullets incremental

* git directory
* index file
* working directory

!SLIDE code

# GIT_DIR #

!SLIDE commandline incremental

	$ mv .git /opt/repo.git

	$ git --git-dir=/opt/repo.git log

	$ export GIT_DIR=/opt/repo.git
	$ git log

!SLIDE code

# GIT_INDEX_FILE #

!SLIDE commandline incremental

	$ git status -s
	 M README
	 M kidgloves.rb
	
	$ git add kidgloves.rb 
	
	$ git status -s
	 M README
	S  kidgloves.rb

!SLIDE commandline incremental 

	$ export GIT_INDEX_FILE=/tmp/index
	$ git read-tree HEAD
	$ git add README 
	
	$ git status -s
	S  README
	 M kidgloves.rb

!SLIDE commandline incremental 

	$ unset GIT_INDEX_FILE
	
	$ git status -s
	 M README
	S  kidgloves.rb
	
	$ export GIT_INDEX_FILE=/tmp/index
	
	$ git status -s
	S  README
	 M kidgloves.rb

!SLIDE code

# GIT_WORK_TREE #

!SLIDE commandline incremental

	$ git status -s
	 M README
	S  kidgloves.rb

	$ export GIT_DIR=$(pwd)/.git
	$ export GIT_WORK_TREE=$(pwd)

	$ cd /tmp
	$ git status -s
	 M README
	S  kidgloves.rb

!SLIDE

# Overwriting your credentials #

!SLIDE code

# GIT_AUTHOR_NAME #
# GIT_AUTHOR_EMAIL #

!SLIDE

# Debugging Git #

!SLIDE code

# GIT_MERGE_VERBOSITY #

!SLIDE commandline incremental

	$ git merge 06ca03a
	Auto-merging kidgloves.rb
	Merge made by recursive.
	 kidgloves.rb |    3 +--
	 1 files changed, 1 insertions(+), 2 deletions(-)

	$ git reset --hard 096880d
	HEAD is now at 096880d use idiomatic rack :Host and :Port options

	$ GIT_MERGE_VERBOSITY=5 git merge 06ca03a
	Merging:
	096880d use idiomatic rack :Host and :Port options
	virtual 06ca03a
	found 1 common ancestor(s):
	66d35ee wasnt setting the header vars properly
	Auto-merging kidgloves.rb
	Merge made by recursive.
	 kidgloves.rb |    3 +--
	 1 files changed, 1 insertions(+), 2 deletions(-)

!SLIDE code

# GIT_TRACE #

!SLIDE commandline incremental

	$ GIT_TRACE=1 git lol
	trace: exec: 'git-lol'
	trace: run_command: 'git-lol'
	trace: alias expansion: lol => 'log' '--oneline' '--graph' '--decorate'
	trace: run_command: 'less'
	trace: exec: 'less'
	trace: built-in: git 'log' '--oneline' '--graph' '--decorate'
	*   b896af7 (HEAD, test) Merge commit '06ca03a' into test
	|\  
	| * 06ca03a (rtomayko/headernames) no need to delete these header names now
	| * 8cebd9f CONTENT_TYPE and CONTENT_LENGTH are not prefixed with HTTP_
	| * 8aff92c request header env keys get HTTP_ prefix
	* | 096880d (rtomayko/bindopts) use idiomatic rack :Host and :Port options
	* | 801e40a log to stderr instead of stdout
	* | 7295993 take listen host/port
	|/  



!SLIDE code

# GIT_CURL_VERBOSE #

!SLIDE commandline

	$ GIT_CURL_VERBOSE=1 git clone http://github.com/schacon/showoff.git
	Cloning into showoff...
	* Couldn't find host github.com in the .netrc file; using defaults
	* About to connect() to github.com port 80 (#0)
	*   Trying 207.97.227.239... * Connected to github.com (207.97.227.239) port 80 (#0)
	> GET /schacon/showoff.git/info/refs?service=git-upload-pack HTTP/1.1
	User-Agent: git/1.7.2.1
	Host: github.com
	Accept: */*
	Pragma: no-cache

	< HTTP/1.1 200 OK
	< Server: nginx/0.7.67
	< Date: Wed, 11 Aug 2010 20:21:35 GMT
	< Content-Type: application/x-git-upload-pack-advertisement
	< Connection: keep-alive
	< Status: 200 OK
	< Pragma: no-cache
	< Content-Length: 1316
	< Expires: Fri, 01 Jan 1980 00:00:00 GMT
	< Cache-Control: no-cache, max-age=0, must-revalidate
	< 
	* Expire cleared
	* Connection #0 to host github.com left intact
	* Couldn't find host github.com in the .netrc file; using defaults
	* About to connect() to github.com port 80 (#0)
	*   Trying 207.97.227.239... * connected
	* Connected to github.com (207.97.227.239) port 80 (#0)
	> POST /schacon/showoff.git/git-upload-pack HTTP/1.1
	User-Agent: git/1.7.2.1
	Host: github.com
	Accept-Encoding: deflate, gzip
	Content-Type: application/x-git-upload-pack-request
	Accept: application/x-git-upload-pack-result
	Content-Length: 866

	< HTTP/1.1 200 OK
	< Server: nginx/0.7.67
	< Date: Wed, 11 Aug 2010 20:21:35 GMT
	< Content-Type: application/x-git-upload-pack-result
	< Transfer-Encoding: chunked
	< Connection: keep-alive
	< Status: 200 OK
	< 
	remote: Counting objects: 1364, done.
	remote: Compressing objects: 100% (843/843), done.
	remote: Total 1364 (delta 756), reused 906 (delta 468)
	* Connection #0 to host github.com left intact
	Receiving objects: 100% (1364/1364), 342.25 KiB, done.
	Resolving deltas: 100% (756/756), done.