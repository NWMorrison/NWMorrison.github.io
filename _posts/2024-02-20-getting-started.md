---
title: Tip Calculator
author: morrison
date: 2024-02-20 20:55:00 +0800
categories: [Projects]
tags: [C++]
pin: true
img_path: '/posts/20180809'
---

## Program

Here is my program: [Tip Calculator](https://github.com/NWMorrison/Tip_Calculator_Final).
It is a fully functional tip calculator.

&lt;span style='color:#3f5fbf; '&gt;///-------------------------------------------------Tip-Calculator---------------------------------------------------///&lt;/span&gt;
&lt;span style='color:#3f5fbf; '&gt;/// This program is a fully functional tip calculator that will do the following: ///&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// 1). Accept a Subtotal Amount (Before tip adjustment)&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// 2). Accept a tip (Either as a percentage or a whole dollar amount)&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// 3). Print receipt to console with values for subtotal, tip percent, tip amount, and total.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// 4). Values must be fixed with a set-precision of 2 decimal places.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// 5). Calculate any missing values.&lt;/span&gt;
&lt;span style='color:#004a43; '&gt;#&lt;/span&gt;&lt;span style='color:#004a43; '&gt;include &lt;/span&gt;&lt;span style='color:#800000; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#40015a; '&gt;iostream&lt;/span&gt;&lt;span style='color:#800000; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#004a43; '&gt; &lt;/span&gt;&lt;span style='color:#696969; '&gt;// Input/Output to our console.&lt;/span&gt;
&lt;span style='color:#004a43; '&gt;#&lt;/span&gt;&lt;span style='color:#004a43; '&gt;include &lt;/span&gt;&lt;span style='color:#800000; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#40015a; '&gt;iomanip&lt;/span&gt;&lt;span style='color:#800000; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#004a43; '&gt; &lt;/span&gt;&lt;span style='color:#696969; '&gt;// Manipulation of our console.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;int&lt;/span&gt; &lt;span style='color:#400000; '&gt;main&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt;
&lt;span style='color:#800080; '&gt;{&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;int&lt;/span&gt; choice &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008c00; '&gt;0&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This allows for a controlled do/while loop to repeatedly run the tip-calculator.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\t&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\t&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\t&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Welcome To My Tip Calculator&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;This Program will take a subtotal amount input by the user and calculate the tip on that amount.&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;You may input either a percentage or an actual dollar amount that you would like to leave.&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;The Program will then provide a receipt with everything broken down in a neat format.&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;do&lt;/span&gt;
&lt;span style='color:#800080; '&gt;{&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;int&lt;/span&gt; option &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008c00; '&gt;0&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This allows for control of our conditional-if branch.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;double&lt;/span&gt; subTotal &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008000; '&gt;0.00&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This variable holds our initial subtotal value input by the user.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;double&lt;/span&gt; tip&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This variable holds our final tip amount which is completed on the back-end.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;double&lt;/span&gt; tip_Percent &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008000; '&gt;0.00&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This variable holds our tip percentage value. (User Input &amp;amp; Back-End).&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;double&lt;/span&gt; cash_Amount &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008000; '&gt;0.00&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This variable holds our cash amount input by the user.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;double&lt;/span&gt; final_Amount&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// This variable holds our final total amount which is completed on the back-end.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block asks for user input of our subtotal.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Please Enter The SubTotal ($00.00) For The Item You Have Purchased: &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cin&lt;/span&gt; &lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt; subTotal&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block sets up our conditional if-statement for user input of either a tip percentage or a dollar amount.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Would You Like To Enter The Tip Percentage (1) or An Actual Dollar Amount (2): &lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;1). Tip Percentage(%)&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;2). Dollar Amount($)&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Selection: &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cin&lt;/span&gt; &lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt; option&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;if&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;option &lt;span style='color:#808030; '&gt;=&lt;/span&gt;&lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008c00; '&gt;1&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#696969; '&gt;// Option 1: (Tip Percentage Calculation)&lt;/span&gt;
&lt;span style='color:#800080; '&gt;{&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block asks for the percentage amount for the tip that the user would like to leave.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Enter the Percentage (00.00)&lt;/span&gt;&lt;span style='color:#007997; '&gt;% A&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;mount You would like to leave: &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cin&lt;/span&gt; &lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt; tip_Percent&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This conversion takes that percentage, converts it down into a decimal number&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// We then multiply that value by our subtotal which will give us our final value of our tip.&lt;/span&gt;
tip &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;tip_Percent &lt;span style='color:#808030; '&gt;/&lt;/span&gt; &lt;span style='color:#008000; '&gt;100.00&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;*&lt;/span&gt; subTotal&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This conversion takes our final amount takes our subtotal and adds our tip.&lt;/span&gt;
final_Amount &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;subTotal &lt;span style='color:#808030; '&gt;+&lt;/span&gt; tip&lt;span style='color:#808030; '&gt;)&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block prints a receipt with set precision to "2" decimal places for every floating point value.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This allows for fluidity when we print out to console.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt;&lt;span style='color:#808030; '&gt;.&lt;/span&gt;precision&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;2&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Receipt:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Subtotal:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;6&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;fixed &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; subTotal &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Tip (&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; tip_Percent &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;%): &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; tip &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;22&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;--------&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Total:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;9&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; final_Amount &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800080; '&gt;}&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;else&lt;/span&gt; &lt;span style='color:#800000; font-weight:bold; '&gt;if&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;option &lt;span style='color:#808030; '&gt;=&lt;/span&gt;&lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008c00; '&gt;2&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#696969; '&gt;// Option 2 (Cash Amount Calculation)&lt;/span&gt;
&lt;span style='color:#800080; '&gt;{&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block asks the user for the cash amount that they would like to leave as a tip.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Enter The Cash Amount ($10.00, $20.00, $50.00) You Would Like To Leave: &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cin&lt;/span&gt; &lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt; cash_Amount&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This conversion takes our cash amount and converts it into a percentile.&lt;/span&gt;
tip_Percent &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;cash_Amount &lt;span style='color:#808030; '&gt;/&lt;/span&gt; subTotal&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;*&lt;/span&gt; &lt;span style='color:#008c00; '&gt;100&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This conversion takes our final amount takes our subtotal and adds our tip.&lt;/span&gt;
final_Amount &lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;subTotal &lt;span style='color:#808030; '&gt;+&lt;/span&gt; cash_Amount&lt;span style='color:#808030; '&gt;)&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This block prints a receipt with set precision to "2" decimal places for every floating point value.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// This allows for fluidity when we print out to console.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt;&lt;span style='color:#808030; '&gt;.&lt;/span&gt;precision&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;2&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Receipt:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Subtotal:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;7&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;fixed &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; subTotal &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Tip (&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; tip_Percent &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;%): &lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;3&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; cash_Amount &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;22&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;--------&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Total:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;setw&lt;/span&gt;&lt;span style='color:#808030; '&gt;(&lt;/span&gt;&lt;span style='color:#008c00; '&gt;10&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;$&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; final_Amount &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800080; '&gt;}&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// Minor error handling if user inputs anything but a 1 or a 2 as an integer input.&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;else&lt;/span&gt;
&lt;span style='color:#800080; '&gt;{&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Invalid Input. Please Run The Program Again.&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800080; '&gt;}&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// Prompts the user if they would like to run the program again.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Would you like to run the Tip-Calculator again? &lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;1). Yes: &lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;2.) No: &lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Selection:&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cin&lt;/span&gt; &lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&gt;&lt;/span&gt; choice&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800080; '&gt;}&lt;/span&gt; &lt;span style='color:#800000; font-weight:bold; '&gt;while&lt;/span&gt; &lt;span style='color:#808030; '&gt;(&lt;/span&gt;choice &lt;span style='color:#808030; '&gt;!&lt;/span&gt;&lt;span style='color:#808030; '&gt;=&lt;/span&gt; &lt;span style='color:#008c00; '&gt;2&lt;/span&gt;&lt;span style='color:#808030; '&gt;)&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt; &lt;span style='color:#696969; '&gt;// If our choice is 2 which is no, we exit our do/while loop.&lt;/span&gt;
&lt;span style='color:#696969; '&gt;// Prints out a goodbye message letting the user know the program has ended.&lt;/span&gt;
&lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;cout&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Thank You For Using The Tip Calculator&lt;/span&gt;&lt;span style='color:#0f69ff; '&gt;\n&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt;
&lt;span style='color:#800000; '&gt;"&lt;/span&gt;&lt;span style='color:#0000e6; '&gt;Have A Nice Day!&lt;/span&gt;&lt;span style='color:#800000; '&gt;"&lt;/span&gt; &lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt;&lt;span style='color:#808030; '&gt;&amp;lt;&lt;/span&gt; &lt;span style='color:#666616; '&gt;std&lt;/span&gt;&lt;span style='color:#800080; '&gt;::&lt;/span&gt;&lt;span style='color:#603000; '&gt;endl&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800000; font-weight:bold; '&gt;return&lt;/span&gt; &lt;span style='color:#008c00; '&gt;0&lt;/span&gt;&lt;span style='color:#800080; '&gt;;&lt;/span&gt;
&lt;span style='color:#800080; '&gt;}&lt;/span&gt;
&lt;!--Created using ToHTML.com on 2024-02-22 03:04:41 UTC --&gt;


## Installation

### Creating a New Site

There are two ways to create a new repository for this theme:

- [**Using the Chirpy Starter**](#option-1-using-the-chirpy-starter) - Easy to upgrade, isolates irrelevant project files so you can focus on writing.
- [**GitHub Fork**](#option-2-github-fork) - Convenient for custom development, but difficult to upgrade. Unless you are familiar with Jekyll and are determined to tweak or contribute to this project, this approach is not recommended.

#### Option 1. Using the Chirpy Starter

Sign in to GitHub and browse to [**Chirpy Starter**][starter], click the button <kbd>Use this template</kbd> > <kbd>Create a new repository</kbd>, and name the new repository `USERNAME.github.io`, where `USERNAME` represents your GitHub username.

#### Option 2. GitHub Fork

Sign in to GitHub to [fork **Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy/fork), and then rename it to `USERNAME.github.io` (`USERNAME` means your username).

Next, clone your site to local machine. In order to build JavaScript files later, we need to install [Node.js][nodejs], and then run the tool:

```console
$ bash tools/init
```

> If you don't want to deploy your site on GitHub Pages, append option `--no-gh` at the end of the above command.
{: .prompt-info }

The above command will:

1. Check out the code to the [latest tag][latest-tag] (to ensure the stability of your site: as the code for the default branch is under development).
2. Remove non-essential sample files and take care of GitHub-related files.
3. Build JavaScript files and export to `assets/js/dist/`{: .filepath }, then make them tracked by Git.
4. Automatically create a new commit to save the changes above.

### Installing Dependencies

Before running local server for the first time, go to the root directory of your site and run:

```console
$ bundle
```

## Usage

### Configuration

Update the variables of `_config.yml`{: .filepath} as needed. Some of them are typical options:

- `url`
- `avatar`
- `timezone`
- `lang`

### Social Contact Options

Social contact options are displayed at the bottom of the sidebar. You can turn on/off the specified contacts in file `_data/contact.yml`{: .filepath }.

### Customizing Stylesheet

If you need to customize the stylesheet, copy the theme's `assets/css/jekyll-theme-chirpy.scss`{: .filepath} to the same path on your Jekyll site, and then add the custom style at the end of it.

Starting with version `6.2.0`, if you want to overwrite the SASS variables defined in `_sass/addon/variables.scss`{: .filepath}, copy the main sass file `_sass/main.scss`{: .filepath} into the `_sass`{: .filepath} directory in your site's source, then create a new file `_sass/variables-hook.scss`{: .filepath} and assign new value.

### Customing Static Assets

Static assets configuration was introduced in version `5.1.0`. The CDN of the static assets is defined by file `_data/origin/cors.yml`{: .filepath }, and you can replace some of them according to the network conditions in the region where your website is published.

Also, if you'd like to self-host the static assets, please refer to the [_chirpy-static-assets_](https://github.com/cotes2020/chirpy-static-assets#readme).

### Running Local Server

You may want to preview the site contents before publishing, so just run it by:

```console
$ bundle exec jekyll s
```

After a few seconds, the local service will be published at _<http://127.0.0.1:4000>_.

## Deployment

Before the deployment begins, check out the file `_config.yml`{: .filepath} and make sure the `url` is configured correctly. Furthermore, if you prefer the [**project site**](https://help.github.com/en/github/working-with-github-pages/about-github-pages#types-of-github-pages-sites) and don't use a custom domain, or you want to visit your website with a base URL on a web server other than **GitHub Pages**, remember to change the `baseurl` to your project name that starts with a slash, e.g, `/project-name`.

Now you can choose _ONE_ of the following methods to deploy your Jekyll site.

### Deploy by Using GitHub Actions

There are a few things to get ready for.

- If you're on the GitHub Free plan, keep your site repository public.
- If you have committed `Gemfile.lock`{: .filepath} to the repository, and your local machine is not running Linux, go to the root of your site and update the platform list of the lock-file:

  ```console
  $ bundle lock --add-platform x86_64-linux
  ```

Next, configure the _Pages_ service.

1. Browse to your repository on GitHub. Select the tab _Settings_, then click _Pages_ in the left navigation bar. Then, in the **Source** section (under _Build and deployment_), select [**GitHub Actions**][pages-workflow-src] from the dropdown menu.  
   ![Build source](pages-source-light.png){: .light .border .normal w='375' h='140' }
   ![Build source](pages-source-dark.png){: .dark .normal w='375' h='140' }

2. Push any commits to GitHub to trigger the _Actions_ workflow. In the _Actions_ tab of your repository, you should see the workflow _Build and Deploy_ running. Once the build is complete and successful, the site will be deployed automatically.

At this point, you can go to the URL indicated by GitHub to access your site.

### Manually Build and Deploy

On self-hosted servers, you cannot enjoy the convenience of **GitHub Actions**. Therefore, you should build the site on your local machine and then upload the site files to the server.

Go to the root of the source project, and build your site as follows:

```console
$ JEKYLL_ENV=production bundle exec jekyll b
```

Unless you specified the output path, the generated site files will be placed in folder `_site`{: .filepath} of the project's root directory. Now you should upload those files to the target server.

[nodejs]: https://nodejs.org/
[starter]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[latest-tag]: https://github.com/cotes2020/jekyll-theme-chirpy/tags
