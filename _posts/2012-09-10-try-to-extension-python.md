---
layout: default
title: "尝试编写Python的C扩展模块"
description: ""
tags: [lesson, python]
---
<div class="dl50">

<h4>一个简单的乘法运算的实例</h4>

{% highlight python %}

>>> hello.calc(1,2)
hello.calc(1,2)
2
>>> hello.calc(2000,39)
hello.calc(2000,39)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
hello.error: result has bigger than 5000!
{% endhighlight %}


<h4>实现代码</h4>

{% highlight c %}

/* This is a demo ext for python */
#include "Python.h"

static PyObject *HelloError;

int calc(int x, int y) {
  return x * y;
}

static PyObject * hello_calc(PyObject *self, PyObject *args) {
  const int x;
  const int y;
  int res;
  
  if(!PyArg_ParseTuple(args,"ii",&x,&y)) 
    return NULL;

  res = calc(x,y);
  if (res > 5000) {
    PyErr_SetString(HelloError,"result has bigger than 5000!");
    return NULL;
  }
  return Py_BuildValue("i", res);
}

static PyMethodDef hello_methods[] = {
  {"calc", hello_calc, METH_VARARGS, "it's a demo funtcion"},
  {NULL,NULL,0,NULL}
};

PyMODINIT_FUNC inithello () {
  PyObject *m;
  m = Py_InitModule("hello", hello_methods);
  HelloError = PyErr_NewException("hello.error",NULL,NULL);
  Py_INCREF(HelloError);
  PyModule_AddObject(m,"error",HelloError);
}
{% endhighlight %}

</div>