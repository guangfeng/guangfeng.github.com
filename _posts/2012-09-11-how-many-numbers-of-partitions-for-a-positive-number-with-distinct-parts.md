---
layout: default
title: "任意自然数可以拆分成多少组不重复自然数之和?"
category: 
tags: [lesson,math]
---
<div class="dl50">
Question: 给定一个自然数N,将其拆分成多个不重复的自然数之和。对这样的拆分共有多少组？<br/>
<br/><br/>


Example:<br/>
<p>
<a href="http://www.codecogs.com/eqnedit.php?latex=6 = 1 @plus; 5 = 2 @plus; 4 = 1 @plus; 2 @plus; 3" target="_blank"><img src="http://latex.codecogs.com/gif.latex?6 = 1 + 5 = 2 + 4 = 1 + 2 + 3" title="6 = 1 + 5 = 2 + 4 = 1 + 2 + 3" /></a><br/>
</p>
因此
<p>
<a href="http://www.codecogs.com/eqnedit.php?latex=f(6) = 3" target="_blank"><img src="http://latex.codecogs.com/gif.latex?f(6) = 3" title="f(6) = 3" /></a>
<br/></p>
<br/><br/>
Solution: 将问题转换成在<a href="http://www.codecogs.com/eqnedit.php?latex=1,2,3.....N-1" target="_blank"><img src="http://latex.codecogs.com/gif.latex?1,2,3.....N-1" title="1,2,3.....N-1" /></a>中找到和为N的组合。<br/>

记为:<p><a href="http://www.codecogs.com/eqnedit.php?latex=P\binom{n-1}{n}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P\binom{n-1}{n}" title="P\binom{n-1}{n}" /></a></p>
<br/>
<br/>



对于任一组划分，必然存在两种情况:
<p>
*1. n-1包含在划分中
<br/>
<br/>
*2. n-1不包含在划分中
</p>
<br/>
<p>



对于情况1，实际上是需要在1，2，3....n-2种找到和为1的自然数组合.根据前文的记号，可以有组<a href="http://www.codecogs.com/eqnedit.php?latex=P\binom{n-2}{1}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P\binom{n-2}{1}" title="P\binom{n-2}{1}" /></a>情况.<br/></p><br/><br/>




<p>
对于情况2，实际上是需要在1，2，3....n-2种找到和为n的自然数组合.根据前文的记号，可以有组<a href="http://www.codecogs.com/eqnedit.php?latex=P\binom{n-2}{n}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P\binom{n-2}{n}" title="P\binom{n-2}{n}" /></a>情况.<br/></p>
<br/><br/>


由此分析，我们得到:<p><a href="http://www.codecogs.com/eqnedit.php?latex=P\binom{n-1}{n} = P\binom{n-2}{1} @plus; P\binom{n-2}{n}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P\binom{n-1}{n} = P\binom{n-2}{1} + P\binom{n-2}{n}" title="P\binom{n-1}{n} = P\binom{n-2}{1} + P\binom{n-2}{n}" /></a></p>
<br/><br/>




<br/>
<p>
好吧，我们带入6来检测下:
<a href="http://www.codecogs.com/eqnedit.php?latex=P\binom{5}{6} = P\binom{4}{1} @plus; P\binom{4}{6} = 1 @plus; P\binom{3}{2} @plus; P\binom{3}{6} = 1 @plus; 1 @plus; P\binom{2}{3} @plus; P\binom{2}{6} = 1 @plus; 1 @plus; 1 @plus; 0 = 3" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P\binom{5}{6} = P\binom{4}{1} + P\binom{4}{6} = 1 + P\binom{3}{2} + P\binom{3}{6} = 1 + 1 + P\binom{2}{3} + P\binom{2}{6} = 1 + 1 + 1 + 0 = 3" title="P\binom{5}{6} = P\binom{4}{1} + P\binom{4}{6} = 1 + P\binom{3}{2} + P\binom{3}{6} = 1 + 1 + P\binom{2}{3} + C\binom{2}{6} = 1 + 1 + 1 + 0 = 3" /></a></p>



</div>