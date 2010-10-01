!SLIDE

# Smart HTTP Transport #

!SLIDE center

## "Dumb" HTTP ##

![](img/smarthttp1.png)

## "Smart" HTTP ##

![](img/smarthttp2.png)


!SLIDE smaller

	SetEnv GIT_PROJECT_ROOT /var/www/git
	SetEnv GIT_HTTP_EXPORT_ALL
	ScriptAlias /git/ /usr/libexec/git-core/git-http-backend/

