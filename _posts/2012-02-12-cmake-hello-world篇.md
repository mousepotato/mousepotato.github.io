---
layout: post
title: CMake Hello World篇
tags:
- CMake
- Technique
status: publish
type: post
published: true
meta:
  views: '1405'
---
<p>CMake 全程 Cross-platform Make，一个非常好的开源编译系统。因为它的跨平台特性，所以可以很方便的生产Windows下的VS项目文件，Linux下的makefile，以及Mac X下的XCode项目。下面简单介绍如何使用CMake在Linux下编译Hello World。</p> <p>&nbsp;</p> <h2>一、目录结构</h2> <p>新建文件目录cmake_example，里面的目录结构如下。</p> <p>&nbsp;</p> <p><a href="/assets/uploads/2012/02/image.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="/assets/uploads/2012/02/image_thumb.png" width="255" height="169"></a></p> <p>&nbsp;</p> <p>&nbsp;</p> <h2>二、编写Hello World代码。</h2> <p>&nbsp;</p> <p><font color="#ff0000">hello.cc</font></p> <p>&nbsp;</p><pre class="prettyprint">#include "hello.h"
#include &lt;iostream&gt;

using namespace std;

void Hello::Print(){
	cout&lt;&lt; "Hello World!" &lt;&lt;endl;
}
</pre>
<p>&nbsp;</p>
<p><font color="#ff0000">hello.h</font></p>
<p>&nbsp;</p><pre class="prettyprint">#ifndef _hello_h
#define _hello_h

class Hello{
	public:
		void Print();
};
#endif
</pre>
<p>&nbsp;</p>
<p><font color="#ff0000">test.cc</font></p>
<p><font color="#ff0000"></font>&nbsp;</p><pre class="prettyprint">#include &lt;iostream&gt;
#include "hello.h"

int main(){
	Hello().Print();
	return 0;
}
</pre>
<p><font color="#ff0000"></font>&nbsp;</p>
<h2>三、编写CMakeLists.txt文件</h2>
<p><font color="#ff0000">Top-level CMakeLists.txt</font></p><pre class="prettyprint">&nbsp;</pre><pre class="prettyprint"># Top-Level CmakeLists.txt
PROJECT( HELLO )

ADD_SUBDIRECTORY( Hello )
ADD_SUBDIRECTORY( Test )
</pre>
<p><font color="#ff0000">Hello目录下CMakeLists.txt</font></p>
<p><font color="#ff0000"></font>&nbsp;</p><pre class="prettyprint">#makeLists.txt in Hello dir
# Adds a library called Hello (libHello.a under Linux) from the source </pre><pre class="prettyprint"># file hello.cc
ADD_LIBRARY( Hello hello )</pre>
<p><font color="#ff0000"></font>&nbsp;</p>
<p><font color="#ff0000">Test目录下CMakeLists.txt</font></p>
<p><font color="#ff0000"></font>&nbsp;</p><pre class="prettyprint"># CmakeLists.txt in Test dir
# Make sure the compiler can find include files from our Hello library.
INCLUDE_DIRECTORIES(${HELLO_SOURCE_DIR}/Hello)
</pre><pre class="prettyprint"># Add binary called "helloWorld" that is built from the source file "test.cc".
# The extension is automatically found.
ADD_EXECUTABLE(helloWorld test)
</pre><pre class="prettyprint"># Link the executable to the Hello library.
TARGET_LINK_LIBRARIES(helloWorld Hello)</pre>
<p><font color="#ff0000"></font>&nbsp;</p>
<h2>四、编译运行</h2>
<p>在根目录下输入</p><pre class="prettyprint">cmake .</pre>

<p>&nbsp;</p>
<p>然后在Test目录输入</p>
<p>./helloWorld</p>
<p>&nbsp;</p>
<p>具体文件可以<a href="http://anotherbug.com/disk/cmake_example.zip" target="_blank">点此下载cmake_example.zip</a></p>
