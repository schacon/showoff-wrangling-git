!SLIDE subsection

# Smart HTTP Transport #

!SLIDE smaller

@@@ apache
	SetEnv GIT_PROJECT_ROOT /var/www/git
	SetEnv GIT_HTTP_EXPORT_ALL
	ScriptAlias /git/ /usr/libexec/git-core/git-http-backend/
@@@

!SLIDE command

# Grack #

### http://github.com/schacon/grack ###

!SLIDE commandline incremental

$ (edit config.ru to set git project path)
$ rackup --host 127.0.0.1 -p 8080 config.ru
$ git clone http://127.0.0.1:8080/schacon/grit.git