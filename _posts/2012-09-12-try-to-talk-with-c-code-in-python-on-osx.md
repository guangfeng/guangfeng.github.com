---
layout: default
title: "尝试在OSX环境使用Python访问C代码"
category: 
tags: [lesson, python]
---
<div class="dl50">
<h4>一个简单的加法运算和字符串回显的实例</h4>

{% highlight python %}
>>> from ctypes import *
>>> clib = CDLL('test2.dylib')
>>> clib.calc(1,2,c_double(3))
6
>>> clib.words(c_char_p("hello"))
hello
"hello"
{% endhighlight %}



<h4>实现代码</h4>

{% highlight c %}

#include<stdio.h>

int calc(int x, int y, double z) {
  return x + y + z;
}

char* words(char *s) {
  printf("%s\n",s);
  return s;
}

int main () {
  return 0;
}
{% endhighlight %}


<h4>代码编译和连接</h4>
{% highlight sh %}

cc -fPIC -arch x86_64 -c test2.c

cc -arch x86_64 -dynamiclib -o test2.dylib test2.o 
{% endhighlight %}


