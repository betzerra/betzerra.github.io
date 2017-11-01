---
layout: post
title:  "Querying Canillitapp with a little of shell scripting"
date:   2017-06-22 10:00:00 -0300
categories: jekyll update
---

I recently discovered [JQ](https://github.com/stedolan/jq) and it worked perfect for me to query [Canillitapp services](https://github.com/Canillitapp/headlines-api).

Here are some examples:

**search.sh**

- Makes a search (URL escaped) and shows last 20 examples. 
- Transforms UNIX timestamp into a legible date.

{% gist betzerra/74f97e4b8693f725aed56b5f60d04038 search.sh %}

`sh search.sh calu%20rivero`

{:refdef: style="text-align: center;"}
![terminal screenshot]({{site.url}}/assets/canillitapp_terminal_001.png){:width="700px"}
{:refdef}

**latest_news.sh**

- Shows last 20 news.
- Transforms UNIX timestamp into a legible date.

{% gist betzerra/74f97e4b8693f725aed56b5f60d04038 latest_news.sh %}

`sh latest_news.sh`

{:refdef: style="text-align: center;"}
![terminal screenshot]({{site.url}}/assets/canillitapp_terminal_002.png){:width="700px"}
{:refdef}

**trending_news.sh**

- Shows trending topics for today.
- Transforms UNIX timestamp into a legible date.

{% gist betzerra/74f97e4b8693f725aed56b5f60d04038 trending_news.sh %}
{:refdef: style="text-align: center;"}
![terminal screenshot]({{site.url}}/assets/canillitapp_terminal_003.png){:width="700px"}
{:refdef}

**finally, alias the scripts in order to make your life easier**
{% gist betzerra/74f97e4b8693f725aed56b5f60d04038 .zshrc %}
