--- 
date: 2006-09-23
layout: post
title: Problem with List and TypeConverter
published: true
---
<p>I am having a bit of difficulty with TypeConverters and Generic Lists and I was hoping that I could get a bit of advice. </p> <p>I have a type converter that is used to create the constructor code for my component. (It is an XNA a Game Component, but I don't think that that has anything to do with the problem because it appears on a Winform) inside another component. </p> <p>For instance I have the following: </p> <p> </p> <div class="wlWriterSmartContent" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px;">
<p />

<div>
<br />Code highlighting produced by Actipro CodeHighlighter (freeware)<br /><a href="http://www.CodeHighlighter.com/">http://www.CodeHighlighter.com/</a><p />--><span style="color: #0000FF;">public</span><span style="color: #000000;"> </span><span style="color: #0000FF;">class</span><span style="color: #000000;"> A{<br /> </span><span style="color: #0000FF;">private</span><span style="color: #000000;"> </span><span style="color: #0000FF;">string</span><span style="color: #000000;"> s;<br /> </span><span style="color: #0000FF;">public</span><span style="color: #000000;"> </span><span style="color: #0000FF;">string</span><span style="color: #000000;"> SProp <br /> {<br />   </span><span style="color: #0000FF;">get</span><span style="color: #000000;">{ s </span><span style="color: #000000;">=</span><span style="color: #000000;"> value;}<br />   </span><span style="color: #0000FF;">set</span><span style="color: #000000;"> {</span><span style="color: #0000FF;">return</span><span style="color: #000000;"> s;}<br /> }<p /> </span><span style="color: #0000FF;">public</span><span style="color: #000000;"> A()<br /> {<br />   s </span><span style="color: #000000;">=</span><span style="color: #000000;"> </span><span style="color: #000000;">""</span><span style="color: #000000;">;<br /> }<br /> </span><span style="color: #0000FF;">public</span><span style="color: #000000;"> A(</span><span style="color: #0000FF;">string</span><span style="color: #000000;"> inS)<br /> {<br />   s </span><span style="color: #000000;">=</span><span style="color: #000000;"> inS;<br /> }<br />}<br /></span>
</div>
</div><br /><p>By itself, when class A is an object on a form (or in my XNA Component) the TypeConverter code works fine, the property grid on the desinger is fine, if I debug the ConvertTo on the type converter I see that the variable s is all set up okay on the object. </p><br /><p>However if on my form, I have a List&lt;A&gt;, the type converter works to an extent, as in it will add code to the perform the List.Add(new A("")), however the constructor with the parameter is not being called, instead the parameterless constructor is being called.  </p><br /><p>Obviously, if the input to ConvertTo on the type converter is not set up, then my type converter won't work or display the values the user has put in.  This only occurs when my object is in a Generic List.</p><br /><p>Can anyone suggest anything to look at?</p><br /><p>tags: <a href="http://www.kinlan.co.uk/tag/question" rel="tag">question</a>, <a href="http://www.kinlan.co.uk/tag/c#" rel="tag">c#</a>, <a href="http://www.kinlan.co.uk/tag/.net" rel="tag">.net</a>, <a href="http://www.kinlan.co.uk/tag/generics" rel="tag">generics</a>, <a href="http://www.kinlan.co.uk/tag/typeconverter" rel="tag">typeconverter</a></p><div class="blogger-post-footer"><img class="posterous_download_image" src="https://blogger.googleusercontent.com/tracker/8109338-115904496365458978?l=www.kinlan.co.uk%2Findex.html" height="1" alt="" width="1" /></div>