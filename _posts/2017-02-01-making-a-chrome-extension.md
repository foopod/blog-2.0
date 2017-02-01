---
layout: post
title: Making a Chrome Extension
date: 2017-01-29
tags: []
tagline: Adds rainbows to your browser
description: Creating a chrome extension that inject javascript into the browser
---

### First Steps

I had this idea when I was making the sidebar for my blog, wouldn't it be cool if every website was this joyous?

So I started off making a Bookmarklet (a browser bookmark that contains javascript) that would do this. It is pretty simple and just adds a pretty animated canvas to the DOM.

```
(function(){
  //Find the body and add the canvas element
  var body=document.getElementsByTagName("body");
  var canvas=document.createElement("canvas");
  document.body.appendChild(canvas);
  
  function init(){
    //Set up the canvas
    canvas.id="rainbowApp";
    canvas.style.position="fixed";
    canvas.style.padding="0";
    canvas.style.top="0";
    canvas.style.left="0";
    canvas.style.zIndex="-5";
    window.addEventListener("resize",function(){resizeCanvas();},!0);
  }
  
  /* Function to resize the canvas to the window */
  function resizeCanvas(a){
    canvas.width=window.innerWidth;
    canvas.height=window.innerHeight;
  };
  
  init();
 
})();
```

Just drag and drop this great emoji <a href='javascript:(function()%7Bfunction run()%7Bfor(var a%3D0%3Ba<10%3Ba%2B%2B)drawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23FEF"%2C100*Math.random()%2B50)%2CdrawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23EFE"%2C100*Math.random()%2B50)%2CdrawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23FFE"%2C100*Math.random()%2B50)%2CdrawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23EFF"%2C100*Math.random()%2B50)%2CdrawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23EFE"%2C100*Math.random()%2B50)%2CdrawSquare(Math.random()*canvas.width-25%2CMath.random()*canvas.height-25%2C"%23FEE"%2C100*Math.random()%2B50)%7Dfunction init()%7Bctx%3Dcanvas.getContext("2d")%2CresizeCanvas()%2Cwindow.addEventListener("resize"%2Cfunction()%7BresizeCanvas()%7D%2C!0)%2CsetInterval(run%2C33)%7Dfunction drawSquare(a%2Cb%2Cc%2Cd)%7Bctx.fillStyle%3Dc%2Ccanvas.height>canvas.width%3Fctx.fillRect(Math.random()*canvas.width%2C0%2C3%2Ccanvas.height)%3Actx.fillRect(0%2CMath.random()*canvas.width%2Ccanvas.width%2C3)%7Dfunction resizeCanvas(a)%7Bcanvas.width%3Dwindow.innerWidth%2Ccanvas.height%3Dwindow.innerHeight%7Dvar body%3Ddocument.getElementsByTagName("body")%2Ccanvas%3Ddocument.createElement("canvas")%3Bcanvas.id%3D"app"%2Cdocument.body.appendChild(canvas)%2Ccanvas.style.position%3D"fixed"%2Ccanvas.style.padding%3D"0"%2Ccanvas.style.top%3D"0"%2Ccanvas.style.left%3D"0"%2Ccanvas.style.zIndex%3D"-5"%3Bvar ctx%3Binit()%7D)()%3B'>✨</a> link into your bookmark bar or just click it to see its effects.

So that worked really nicely and I was really happy with it, but I want rainbows on every page and I don't want to have to click a button every time.

### Wrapping in a Chrome Extenion

Enter [Chrome Extensions](https://developer.chrome.com/extensions/devguide).

Looks easy right? That is what I thought too!

And for something simple like this it was pretty easy. But when I came to add a toggle button to my extension all I found was pain and hardship.

First off I had to make a `manifest.json` to declare information about your app. This has things like icons, permissions and the scripts that will be executed.

```
{
  "name": "Rainbows For All",
  "version": "1.0",
  "description": "Rainbows For All!",
  "permissions": ["<all_urls>"],
  "content_scripts": [{
      "js": ["addContent.js"],
      "matches": ["<all_urls>"]
  }],
  "icons": { 
    "16": "icon-16.png",
    "32": "icon-32.png",
    "48": "icon-48.png",
    "128": "icon-128.png" },
  "web_accessible_resources": ["rainbow.js"],
    "browser_action": {
   "default_icon": {
       "32": "icon-32.png"
       },
   "default_title": "Rainbows!"
},
  "manifest_version": 2
}
```

Above you will notice two scripts, `addContent.js` and `rainbow.js`. The `content_scripts` run as part of the chrome extension itself, whereas `web_accessible_resources` are files that your chrome extension can access.

`rainbow.js` is just my bookmarklet script from above. `addContent.js` is the chrome extension, all it does is add my other script to the DOM in `<script>` tags.

`addContent.js`

```
var rainbowInstallService = document.createElement('script');
rainbowInstallService.src = chrome.extension.getURL('rainbow.js');
(document.head||document.documentElement).appendChild(rainbowInstallService);
rainbowInstallService.onload = function() {
    if(rainbowInstallService.parentNode != null){
        rainbowInstallService.parentNode.removeChild(rainbowInstallService);
    }
};
```

So aside from all the images my extension is just these three files (`manifest.json`, `addContent.js` and `rainbow.js`).

I would have liked to have built it in a way that allowed the user to turn it on and off. But the Chrome API is quite confusing (read:was late at night and was by no means thorough). Also not that many stack overflow posts :(

Source code is [here](https://github.com/foopod/rainbows-for-all/).

Thanks for visiting!

