---
layout: post
title: "Installtion"
description: "Error & Installation"
categories: [Install, Errors]
tags: [install theme, error in installtion]
redirect_from:
  - /2020/06/07/
---

## Installing jekyll 

`sudo gem install jekyll`  (It will take 15 minutes if not already installed)

## Creating your new site  


> Follow steps:
> * `jekyll new name_of_your_site`
> * Once created the website folder with Folders(_posts, _site) in it.
> * You are ready to serve the website to locally by typing "`jekyll serve`"


## Errors 

If any theme requires newer version of bundler then it is ok with

`gem install bundle` (It will install newer version)

But if any theme requires older version of bundler then it is not ok with above command
`gem install bundler -v your_version`

After that you need to install bundle for you theme :
`bundle _yourVersion_ install` (Don't remove underscore first underscore then version and then again underscore 
For ex. `bundle _2.0.2_ install`)


### If this error comes:  
-> /usr/lib/ruby/vendor_ruby/rubygems/defaults/operating_system.rb:10: warning: constant Gem::ConfigMap is deprecated

### Solved with:- `sudo gem update --system 3.0.6`


-- Autoreload with add command line attribute :- `jekyll serve --watch` (locally)
