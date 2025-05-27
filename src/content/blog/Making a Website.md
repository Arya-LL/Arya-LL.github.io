---
author: Arya Lyngdoh Lakshmanan
pubDatetime: 2024-01-30T19:04:28.969Z
title: Making a Website
slug: making-a-website
featured: true
draft: false
tags:
  - Personal
  - Techincal
  - Markdown
  - Guide
description: A summary of my experience creating a personal blog, and how you can do it too.
layout:
---
So I kinda made a website. Here's an accessible how-to using my experiences as a guide if you're looking to build your own website as well!

## Table of Contents

## Goals

Before I get into the what and hows of making a personal blog, let me outline my goals in creating this website. I wanted to create an accessible collection of documentation on my various projects in hopes of structuring my ideas better and developing my ability to present repeatable versions of my work. I hope that by documenting these projects in a simple blog, my work will have a further reach than if I only used technically dense documentation techniques.

With that in mind, I do not have experience in developing pretty or efficient front ends - regardless of coding heavy tooling or blog publishing tools. However, I recently found a love for [Obsidian.md](https://obsidian.md/), and have been itching to create something beautiful with markdown.

## Tech stack

### TL;DR

- Written in: Markdown
- Using:  [Obsidian.md](https://obsidian.md/)
- With Web Framework: [Astro](https://astro.build/)
- Using a modified template from: [Astropaper by Sat Naing](https://astro.build/themes/details/astro-paper/)
- Running on: [github pages](https://pages.github.com/)

### Writing tools

I will likely create a future post on [Obsidian.md](https://obsidian.md/), as I am currently trying to integrate it into my weekly dungeons and dragons campaigns and am excited by the formatting capabilities available to me with the software. The star of today's show is not Obsidian however; our focus is on markdown. Markdown is "[a lightweight markup language for creating formatted text using a plain text editor](https://en.wikipedia.org/wiki/Markdown)". What this means for us is that we can write mostly normal looking (and thus very readable while drafting) posts that utilizes powerful and lightweight formatting to create structured and pretty blog posts! Writing in markdown is very easy to get started with even with no coding experience, so I recommend using it for anyone with similar goals as mine. It's such a well established standard used so widely that you can find incredible amounts of tooling and editors to enhance your markdown skills as you get accustomed to the language. 

### Web framework

Due to my want to utilize markdown and my aversion to front end development, I wanted something akin to a template, where I could just write my posts using markdown, and leave all the formatting to the templater. This led me to [Astro](https://astro.build/), an efficient web-framework for content heavy sites. If you don't know what that means, rest assured that I honestly don't really understand it either. I managed to work with it regardless though, so you will be able to as well. For our purposes here, you can think of it as a translator that we will feed our blogs in markdown, and it will output our beautiful website featuring our content.

### Theme

Astro isn't quite that plug and play to use, however. In order to get the simplicity I was looking for, I had to find a theme that I could use as a starting point. I found the beautiful theme you are currently looking at, [Astropaper by Sat Naing](https://astro.build/themes/details/astro-paper/), in the [community themes](https://astro.build/themes/) section of Astro's site. I recommend looking through some of the other ones available if you're not a particular fan of this theme. There's a huge collection of free ones, many which allow the same plug and play capabilities that Astropaper gave me.

In particular, Astropaper hosted three incredible features out of the box:
- Type-safe markdown (this really just means we can create our posts in markdown)
- Light & Dark mode support
- SEO-friendliness

I've gushed enough about markdown by this point and that bullet-point is fairly self-explanatory, so let's focus on the other two features. Light & Dark mode support just means I can theme my website to either have a dark background - which is my preference - or a light background - which is more standard and thus a good idea to include in your blog for accessibility purposes. More importantly though, the theme is SEO friendly, which means that your blog will be more likely to show up higher on the list when people search for it using something like Google or Bing.

### Deployment

Finally, to address one of the biggest mental roadblocks in creating a personal site, let's discuss how we can deploy our site. I use [github pages](https://pages.github.com/). Github pages is GitHub's solution to the exact problem we are trying to address of site hosting. It allows me to easily create a website that is clearly tied to my projects which are mainly coding-focused, and using it took the burden of maintenance and hosting off of my back due to how easily I could use templates to run everything through GitHub actions. Again, you don't really need to know how these things work, I'd be lying if I said I did. What is important here is that we are going to use something called GitHub pages to deploy our site, and this thing will allow us to launch and forget about our site until we want to update it. 

With that sorted, we now have all our tools ready to start tinkering, and to start writing.

## Implementation

So far, we've outlined a bunch of tools that I claim are going to help us create a simple blog. This section will focus on how we can put these tools together and what concrete steps I took to create this site.

## Downloading everything

Astro and Astropaper both integrate JavaScript/NodeJS (short for NodeJavaScript) package managers. What this means for us, is we need a NodeJS package manager to download everything we need. I used [**npm**](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm), but you can use either **pnpm** or **yarn**\* instead. I'm probably going to get hunted down by JavaScript devs for saying this, but we don't really need to care about how we're installing npm. Unfortunately for this blog post, I use Arch Linux on my home PC, so I am unfamiliar with the windows or mac installation process. The best I can guide you on this subject is to follow the instructions outlined on this [website](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm). I cannot guarantee and easy experience, but I can try helping if you have trouble with this step and contact me - I will gladly use the excuse to try and understand npm and node version managers better. For anyone who happens to use Arch or another Linux distribution, just follow any of the suggested installation methods on the [Arch wiki](https://wiki.archlinux.org/title/Node.js) or by using your distribution's suggested method.

With npm downloaded, we can now use npm to download astro and our theme in a single command (check [Astropaper's github](https://github.com/satnaing/astro-paper) if you are using pnpm or yarn). Before we do that, we have to select a folder to place our website's code/blog posts in. In my case, I have a folder/directory called "Projects" where I executed the following instructions. Open a terminal window in your chosen folder (sorry again windows and mac users), and run the following command:

```
npm create astro@latest -- --template satnaing/astro-paper
```

The above command will create a prompt in your terminal to create a new Astro project using Astropaper as a template. 
**MAKE SURE YOU ENABLE THIS PROJECT TO BE A GIT REPOSITORY**
Follow the prompts until finished, and you've now got a folder/directory that hosts all the information about your website! 

\* Be warned that I used yarn initially and ran into some issues during the deployment stage. I had no such issues with npm and suggest using that instead. 

## Personalizing the site

We are now going to remove a lot of the default content that comes with the theme, and replacing it with our own personal content. This section is going to be a bit heavy on adjusting the underlying code, but I promise you have to do zero actual coding to accomplish our goals. We're adjusting code, but we're not adjusting the underlying logic. Throughout this entire process, you can run the following command in your terminal in your website's folder/directory to get a link to a live feed of how your website is changing as you edit it:
```Shell
npm run dev
```

### Removing default posts

Now that we have our theme and Astro downloaded, we have to adjust the theme and personalize it to our content, style, and needs. Go into the folder/directory you just created, and delete the following files:
```
/
├── src/
│   ├── content/
│   │   |  blog/
│   │   |    └── adding-new-post.md
│   │   |    └── astro-paper-2.md
│   │   |    └── astro-paper-3.md
│   │   |    └── astro-paper-4.md
│   │   |    └── customizing-astropaper-theme-color-schemes.md
│   │   |    └── dynamic-og-images.md
│   │   |    └── example-draft-post.md
│   │   |    └── how-to-add-a-new-social-icon.md
│   │   |    └── how-to-add-an-estimated-reading-time.md
│   │   |    └── how-to-configure-astropaper-theme.md
│   │   |    └── how-to-connect-astro-paper-blog-with-forestry-cms.md
│   │   |    └── how-to-update-dependencies.md
│   │   |    └── portfolio-website-development.md
│   │   |    └── predefined-color-schemes.md
│   │   |    └── setting-dates-via-git-hooks.md
│   │   |    └── tailwind-typography.md
│   │   |    └── terminal-development.md
```

### Adjusting site metadata

Once that's done, open the file **src/config.ts** in your favorite text editor. In this file, you are going to be adjusting the site metadata (information about the site itself) so that people know that this is your website.

In particular, edit the content following block so that it instead describes your site. For the **website** parameter, just type **{user-name}.github.io** for now. In my case, that becomes **arya-ll.github.io**. Your website won't be accessible when you put that in your browser yet, but it will be by the end of this guide if you are following step by step. For reference, I posted my **SITE** block below the default one

- Default:
```ts
  export const SITE: Site = {
  website: "https://astro-paper.pages.dev/", // replace this with your deployed domain
  author: "Sat Naing",
  desc: "A minimal, responsive and SEO-friendly Astro blog theme.",
  title: "AstroPaper",
  ogImage: "astropaper-og.jpg",
  lightAndDarkMode: true,
  postPerPage: 3,
  scheduledPostMargin: 15 * 60 * 1000, // 15 minutes
};
```
- Mine:
```ts
  export const SITE: Site = {
  website: "https://Arya-LL.github.io", // replace this with your deployed domain
  author: "Arya Lyngdoh Lakshmanan",
  desc: "A collection of my mostly unfinished personal projects.",
  title: "A.L.L. my work",
  ogImage: "astropaper-og.jpg",
  lightAndDarkMode: true,
  postPerPage: 3,
  scheduledPostMargin: 15 * 60 * 1000, // 15 minutes
};
```

Additionally, be sure to review the **LOCALE** and **SOCIALS** sections.

### Changing default Intro page

The default intro text blurb for your new website is defined in the **src/pages/index.astro** file. Like the **config.ts** file, I'll paste the default below and what I changed mine to so you can do the same accordingly. The block of code I am referring to starts at line 22 and ends at line 58 in the default file.

- Default:
```html
<Layout>
  <Header />
  <main id="main-content">
    <section id="hero">
      <h1>Mingalaba</h1>
      <a
        target="_blank"
        href="/rss.xml"
        class="rss-link"
        aria-label="rss feed"
        title="RSS Feed"
      >
        <svg xmlns="http://www.w3.org/2000/svg" class="rss-icon"
          ><path
            d="M19 20.001C19 11.729 12.271 5 4 5v2c7.168 0 13 5.832 13 13.001h2z"
          ></path><path
            d="M12 20.001h2C14 14.486 9.514 10 4 10v2c4.411 0 8 3.589 8 8.001z"
          ></path><circle cx="6" cy="18" r="2"></circle>
        </svg>
        <span class="sr-only">RSS Feed</span>
      </a>

      <p>
        AstroPaper is a minimal, responsive, accessible and SEO-friendly Astro
        blog theme. This theme follows best practices and provides accessibility
        out of the box. Light and dark mode are supported by default. Moreover,
        additional color schemes can also be configured.
      </p>
      <p>
        Read the blog posts or check
        <LinkButton
          className="underline decoration-dashed underline-offset-4 hover:text-skin-accent"
          href="https://github.com/satnaing/astro-paper#readme"
        >
          README
        </LinkButton> for more info.
      </p>
```
- Default:
```html
<Layout>
  <Header />
  <main id="main-content">
    <section id="hero">
      <h1>Hi!</h1>
      <a
        target="_blank"
        href="/rss.xml"
        class="rss-link"
        aria-label="rss feed"
        title="RSS Feed"
      >
        <svg xmlns="http://www.w3.org/2000/svg" class="rss-icon"
          ><path
            d="M19 20.001C19 11.729 12.271 5 4 5v2c7.168 0 13 5.832 13 13.001h2z"
          ></path><path
            d="M12 20.001h2C14 14.486 9.514 10 4 10v2c4.411 0 8 3.589 8 8.001z"
          ></path><circle cx="6" cy="18" r="2"></circle>
        </svg>
        <span class="sr-only">RSS Feed</span>
      </a>

      <p>
        Welcome to my personal site. It is currently in development, so expect
        it to look and function different if you visit again. I aim to use this
        place to document my projects, most of which are in progress.
      </p>
      <p>Read the blog posts or check my socials for more.</p>
```

With that, you now have a personalized welcome blurb for all future visitors of your website!

### Changing default About page

The default about page tells you a lot about Astropaper, but let's change that to instead describe your new website. Again, I'll demonstrate what you need to change by pasting the default and then what I changed my about page to. The about page is located at **src/pages/about.md**, and we are functionally going to be editing the entire file.

- Default:
```markdown
---
layout: ../layouts/AboutLayout.astro
title: "About"
---

AstroPaper is a minimal, responsive and SEO-friendly Astro blog theme. I designed and crafted this based on [my personal blog](https://satnaing.dev/blog).

This theme is aimed to be accessible out of the box. Light and dark mode are supported by
default and additional color schemes can also be configured.

This theme is self-documented \_ which means articles/posts in this theme can also be considered as documentations. So, see the documentation for more info.

<div>
  <img src="/assets/dev.svg" class="sm:w-1/2 mx-auto" alt="coding dev illustration">
</div>

## Tech Stack

This theme is written in vanilla JavaScript (+ TypeScript for type checking) and a little bit of ReactJS for some interactions. TailwindCSS is used for styling; and Markdown is used for blog contents.

## Features

Here are certain features of this site.

- fully responsive and accessible
- SEO-friendly
- light & dark mode
- fuzzy search
- super fast performance
- draft posts
- pagination
- sitemap & rss feed
- highly customizable

If you like this theme, you can star/contribute to the [repo](https://github.com/satnaing/astro-paper).  
Or you can even give any feedback via my [email](mailto:contact@satnaing.dev).
```
- Mine:
```markdown
---
layout: ../layouts/AboutLayout.astro
title: "About"
---

Hi, my name is Arya Lyngdoh Lakshmanan. This website is a collection of my various projects, and possibly blog posts written just for the site. My projects are typically endeavors in data analytics, web development, and machine learning. My biggest current project for example is a home grown implementation of user-tailored neural network to create and maintain spotify playlists.
Most of my projects are open source and hosted on my [GitHub](https://github.com/Arya-LL).

If you enjoy any of what I've done or you want to contact me, please get in touch through [email](mailto:arya.l.lakshmanan@gmail.com).

## Tech Stack

Most of my work is done in Rust, which I learned through reading the incredible [rust book](https://doc.rust-lang.org/book/). I am aiming to use Rust as my primary language for all of my projects so I can gain experience with the language and learn through doing.

I also work extensively in Python and R, as I have the most past experience in data analytics with them, especially in the realms of academic analysis and finance/economics.

For data management, I use PostgreSQL and am learning alternative databases like SurrealDB.

Lastly, for project management, I use [Obsidian](https://obsidian.md) to organize my thoughts and develop high level goals.
```

### Adjusting the color schemes

Lastly, and most importantly for personalization, I needed to change the default color schemes to something that felt more tailored to my preferences. In order to figure out what color scheme you want to go with before setting one for your webpage, I suggest using the [trending palettes page on Coolors.co][https://coolors.co/palettes/trending] for inspiration. I used some palettes from there as inspiration for my dark theme palette, and I used the non-binary pride flag as inspiration for my light theme palette. Now that you have a paltette (and more importantly, the corresponding RGB color codes) in mind, let's implement the change in our website. The file we're editing this time is **src/styles/base.css**, from line 11 onward.
- Default:
```css
@layer base {
  :root,
  html[data-theme="light"] {
    --color-fill: 251, 254, 251;
    --color-text-base: 40, 39, 40;
    --color-accent: 0, 108, 172;
    --color-card: 230, 230, 230;
    --color-card-muted: 205, 205, 205;
    --color-border: 236, 233, 233;
  }
  html[data-theme="dark"] {
    --color-fill: 33, 39, 55;
    --color-text-base: 234, 237, 243;
    --color-accent: 255, 107, 1;
    --color-card: 52, 63, 96;
    --color-card-muted: 138, 51, 2;
    --color-border: 171, 75, 8;
  }
```
- Mine:
```css
@layer base {
  :root,
  html[data-theme="light"] {
    --color-fill: 229, 229, 229;
    --color-text-base: 58, 58, 58;
    --color-accent: 252, 163, 17;
    --color-card: 94, 84, 142;
    --color-card-muted: 35, 25, 66;
    --color-border: 20, 33, 61;
  }
  html[data-theme="dark"] {
    --color-fill: 74, 74, 72;
    --color-text-base: 241, 242, 235;
    --color-accent: 164, 194, 165;
    --color-card: 86, 98, 70;
    --color-card-muted: 66, 77, 52;
    --color-border: 241, 242, 235;
  }
```

Additionally, we can set the default color scheme to the dark color scheme by adjusting the first line in **src/toggle-theme.js**
- Default:
```js
const primaryColorScheme = ""; // "light" | "dark"
```
- Mine:
```js
const primaryColorScheme = "dark"; // "light" | "dark"
```

With all of that done, you finally have a completely personalized site to work with! All that's left is making your first post and deploying the site.

## Making a new post

Now, we can make our first post on our brand new personalized website. To do that, create a new file named **src/content/blog/first-post.md**

Now, before you get to writing, you need to include some properties or meta-data for your post so that your new website can use its tag functionality and direct visitors to the correct web addresses when interacting with your site. A sample properties section, that I used when creating my first post, is shown below.

```markdown
---
author: Arya Lyngdoh Lakshmanan
pubDatetime: 2024-01-27T23:38:50.459Z
title: First post
slug: first-post
featured: true
draft: false
tags:
  - Non-technical
  - Personal
description: A very first post introducing people to the website.
---
```

Below this, you can finally - as promised -  simply write your blog post in markdown.

## Deploying to github pages

Finally, we need to deploy your site to github pages. 

First, create the following new folders and file in your project folder/directory:
- **.github/**
- **.github/workflows/**
- **.github/workflows/astro.yml**

In **.github/workflows/astro.yml**, paste the following code block.

```yml
# Sample workflow for building and deploying an Astro site to GitHub Pages
#
# To get started with Astro see: https://docs.astro.build/en/getting-started/
#
name: Deploy Astro site to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["master"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

env:
  BUILD_PATH: "." # default value when not using subfolders
  # BUILD_PATH: subfolder

jobs:
  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Detect package manager
        id: detect-package-manager
        run: |
          if [ -f "${{ github.workspace }}/yarn.lock" ]; then
            echo "manager=yarn" >> $GITHUB_OUTPUT
            echo "command=install" >> $GITHUB_OUTPUT
            echo "runner=yarn" >> $GITHUB_OUTPUT
            exit 0
          elif [ -f "${{ github.workspace }}/package.json" ]; then
            echo "manager=npm" >> $GITHUB_OUTPUT
            echo "command=ci" >> $GITHUB_OUTPUT
            echo "runner=npx --no-install" >> $GITHUB_OUTPUT
            exit 0
          else
            echo "Unable to determine package manager"
            exit 1
          fi
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: "20"
          cache: ${{ steps.detect-package-manager.outputs.manager }}
          cache-dependency-path: ${{ env.BUILD_PATH }}/package-lock.json
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v4
      - name: Install dependencies
        run: ${{ steps.detect-package-manager.outputs.manager }} ${{ steps.detect-package-manager.outputs.command }}
        working-directory: ${{ env.BUILD_PATH }}
      - name: Build with Astro
        run: |
          ${{ steps.detect-package-manager.outputs.runner }} astro build \
            --site "${{ steps.pages.outputs.origin }}" \
            --base "${{ steps.pages.outputs.base_path }}"
        working-directory: ${{ env.BUILD_PATH }}
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ${{ env.BUILD_PATH }}/dist

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    needs: build
    runs-on: ubuntu-latest
    name: Deploy
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

That code block will tell GitHub to do two things whenever you update your blog files on GitHub. First, it will rebuild your website automatically with the new content, and second, it will make that site accessible at **{username}.github.io**. 

If you don't have a GitHub account, make one. Make a new repository by following [this guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository), making sure to name your repository **{username}.github.io**. Then, in a terminal in your project folder/directory, run the following command, making sure to replace {username} with your username:

```Shell
git remote add upstream https://github.com/{username}/{username}.github.io
```

Now, whenever you want to update your website, you just have to run
```Shell
git push
```
and your website will automatically update!

## Conclusion

Congratulations! I know there's been a lot of work to get to this point, but you now have everything set up and can happily just add blog posts while ignoring all the code we've addressed in this guide. If you instead want to tinker with the theme, the underlying Astro, and the markdown language more, here are some resources that I found helpful:
- [The astropaper github page](https://github.com/satnaing/astro-paper)
- [Astro's syntax guide](https://docs.astro.build/en/core-concepts/astro-syntax/)
- [Obsidian's markdown guide](https://help.obsidian.md/Editing+and+formatting/Basic+formatting+syntax)