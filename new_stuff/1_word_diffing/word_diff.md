!SLIDE

# Word Diffing #

!SLIDE commandline

<pre>
<strong>$ git diff</strong>
<span class="grey">diff --git a/timer.js b/timer.js
index 4595967..8ba61dd 100644
--- a/timer.js
+++ b/timer.js</span>
<span class="blue">@@ -2,7 +2,7 @@</span> var timerSetUp = false;
 var timerRunning = false;
 var intervalRunning = false;
 var seconds = 0;
<span class="red">-var totalMinutes = 45;</span>
<span class="green">+var totalMinutes = 120;</span>
</pre>

!SLIDE commandline

<pre>
<strong>$ git diff --word-diff</strong>
<span class="grey">diff --git a/timer.js b/timer.js
index 4595967..8ba61dd 100644
--- a/timer.js
+++ b/timer.js</span>
<span class="blue">@@ -2,7 +2,7 @@</span> var timerSetUp = false;
var timerRunning = false;
var intervalRunning = false;
var seconds = 0;
var totalMinutes = <span class="red">[-45;-]</span><span class="green">{+120;+}</span>
</pre>

