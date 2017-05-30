---
layout: tutorial
title: Making a Website
date: 2017-05-30
tags: []
tagline: Creating a static website with Github Pages
description: Learn how to make a simple website using Github Pages
image: /public/images/web.png
---

Github is an awesome place that lets people collaborate to create fantastic things.

## Goals

What do we want to get out of this tutorial?

+ Create a Github account
+ Make our own website

## Getting started

First thing we need to go and sign up at [Github](http://github.com/).

Once you have done that we will make our first repository (repo). A repo is kind of like a magic folder that lets us track when things were added to it.

Just click the **New Repository** button on github or follow [this link](https://github.com/new).

I called my repository `site`, you can name yours whatever you want, but when I refer to `site` going forward you will have to keep this in mind.

Also be sure to tick the box for 'Initialize this Repository with a README'. We do this so we can start using the repo right away.

## Adding some content

That was easy, now we have an empty repo, well except for that README.

The first thing we are going to do now is add an html file that will be the first iteration of our website.

To do this click the **Create new file** button. Up the top you can name the file and for our website to work properly this homepage of your website must be called `index.html`. Easy.

Below is a really simple html page that you can copy and paste into your `index.html` to get you started.

``` html
<html>
    <head>
        <title>Website</title>
    </head>
    <body>
        <h1>Hello World!</h1>
    </body>
</html>
```

Now you can scroll to the bottom and click **Commit new file**.

## Making your site live on Github Pages

This last step is super simple. We are just going to enable the Github Pages feature on our repository.

To do this, go to the settings tab of your repo and in the options find the section for Github Pages.

Next just change the source from **None** to **master branch**.

The page will refresh and when you scroll down to the same github pages section you should now see a link to your newly created website.

## Nice!

Today we...

+ Made a Git Account
+ Made a website

<div class="challengeContainer" markdown="1">
{:.challengeTitle}
## Challenge

<div class="challengeContent" markdown="1">
> Make a super cool site

Think about the cool things you learned in the HTML & CSS codeclub exercises and start coding away at your own website.

</div></div>

## Going Forward

This whole exercise relies on something called Git under the hood.

If you are interested in learning how it works then I would highly recommend this [game](http://learngitbranching.js.org/). It shows all of the git concepts and is quite fun too.