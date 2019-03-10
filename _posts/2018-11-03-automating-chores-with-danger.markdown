---
layout: post
title:  "Automating chores with Danger"
date:   2018-11-03 19:06:00 -0300
categories: en canillitapp automation danger
---

It's been a while I've been thinking about writing about [Fastlane](https://fastlane.tools) and [Danger](https://danger.systems). 

Basically, because **I hate manual processes**. I do. They are boring, require lots of time and they're prone to human errors. The more boring the task is, the more likely to fuck it up I am.

So automating these tasks are (for me and probably for you too) not just a way of being happier at work, but also a sort of safety net. Of course you'll need to invest some time on it, and it will probably need a couple of iterations after you're 100% happy with it. But it pays off quickly, I promise :-)

On this post I'll make an introduction about **Danger** and give some examples of what you can do with it [^1].

# Getting started before "Getting started"
First of all, I need to give you a tip regardless you agree with me at the end of this post or not. Cocoapods, Danger [^2] and Fastlane are tools written in Ruby. If you're using any of these, I recommend you to:

- [Use RVM](https://rvm.io)[^3] so you can have many versions of Ruby in your system. This will avoid some possible issues in the future.
- [Use Bundler](https://bundler.io), this will allow you to get multiple versions of ruby gems. This means that you can have Cocoapods `1.4.0` on one project, and `1.5.3` on another.
- Write your dependencies on a [Gemfile](https://github.com/Canillitapp/headlines-iOS/blob/master/Gemfile).

# So... what’s Danger?
Well, [the website has a great explanation](https://danger.systems/ruby/) but the TLDR; version would be:

> it’s a script that runs on the CI phase and it will send messages on your pull request depending on some rules you wrote on the [Dangerfile](https://github.com/Canillitapp/headlines-iOS/blob/master/Dangerfile)

![Danger bot working]({{site.url}}/assets/danger_demo.png)

Still confused? Here are some examples:

- check if my code complies with project's code style.
- warn me to update `changelog.md` if I forgot.
- if it’s a release branch, remind me to tag this commit after it’s approved.
- if the PR is still in progress, warn my teammates.
- if my PR is too long remind me to make changes as atomic as possible next time.
- if some core files are modified, maybe it's a good idea to notify top contributors
- if it’s an Open Source project, thank other contributors.

On top of that, I'll add that apart from preventing humans to do those chores, it removes the friction of being the bad cop that asks developers to remove that extra whitespace ;-)

# Dangerfile
So, once you have an idea of what are the rules you want to implement, you just write these on a file called `Dangerfile`, here's an example (Ruby developers will find this quite easy):

```ruby
# check if my code complies with project's code style.
swiftlint.lint_files inline_mode: true

# warn me to update changelog.md file if I forgot.
no_changelog_entry = !git.modified_files.include?("changelog.md")
if no_changelog_entry
  warn_text = 'Please consider adding a note to our changelog if its required.'
  warn(warn_text)
end

# if it’s a release branch, remind me to tag this commit after it’s approved.
if github.branch_for_head.include? 'release'
  message_text = """
  This looks like a release PR. 
  Don't forget to: 
  - Tag the version. 
  - Write the changelog.
  - Build a version and deploy to QA.
  """
  message(message_text)
end

# if the PR is still in progress, warn my teammates.
warn("PR is classed as Work in Progress") if github.pr_title.include? "[WIP]"

# if my PR is too long remind me to make changes as atomic as possible next time.
warn("Big PR") if git.lines_of_code > 500

# if some core files are modified, maybe it's a good idea to notify top contributors
modified_core_files = !(git.modified_files.grep(/core/).empty?)
if modified_core_files
  message('Heads up @betzerra . This might be important')
end

# if it’s an Open Source project, thank other contributors.
message("Thanks @#{github.pr_author}! :tada:") if github.pr_author != "betzerra"
```

Check Danger's website for more examples.

# Setup Dangerfile
- Add Danger and its plugins (if needed) on your Gemfile. [See an example](https://github.com/Canillitapp/headlines-iOS/blob/master/Gemfile)
- Setup an account on Github / Gitlab / Bitbucket for the bot. This is probably the most annoying part. Follow [these instructions](https://danger.systems/guides/getting_started.html).
- Setup your CI file to run Danger. [See an example on TravisCI](https://github.com/Canillitapp/headlines-iOS/blob/master/.travis.yml)
- ???
- Profit

By now, you should have your own Danger bot working on your repos. Kudos! 
Let me know your doubts / opinions via twitter @betzerra or by email!

[^1]: I'll talk about Fastlane on the next post. 
[^2]: There's a javascript version for Danger, but [javascript sucks](https://www.destroyallsoftware.com/talks/wat).
[^3]: I heard [rbenv](https://github.com/rbenv/rbenv) is great too but I use RVM so... 🤷
