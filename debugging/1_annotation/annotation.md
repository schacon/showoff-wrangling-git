!SLIDE

# git blame #

## ie: "what dumbass did this? oh yeah, it was me..." ##

!SLIDE commandline incremental small

	$ git blame daemon.c
	979e32fa (Randal L. Schwartz      2005-10-25 16:29:09 -0700    1) #include "cache.h"
	85023577 (Junio C Hamano          2006-12-19 14:34:12 -0800    2) #include "pkt-line.h"
	77cb17e9 (Michal Ostrowski        2006-01-10 21:12:17 -0500    3) #include "exec_cmd.h"
	49ba83fb (Jon Loeliger            2006-09-19 20:31:51 -0500    4) #include "interpolate.h"
	f8ff0c06 (Petr Baudis             2005-09-22 11:25:28 +0200    5) 
	85023577 (Junio C Hamano          2006-12-19 14:34:12 -0800    6) #include <syslog.h>
	85023577 (Junio C Hamano          2006-12-19 14:34:12 -0800    7) 
	695dffe2 (Johannes Schindelin     2006-09-28 12:00:35 +0200    8) #ifndef HOST_NAME_MAX
	695dffe2 (Johannes Schindelin     2006-09-28 12:00:35 +0200    9) #define HOST_NAME_MAX 256
	695dffe2 (Johannes Schindelin     2006-09-28 12:00:35 +0200   10) #endif
	695dffe2 (Johannes Schindelin     2006-09-28 12:00:35 +0200   11) 
	415e7b87 (Patrick Welche          2007-10-18 18:17:39 +0100   12) #ifndef NI_MAXSERV
	415e7b87 (Patrick Welche          2007-10-18 18:17:39 +0100   13) #define NI_MAXSERV 32
	415e7b87 (Patrick Welche          2007-10-18 18:17:39 +0100   14) #endif
	415e7b87 (Patrick Welche          2007-10-18 18:17:39 +0100   15) 
	9048fe1c (Petr Baudis             2005-09-24 16:13:01 +0200   16) static int log_syslog;
	f8ff0c06 (Petr Baudis             2005-09-22 11:25:28 +0200   17) static int verbose;
	1955fabf (Mark Wooding            2006-02-03 20:27:04 +0000   18) static int reuseaddr;
	f8ff0c06 (Petr Baudis             2005-09-22 11:25:28 +0200   19) 
	960deccb (H. Peter Anvin          2005-10-19 14:27:01 -0700   20) static const char daemon_usage[] =
	1b1dd23f (Stephan Beyer           2008-07-13 15:36:15 +0200   21) "git daemon [--verbose] [--syslog] [
	3bd62c21 (Stephen R. van den Berg 2008-08-14 20:02:20 +0200   22) "           [--timeout=n] [--init-ti
	3bd62c21 (Stephen R. van den Berg 2008-08-14 20:02:20 +0200   23) "           [--strict-paths] [--base
	73a7a656 (Jens Axboe              2007-07-27 14:00:29 -0700   24) "           [--user-path | --user-pa
	49ba83fb (Jon Loeliger            2006-09-19 20:31:51 -0500   25) "           [--interpolated-path=pat
	678dac6b (Tilman Sauerbeck        2006-08-22 19:37:41 +0200   26) "           [--reuseaddr] [--detach]
	d9edcbd6 (Junio C Hamano          2006-09-07 01:40:04 -0700   27) "           [--[enable|disable|allow
	dd467629 (Jon Loeliger            2006-09-26 09:47:43 -0500   28) "           [--inetd | [--listen=hos

!SLIDE commandline incremental small

	$ git blame -C GITPackUpload.m
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  12) 
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  13) #define PACK_SIGN
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  14) #define PACK_VERS
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  15) 
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  16) @implementation G
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  17) 
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  18) @synthesize gitRe
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  19) @synthesize needR
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  20) @synthesize gitSo
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  21) @synthesize refDi
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  22) 
	a2cbabf5 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-25 22:29:39 +0100  23) - (id) initWithGi
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  24) {
	a2cbabf5 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-25 22:29:39 +0100  25)        gitRepo = 
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  26)        needRefs =
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  27)        gitSocket 
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  28)        return sel
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  29) }
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  30) 
	ad11ac80 Source/Network/GITPackUpload.m    (Scott Chacon  2009-03-24 18:32:50 +0100  31) - (bool) uploadPa
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  32) {
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  33)        NSLog(@"up
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  34)        NSString *
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  35)        NSArray *t
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  36)        
	56ef2caf Source/Network/GITServerHandler.m (Scott Chacon  2009-01-05 21:44:26 -0800  37)        refDict = 
	f344f58d Source/Network/GITServerHandler.m (Scott Chacon  2009-01-04 18:59:04 -0800  38)        
