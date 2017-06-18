---
layout: post
title:  "Why I moved my news service from bot to app 📱"
date:   2017-06-17 09:00:00 -0300
categories: jekyll update
---

It's been more than a year since I talked about [botzerra, my news bot]({{site.url}}/jekyll/update/2016/04/26/telegram-bot.html).
Back then, there was a lot of hype around bots. It was justfied, bots are awesome for several reasons: mostly because users don't need to download a new app (they don't need to login or sign up either). So I guess it's ok to say there's less friction on bots than in apps, right?

Well, not quite. For some users, the idea of _an app inside your messaging app_ was quite hard to grasp.
Also, after the novelty wore off I realized that having an app would be more attactive.

To start with, bot's flow is way slower:
1. Open Telegram.
2. Look for News bot.
3. Write `/latest_news`.
4. Send.

Let's check same flow on an app:
1. Open app.

Boom.

In addition, apps can potencially look much better than bots.
- Bots focus on simple actions and content is key.
- Apps are more complex and focus on richer experiences.

So I extracted the code from the bot and I made a [news API](https://github.com/Canillitapp/headlines-api).
After that, I created an [Apple Watch client](https://twitter.com/betzerra/status/768816272192733184), and many months later it became a whole [iOS app](https://itunes.apple.com/us/app/canillitapp/id1148447560?ls=1&mt=8).

{:refdef: style="text-align: center;"}
![terminal screenshot]({{site.url}}/assets/canillitapp_screenshot.png){:width="300px"}
{:refdef}

My conclussion is that there's no better platform than other. As many things in life, there's always a trade off. If possible, try to think your app as a service and how could you adapt it on different use cases such as mobile apps, widgets, smartwatch apps, tv apps, bots, webapps and so on.

