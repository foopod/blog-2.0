---
layout: post
title: Advanced Google
date: 2017-02-12
tags: []
tagline: What google can do for you
description: Why solve a problem someone else has solved? Let Google do it and save your energy for other things.
image: /public/images/google.png
---

So you want to learn how to use Google like a pro? Want google to solve all your problems for you?

Here's how..

## What is Google?

Google is that kid that always knows the answer and puts up their hand 0.46s after the teach asks a question.

## How did Google get so smart?

Google reads hundreds of thousands of pages every day. And tries to organise everything so it can always find it again easily.

## How does it work?

Try searching for `241543903` on Google. What comes up in the images section?

Yep. Pictures of people with their heads in freezers. But why?

Because the internet is a weird and wonderful place. Google has seen pictures like this and the number 241543903 together all over the internet.

<p class="message" style="overflow:hidden">
  FACT :  In 2009 David Horvitz encouraged people to take a picture of their heads in a freezer and upload it with the tag “241543903”.
</p>

<div class="challengeContainer" markdown="1">
{:.challengeTitle}
## Challenge #1

<div class="challengeContent" markdown="1">
> Use Google to solve these challenges. **HINT:** Useful things to search are in **bold**

The box below reads **javascript**. How would you make a pop up **alert box** that says `Hello World!`?

<p class="challengeEntry" id="jsTestOneContainer"><input type="text" id="jsTestOne" placeholder="Put code here..."><button type="button" onclick="jsTestOne()">Submit</button></p>
<p style="text-align:right;"><a href="http://google.com/search?q=javascript+alert" target="_blank">Need some help?</a></p>
<script>
function jsTestOne(){
    if(document.getElementById("jsTestOneError")){
        document.getElementById("jsTestOneError").remove();
    }
    var input = document.getElementById("jsTestOne").value.toLowerCase();
    if(input.includes("alert")){
        alert("");
        document.getElementById("jsTestOneContainer").innerHTML = '<p class="correct">Correct!</p>'
    } else {
        document.getElementById("jsTestOneContainer").insertAdjacentHTML( 'beforeend', '<p class="incorrect" id="jsTestOneError">Nope try again!</p>' );
    }
}
</script>
</div></div>

<div class="challengeContainer" markdown="1">
{:.challengeTitle}
## Challenge #2

<div class="challengeContent" markdown="1">
>In programming there lots of ways to solve the same problem. Google will still find the answer for you, but it might not be the first result.

See this poop? Which **css** style would **move** it to the right side of the **page**.

<p id="jsTestTwoTarget" style="font-size:50px;">💩</p>
<p class="challengeEntry" id="jsTestTwoContainer"><input placeholder="Put code here..." type="text" id="jsTestTwo"><button type="button" onclick="jsTestTwo()">Submit</button></p>
<p style="text-align:right;"><a href="http://google.com/search?q=css+move+right" target="_blank">Need some help?</a></p>
<script>
var attempts = [];
function jsTestTwo(){
    if(document.getElementById("jsTestTwoError")){
        document.getElementById("jsTestTwoError").remove();
    }
    var input = document.getElementById("jsTestTwo").value.toLowerCase();
    if(input.includes("margin") || input.includes("padding") || input.includes("text-align") || input.includes("float") || input.includes("right") || input.includes("position") ){
        if(!attempts.includes(input)){
            if(attempts.length == 0){
                document.getElementById("jsTestTwoContainer").insertAdjacentHTML( 'beforeend', '<p id="jsTestTwoError" class="incorrect">Not that one!</p>' );
                attempts.push(input);
            } else {
                document.getElementById("jsTestTwoTarget").style.textAlign = "right";
                document.getElementById("jsTestTwoContainer").innerHTML = '<p class="correct">Correct!</p>';
            }
        }
    } else {
        document.getElementById("jsTestTwoContainer").insertAdjacentHTML( 'beforeend', '<p id="jsTestTwoError" class="incorrect">Not that one!</p>' );
    }
}
</script>
</div></div>

## How do I find the information I need?

Google gives you some handy sites, it's up to you to find the info you need.

Each website shows its data in its own way. Here are some common sites and tips to find what you are looking for.

**Stack Overflow** is one of your most powerful allies. It is kind of like yahoo answers but for coding. Just skim the question to see if it us like your problem and read the answers that have the **most votes**.

**W3Schools** has tons of info on HTML, CSS and javascript. The code and example sections are my favourite because that's where all the code is.

For **anything else** you can just skim the page or use Find (CMD+F or CTRL+F) on the page to search for keywords.

<div class="challengeContainer" markdown="1">
{:.challengeTitle}
## Challenge #3
<div class="challengeContent" markdown="1">

The box below uses **python**. How do you **add an object to a list**?

<p class="challengeEntry" id="jsTestThreeTarget">[❤️️, ⚽, ☺️️, ✌️️]</p>
<p id="jsTestThreeContainer" class="challengeEntry"><input placeholder="Put code here..." type="text" id="jsTestThree"><button type="button" onclick="jsTestThree()">Submit</button></p>
<p style="text-align:right;"><a href="http://google.com/search?q=python+add+to+list" target="_blank">Need some help?</a></p>
<script>
function jsTestThree(){
    if(document.getElementById("jsTestThreeError")){
        document.getElementById("jsTestThreeError").remove();
    }
    var input = document.getElementById("jsTestThree").value.toLowerCase();
    if(input.includes("append")){
        document.getElementById("jsTestThreeTarget").innerHTML = "[❤️️, ⚽, ☺️️, ✌️️, ☂️]";
        document.getElementById("jsTestThreeContainer").innerHTML = '<p class="correct">Correct!</p>';
    } else {
        document.getElementById("jsTestThreeContainer").insertAdjacentHTML( 'beforeend', '<p id="jsTestThreeError" class="incorrect">Maybe try something else.</p>' );
    }
}
</script>
</div>
</div>

## Don't search for questions, search for answers

Google is starting to get better at matching questions to answers. But it's excellent at finding answers on their own.

Try searching for the answer on its own, think about how it would be phrased.

So instead of searching for `What is the land mass of Australia?`, try looking for the answer `Australia land mass`. Not only is it quicker to type in, but you will find it even if no one has asked the question.

If you are looking for something specific you can search for an answer using quotation marks. So instead of searching for `need to summon a druid, then sing me a song` you could search for `"Need to summon a Druid?" "Sing me a song"`.

<div class="challengeContainer" markdown="1">
{:.challengeTitle}
## Challenge #4
<div class="challengeContent" markdown="1">

Who first said `"What doesn't kill you does a great job of making you look incompetent"`?

<p id="jsTestFourContainer" class="challengeEntry"><input placeholder="Name goes here..." type="text" id="jsTestFour"><button type="button" onclick="jsTestFour()">Submit</button></p>
<p style="text-align:right;"><a href='http://google.com/search?q="What+doesn%27t+kill+you+does+a+great+job+of+making+you+look+incompetent"' target="_blank">Need some help?</a></p>
<script>
function jsTestFour(){
    if(document.getElementById("jsTestFourError")){
        document.getElementById("jsTestFourError").remove();
    }
    var input = document.getElementById("jsTestFour").value.toLowerCase();
    if(input.includes("cowern") || input.includes("dianna")){
        document.getElementById("jsTestFourContainer").innerHTML = '<p class="correct">Correct!</p><p >Notice how the quotation marks helped narrow down the search?</p>';
    } else {
        document.getElementById("jsTestFourContainer").insertAdjacentHTML( 'beforeend', '<p id="jsTestFourError" class="incorrect">Nope.</p>' );
    }
}
</script>
</div>
</div>

## Extra Super Powers

Google has a lot of other cool hidden stuff.

Try using an **asterisk (*)** as a wildcard to include everything.

>eg. `"Largest * in the world"`

Start your search with **site:** if you want to limit your search to a specific site.

>eg. `site:wikipedia.org swallow velocity`

You can also use **-** to remove something from search results.

>eg. `jaguar speed -car`

## Google in action!

So now that you know how to use Google, put it to work while you are coding.

It works for anything and everything. Not just scratch or HTML, but any question you have about anything.

Want to see how I use Google?

<a href="https://docs.google.com/document/d/1L6JDnchdb53lg15haj1gbhHnNLlATVOzRVO3AjgQ_eo/edit?usp=sharing" target="_blank">
This</a> is a log of how I google when I am programming. Yep. Every few minutes I find something I haven't memorized and need to google it.

I hope you enjoyed this 'How to Google' tutorial. If you have any questions or requests on things for next time then leave a comment for me down below.
