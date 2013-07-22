---
layout: post
title: "Hadoop 启动出错解决"
description: "Hadoop issue: jobtracker.info could only be replicated to 0 nodes, instead of 1  启动出错解决"
category: "Technique"
tags:
- Hadoop
---
{% include JB/setup %} 

> ### "Hadoop issue: jobtracker.info could only be replicated to 0 nodes, instead of 1"

1.  首先在格式化namenode之前 (`hadoop namenode –format`)，注意先 `stop-all.sh` 

2. Instead of using `hadoop/bin/start-all.sh`, run each of the commands separately:   

		./bin/hadoop-daemon.sh start namenode    
		./bin/hadoop-daemon.sh start jobtracker    
		./bin/hadoop-daemon.sh start tasktracker  
		./bin/hadoop-daemon.sh start datanode

There still may be some intermediate issue with dfs dir. Try deleting the dfs dir and cleanup everything of the form `/tmp/hadoop*`


Then do a `hadoop namenode -format`.

<font color="#ff0000">The reason is that datanode is loaded very slowly. </font>  

If start map-red before datanode loaded, everything goes wrong and jobtracker gives 
> "jobtracker.info could only be replicated to 0 nodes, instead of" error.    

So we should wait for datanode loading.
