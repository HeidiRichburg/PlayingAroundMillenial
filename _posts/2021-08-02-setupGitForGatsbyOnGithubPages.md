---
layout: post
title: "Set Up Git for Gatsby and GitHub Pages Custom Domain Hosting"
author: "Heidi"
categories: facts
tags: [githubpages]
image: cuba-4.jpg
---
Here are the steps to set up git so that you can use VS Code directly to work with the site you are developing.
This applies specifically when you are working locally on a Gatsby app using VS Code as your IDE/Editor, and you want to host it on GitHub Pages using a custom domain name.

1. Stop the server in VS Code.

If you have a repo set up already, skip to step 4.

2. Log in to GitHub online. 
3. Create a repo, and select 'Public'. There will be some details regarding the repo, and we will use these.
4. In a terminal/command promt window on your computer (not in VS Code terminal), navigate to the directory where you are working.
5. In the terminal, type the following: 
      git remote add origin https://github.com/<your-user-or-organization-name>/<repo-name>.git
6. You may get an message saying the repo already exists. In the terminal, type: 
      git remote origin set-url https://github.com/<your-user-or-organization-name>/<repo-name>.git
7. In the terminal, you will now install the package for gatsby to work smoothly with github pages type: 
      npm install gh-pages --save-dev
8. Back in VS Code, add a script to the package.json, just above the build script:
  "deploy": "gatsby build && gh-pages -d public"
9. Save your file.
10. Back in terminal type:
      npm deploy
11. Address any errors and try again until you get 'SUCCESS'

If you are configuring the repo to work with the custom domain name, go back to your repo in GitHub online.
  1. Select Settings -> Pages, select 'gh-pages' branch, 'Save'
  2. Below that you can enter the custom domain name: www.<your-domain>.<com, net, etc>
  3. Save that.
  4. Now go to your DNS provider to create a CNAME entry that will affiliate your page to be hosted on GitHub pages with your account on GitHub pages.
   From GitHub documentation: "For example, if you want to use the subdomain www.example.com for your user site, create a CNAME record that points www.example.com to <user>.github.io. If you want to use the subdomain www.anotherexample.com for your organization site, create a CNAME record that points www.anotherexample.com to <organization>.github.io. The CNAME record should always point to <user>.github.io or <organization>.github.io, excluding the repository name."
  5. Your site will be live as soon as this propagates. Take a walk, get a tea, come back, and check out the page on your domain!
  
