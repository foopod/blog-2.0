---
layout: post
title: Construct 3
date: 2017-04-02
tags: []
tagline: Getting started with Construct 3
description: You can make games too with the new Construct 3 beta!
image: /public/images/c3.png
---

Welcome to Construct 3!

The massive advantage that Construct 3 has over Construct 2 is that it runs in your browser. This means you can update your game project from any internet connected device, you don't need to install a game engine.

Goals. What do we want to get out of this tutorial?

+ Starting a Project
+ Learning about layouts and event sheets
+ Use pre-made behaviours to make setup really easy

## Getting started

So to get started just head right on over to...

[https://editor.construct.net/](https://editor.construct.net/)

Click on `NEW PROJECT` to get started on a new project.

<img src="/public/images/c3/0_new_project.png"/>

You will see a new screen that looks something like this...

<img src="/public/images/c3/1_workspace.png"/>

1. **Properties Panel** - This shows you everything you need to know and everything that you might be able to edit about the selected object. 
2. **Workspace Tabs** - These let you quickly swap back and forth between workspace assets you have open. Layouts are essentially scenes in your game, you might have one for each level or others for your start screen or for high scores. Event sheets define all of the interactions that happen in your game, it works kind of like "If that then this".
3. **Workspace** - This is the main view into the asset you are working on, be it a layout or an event sheet or something else.
4. **Assets** - This is a file browser for all your assets, not just programming, but images and sounds, whatever you need.
5. **Play** - The most important button, this launches your game so you can test it while you build it.

Woo! Now lets make a game!

## Making a Sprite

Open Layout 1 either from your assets or by clicking on its Tab.

Now if you `Right-Click` and select **Insert new object** you can find all sorts of things to add to your layout.

From this menus select Sprite. This will be our player character that we control.

<img src="/public/images/c3/2_sprite.png"/>

Once you select sprite you will have some funky cross hairs, just click anywhere in your layout to add the sprite to it.

This will bring up the animation editor...

<img src="/public/images/c3/3_sprite_editor.png"/>

As you can see I just drew a simple **fly** to be my main character. But for now just draw anything in the box and you can perfect it later.

## Behaviours

Now if you click on your new found character you will see the properties panel for it on the left hand side. Let's take the time to rename it from `Sprite` to something more recognizable.

<img src="/public/images/c3/4_properties.png"/>

You can also change any properties you want here, for example it's size or it's position.

If you ever want to know more about a property, just select it and a tip will appear at the bottom of the panel with more information about it.

Click `Behaviours` in the properties panel and you will get a little screen like this...

<img src="/public/images/c3/5_behaviours.png"/>

`Right-Click` and select **Add behaviour**.

Behaviours are predefined behaviours, not just for the player, but for common objects in video games.

<img src="/public/images/c3/6_add_behaviour.png"/>

For now we are just going to grab something to move our player around.

In the Movements section, select **8Direction** from this list. This lets us move the character around using the arrow keys on the keyboard.

Now that this Behaviour is attached to your sprite you will see the behaviours properties appear in the property panel too.

Like so...

<img src="/public/images/c3/7_behaviour_properties.png"/>

You can tweak these however you want to make the game feel different.

Now press the play button to see if it works.

You may notice that your player rotates as you move it around to face the direction it moves. This didn't make much sense for my fly so I changed `Set Angle` to `No` in the 8Direction properties.

Awesome! Now we know how to add behaviours!

## Events

Right now it isn't much of a game. Let's make a goal.

Now create a new Sprite for our goal. I have chosen to poorly draw an apple for now.

<img src="/public/images/c3/8_apple.png"/>

This sprite doesn't need to do anything other than just sit there, so we don't need to worry about adding behaviours.

Next we want to display a message when the player gets to the goal.

Go to the **Insert new object**, to do this `Right-Click` and select **Insert new object**. Here we are going to look for the **Text** object.

<img src="/public/images/c3/9_text.png"/>

Place your text and use the properties panel to change the `Text` and the `Size` to something more suitable. Note this properties menu is confusing because there are two sizes, the top one is for the size of the text box and the bottom one is for the font size.

Mine looks something like this...

<img src="/public/images/c3/10_win.png"/>

**IMPORTANT** : Look for the property `Initially Visible` and untick it. This will make sure that the text is hidden when the game starts.

Sweet. Now we just want to set up some events to show this when the Sprite reaches the apple.

Open your `Event Sheet 1` either from the asset menu on the right or by clicking on its tab. Since you don't have any events yet all you will see is a button to add one.

Events work by having a condition on the left, once the condition is met then the actions on the right happen.

Click **Add event**. Next choose the object that the event happens on. We want to trigger our event when the player reaches the goal, so **we will choose the player sprite**.

<img src="/public/images/c3/11_events_start.png"/>

Next. We want this to trigger when it collides with the goal. So under `Collisions` select `On collision with another object`.

<img src="/public/images/c3/extra_collision.png"/>

Next. Now just choose your other Sprite(in my case the apple) as the object to test for a collision with.

Awesome! Now we have one event!

<img src="/public/images/c3/12_event_sheet.png"/>

And we just need to add actions that happen when the collision happens.

Click **Add action**. Most importantly we should make our text appear to let the user know that they have won.

To do this we select our Text object to perform the action on.

<img src="/public/images/c3/13_wintext.png"/>

And under `Appearance` we select `Set visible`. We want to set the **visibility** to **visible**.

Bam! Now when you play the game and reach the goal your fantastic text should appear.

Maybe we want it to reset though?

Let's add two more actions, the first to wait for a few seconds to read the congratulations text and the second to restart the game.

Let's Click **Add action** to add another action.

But this time the action isn't on a Sprite, the action is telling the system to wait for a while.

So Select `System` to perform the action on.

<img src="/public/images/c3/14_system.png"/>

And in the `Time` section find the action called `Wait`. Select this and choose a wait time of `3` seconds.

<img src="/public/images/c3/15_wait.png"/>

Easy. One more now. Click **Add action** to add another, this time to restart the game.

This is another `System` action. Look for the action called `Restart layout` in the `Layout` section and select it. This will take your layout back to its beginning state, reset the player and set the text to be invisible.

Something like this...

<img src="/public/images/c3/16_events.png"/>

## Nice!

Today we...

+ Started a Construct3 project
+ Made a Sprite with behaviours to move around
+ Learned how events work

## Going Forward

Have a play with the other behaviours that are availble and see what other kind of actions you can do on objects. There is a lot of room to make cool stuff with what we just learned.

Unfortunately there is no documentation for Construct3 right now. But pretty much all of the Construct2 tutorials and documentation will work for Construct3 too.

Here are some handy resources for you going forward...
+ The Construct2 Manual ([https://www.scirra.com/manual/11/start-page](https://www.scirra.com/manual/11/start-page))
+ Construct2 Tutorials ([https://www.scirra.com/tutorials/top](https://www.scirra.com/tutorials/top))