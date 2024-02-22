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

<pre class="hljs" style="display: block; overflow-x: auto; padding: 0.5em; background: rgb(240, 240, 240); color: rgb(68, 68, 68);"><span class="hljs-comment" style="color: rgb(136, 136, 136);">///-------------------------------------------------Tip-Calculator---------------------------------------------------///</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">///                  This program is a fully functional tip calculator that will do the following:                   ///</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">// 1). Accept a Subtotal Amount (Before tip adjustment)</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">// 2). Accept a tip (Either as a percentage or a whole dollar amount)</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">// 3). Print receipt to console with values for subtotal, tip percent, tip amount, and total.</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">// 4). Values must be fixed with a set-precision of 2 decimal places.</span>
<span class="hljs-comment" style="color: rgb(136, 136, 136);">// 5). Calculate any missing values.</span>


<span class="hljs-meta" style="color: rgb(31, 113, 153);">#<span class="hljs-meta-keyword" style="font-weight: 400;">include</span> <span class="hljs-meta-string" style="color: rgb(77, 153, 191);">&lt;iostream&gt;</span> <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Input/Output to our console.</span></span>
<span class="hljs-meta" style="color: rgb(31, 113, 153);">#<span class="hljs-meta-keyword" style="font-weight: 400;">include</span> <span class="hljs-meta-string" style="color: rgb(77, 153, 191);">&lt;iomanip&gt;</span>  <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Manipulation of our console.</span></span>


<span class="hljs-function"><span class="hljs-keyword" style="font-weight: 400;">int</span> <span class="hljs-title" style="color: rgb(136, 0, 0); font-weight: 400;">main</span><span class="hljs-params">()</span>
</span>{

    <span class="hljs-keyword" style="font-weight: 400;">int</span> choice = <span class="hljs-number" style="color: rgb(136, 0, 0);">0</span>;                 <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This allows for a controlled do/while loop to repeatedly run the tip-calculator.</span>

    <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"\t\t\tWelcome To My Tip Calculator\n"</span>
                 <span class="hljs-string" style="color: rgb(136, 0, 0);">"\nThis Program will take a subtotal amount input by the user and calculate the tip on that amount.\n"</span>
                 <span class="hljs-string" style="color: rgb(136, 0, 0);">"You may input either a percentage or an actual dollar amount that you would like to leave.\n"</span>
                 <span class="hljs-string" style="color: rgb(136, 0, 0);">"The Program will then provide a receipt with everything broken down in a neat format."</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;

    <span class="hljs-keyword" style="font-weight: 400;">do</span>
    {
        <span class="hljs-keyword" style="font-weight: 400;">int</span> option = <span class="hljs-number" style="color: rgb(136, 0, 0);">0</span>;             <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This allows for control of our conditional-if branch.</span>


        <span class="hljs-keyword" style="font-weight: 400;">double</span> subTotal = <span class="hljs-number" style="color: rgb(136, 0, 0);">0.00</span>;     <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This variable holds our initial subtotal value input by the user.</span>
        <span class="hljs-keyword" style="font-weight: 400;">double</span> tip;                 <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This variable holds our final tip amount which is completed on the back-end.</span>
        <span class="hljs-keyword" style="font-weight: 400;">double</span> tip_Percent = <span class="hljs-number" style="color: rgb(136, 0, 0);">0.00</span>;  <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This variable holds our tip percentage value. (User Input &amp; Back-End).</span>

        <span class="hljs-keyword" style="font-weight: 400;">double</span> cash_Amount = <span class="hljs-number" style="color: rgb(136, 0, 0);">0.00</span>;  <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This variable holds our cash amount input by the user.</span>
        <span class="hljs-keyword" style="font-weight: 400;">double</span> final_Amount;        <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This variable holds our final total amount which is completed on the back-end.</span>


        <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block asks for user input of our subtotal.</span>
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Please Enter The SubTotal ($00.00) For The Item You Have Purchased: "</span>;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cin</span> &gt;&gt; subTotal;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;


        <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block sets up our conditional if-statement for user input of either a tip percentage or a dollar amount.</span>
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Would You Like To Enter The Tip Percentage (1) or An Actual Dollar Amount (2): \n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"1). Tip Percentage(%)\n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"2). Dollar Amount($)\n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"Selection: "</span>;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cin</span> &gt;&gt; option;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;



        <span class="hljs-keyword" style="font-weight: 400;">if</span> (option == <span class="hljs-number" style="color: rgb(136, 0, 0);">1</span>) <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Option 1: (Tip Percentage Calculation)</span>
        {
            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block asks for the percentage amount for the tip that the user would like to leave.</span>
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Enter the Percentage (00.00)% Amount You would like to leave: "</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cin</span> &gt;&gt; tip_Percent;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;


            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This conversion takes that percentage, converts it down into a decimal number</span>
            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// We then multiply that value by our subtotal which will give us our final value of our tip.</span>
            tip = (tip_Percent / <span class="hljs-number" style="color: rgb(136, 0, 0);">100.00</span>) * subTotal;


            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This conversion takes our final amount takes our subtotal and adds our tip.</span>
            final_Amount = (subTotal + tip);



            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block prints a receipt with set precision to "2" decimal places for every floating point value.</span>
            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This allows for fluidity when we print out to console.</span>
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span>.precision(<span class="hljs-number" style="color: rgb(136, 0, 0);">2</span>);
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Receipt:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Subtotal:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">6</span>) &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::fixed &lt;&lt; subTotal &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Tip ("</span> &lt;&lt; tip_Percent &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"%): "</span>  &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span>  &lt;&lt; tip &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">22</span>) &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"--------"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Total:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">9</span>) &lt;&lt;  <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span> &lt;&lt; final_Amount &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
        }


        <span class="hljs-keyword" style="font-weight: 400;">else</span> <span class="hljs-keyword" style="font-weight: 400;">if</span> (option == <span class="hljs-number" style="color: rgb(136, 0, 0);">2</span>) <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Option 2 (Cash Amount Calculation)</span>
        {
            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block asks the user for the cash amount that they would like to leave as a tip.</span>
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Enter The Cash Amount ($10.00, $20.00, $50.00) You Would Like To Leave:  "</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cin</span> &gt;&gt; cash_Amount;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;


            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This conversion takes our cash amount and converts it into a percentile.</span>
            tip_Percent = (cash_Amount / subTotal) * <span class="hljs-number" style="color: rgb(136, 0, 0);">100</span>;

            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This conversion takes our final amount takes our subtotal and adds our tip.</span>
            final_Amount = (subTotal + cash_Amount);


            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This block prints a receipt with set precision to "2" decimal places for every floating point value.</span>
            <span class="hljs-comment" style="color: rgb(136, 136, 136);">// This allows for fluidity when we print out to console.</span>
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span>.precision(<span class="hljs-number" style="color: rgb(136, 0, 0);">2</span>);
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Receipt:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Subtotal:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">7</span>) &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::fixed &lt;&lt; subTotal &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Tip ("</span>  &lt;&lt; tip_Percent &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"%): "</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">3</span>) &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span> &lt;&lt; cash_Amount &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">22</span>) &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"--------"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Total:"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::setw(<span class="hljs-number" style="color: rgb(136, 0, 0);">10</span>) &lt;&lt;  <span class="hljs-string" style="color: rgb(136, 0, 0);">"$"</span> &lt;&lt; final_Amount &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
        }


        <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Minor error handling if user inputs anything but a 1 or a 2 as an integer input.</span>
        <span class="hljs-keyword" style="font-weight: 400;">else</span>
        {
            <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Invalid Input. Please Run The Program Again."</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;
        }



        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;

        <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Prompts the user if they would like to run the program again.</span>
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Would you like to run the Tip-Calculator again? \n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"1). Yes: \n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"2.) No:  \n"</span>
                     <span class="hljs-string" style="color: rgb(136, 0, 0);">"Selection:"</span>;

        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cin</span> &gt;&gt; choice;
        <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;

    } <span class="hljs-keyword" style="font-weight: 400;">while</span> (choice != <span class="hljs-number" style="color: rgb(136, 0, 0);">2</span>); <span class="hljs-comment" style="color: rgb(136, 136, 136);">// If our choice is 2 which is no, we exit our do/while loop.</span>



    <span class="hljs-comment" style="color: rgb(136, 136, 136);">// Prints out a goodbye message letting the user know the program has ended.</span>
    <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">cout</span> &lt;&lt; <span class="hljs-string" style="color: rgb(136, 0, 0);">"Thank You For Using The Tip Calculator\n"</span>
                 <span class="hljs-string" style="color: rgb(136, 0, 0);">"Have A Nice Day!"</span> &lt;&lt; <span class="hljs-built_in" style="color: rgb(57, 115, 0);">std</span>::<span class="hljs-built_in" style="color: rgb(57, 115, 0);">endl</span>;


    <span class="hljs-keyword" style="font-weight: 400;">return</span> <span class="hljs-number" style="color: rgb(136, 0, 0);">0</span>;
}</pre>

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
