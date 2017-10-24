---
layout: default
title: Ask
description: Ask Jono a question
---

<style>

</style>

<p class="message" style="overflow:hidden">
  Feel free to ask Jono anything you want! Having a tough time with a coding problem? Want to know what I think about X or Y? 
</p>
  <form style="max-width:30em;margin:auto;padding:1em;" class="form-horizontal" netlify name="Ask Jono" action="/thanks" method="POST">
    <fieldset>
    <label for="name">Name</label>
    <input id="name" class="full-width" name="name" type="text" placeholder="Your name">

    <label for="email">E-mail</label>
    <input id="email" class="full-width" name="Email" type="text" placeholder="Your email" >

    <label for="message">Question</label>
    <div>
    <textarea class="full-width" required id="message" name="message" placeholder="Please enter your question here..." rows="5"></textarea>
    </div>

    <div class="text-right">
        <button type="submit" class="btn btn-dark btn-lg">Submit</button>
    </div>
    </fieldset>
    </form>