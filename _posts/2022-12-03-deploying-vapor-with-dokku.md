---
layout: post
title: Deploying a Vapor app on an Ubuntu server with Dokku
date: 2022-12-03 18:00 -0300
categories: en
---

Context switch is a bitch, there's no nice way to say it. When I work on side projects that needs a backend service it slows me down a lot. 

I've worked with [Sinatra](https://sinatrarb.com) and [Ruby on Rails](https://rubyonrails.org) in the past. They're great but I don't use the quite often so I'm very slow when I work with them because my memory is terrible.

On the other hand, I code in Swift every day. So there are some things I can quickly code as if it's matter of *"muscle memory"*.

Because of that, [Vapor](https://vapor.codes) looks like a perfect fit for me, or at leas it's what I thought.

## 1. Requirements
Like every tutorial, it is likely to get outdated after a while. These are the versions I worked with. 

```
- Dokku's version: 0.28.4
- Let's Encrypt plugin version: 0.18.1
- Vapor's version: 4.66.1
```

Hopefully, deploying Vapor apps with Dokku will get more straightforward in the future and you won't need to follow these steps anymore.

## 2. Create a new project and run it locally
1. Create a new vapor project using the [CLI tool](https://docs.vapor.codes/install/macos/#install-toolbox).
`vapor new HelloVapor`

We don't need **Fluent** (databases) but we want to install **Leaf** (templates).

2. Run the project on our machine.

3. Make sure it works\
`curl http://127.0.0.1:8080/hello`

## 3. Deploy to Dokku
1. Create a new Dokku app
`ssh dokku@[REDACTED] apps:create hellovapor`

2. Create a new local git repository and push to Dokku
```
git init
git remote add betzerra dokku@[REDACTED]:hellovapor
git push betzerra main:master
```

### ... and we're done, right?
Well, no.

We've deployed the app but with no **https** support. This would've been _just fine_ in 2010 but now there're many browsers that won't open "unsecured" websites by default.

That's where **letsencrypt plugin** comes in.

1. Set your email to DOKKU_LETSENCRYPT_EMAIL environment variable so the plugin can do its magic
```
ssh dokku@[REDACTED] config:set --no-restart hellovapor DOKKU_LETSENCRYPT_EMAIL=[REDACTED]
```

2. Get a letsencrypt certificate for our project
`ssh dokku@[REDACTED] letsencrypt:enable hellovapor`

If you're using the versions I defined above you'll get an error.

```
2022/12/03 20:09:28 Could not obtain certificates: error: one or more domains had a problem:

[REDACTED] acme: error: 403 :: urn:ietf:params:acme:error:unauthorized :: [REDACTED]: Invalid response from [REDACTED]:443/.well-known/acme-challenge/3e9u9oJnT9r1Do83dtiCOWvk4BSDFgyONlfbK7nNZvc: 404
```

I got stuck with this error for more than a week.
Reported this [here](https://github.com/dokku/dokku-letsencrypt/issues/285) and [here](https://github.com/vapor/vapor/issues/2911) but had no luck.

### The fix
This piece of information in the [README](https://github.com/dokku/dokku-letsencrypt#dockerfile-deploys) helped me a lot:
> For Dockerfile deploys, by default, dokku will determine which ports a container exposes and proxies all those exposed ports in the Docker container by listening on the same port numbers on the host. This means that both the proxies for HTTP port 80 and HTTPS port 443 to the app's container need to be manually configured.

This is how it should look like when you write:
`ssh dokku@[REDACTED] proxy:ports hellovapor`

Use **proxy:ports-remove** command to set the ports properly.
For example:
```
// Remove the wrong port
ssh dokku@[REDACTED] proxy:ports-remove hellovapor http:8080:8080

// Add http and https
ssh dokku@[REDACTED] proxy:ports-add hellovapor http:80:8080
ssh dokku@[REDACTED] proxy:ports-add hellovapor https:443:8080
```

Now re-run **letsencrypt** command:
`ssh dokku@[REDACTED] letsencrypt:enable hellovapor`

This time should run fine 🙌

## 4. Herokuish Buildpack (Optional)
If you're getting an outdated Swift, you could try Heroku's buildpack:

Create a file called `.buildpack` with the following content:
```
https://github.com/vapor/heroku-buildpack
```

