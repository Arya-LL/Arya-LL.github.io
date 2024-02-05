---
author: Arya Lyngdoh Lakshmanan
pubDatetime: 2024-01-30T19:04:28.969Z
title: Spotify Playlist Manager
slug: spotify-playlist-manager
featured: true
draft: true
tags:
  - Personal
  - Techincal
  - Markdown
  - Guide
description: I decided maintaining a few spotify playlists was too much effort so I learned a low-level programming language to create a neural network playlist creator and organizer.
layout:
---
I decided maintaining a few spotify playlists was too much effort so I learned a low-level programming language to create a neural network playlist creator and organizer. The source code for this project is available [here!](https://www.github.com/Arya-LL/Spotify-Playlists)

## Table of Contents

## Project Overview

### Problem being addressed

I am not a fan of Spotify's recommendation methods. I especially wish I could have auto-generated playlists that only include the songs from my library of liked songs, rather than spotify's recommended mixes which include both songs from my library and suggested songs. 

To be specific about the problem I am trying to address and how my tool will fix it, consider the following situation I frequently find myself in.

My music taste is fairly bimodal, where I really like singing along to songs that fall into or near the indie rock genre, and I also really like blasting hyperpop and breakcore while I work or go on runs. For anyone unfamiliar with these genres, they are characterized by dissonant and incredibly loud sections.

Because my music taste isn't unimodal, I can't just have one big playlist and put it on shuffle. If I'm in the car with friends, I'm skipping all the breakcore and hyperpop. If I'm trying to hunker down and burn through work, I'm skipping all the indie rock songs. I also always inevitably get tired of maintaining multiple playlists, and am now left with a huge graveyard of unused playlists.

## How to solve the problem

This project is my attempt at creating a tool that creates the auto-generated playlists of my dreams, with an added bonus of being a playlist maintainer. Once set up, a user can just add songs to their liked songs and my playlist manager will auto-sort those songs into the correct playlist.

A simple solution to this would be to create playlists split by genre, where we create one playlist for each genre (or user defined genre grouping) found in the liked songs. This approach, however, was not granular enough for me and I would disagree with some of the classifications.

I realized that coming up with a fixed set of rules to classify these songs was not going to work, and that classifying music based on "vibes" required a much more adaptable classification system which used variables I could not even consider. I looked to neural networks to address this issue instead.

A neural network is a classification algorithm which is first trained with training data items where we provide both our input data, and a label for how we would classify that item. The algorithm is trained using this data to refine what weights it assigns to each factor we provide in the data associated with each item. For our music tracks, our trained algorithm might assign a large negative weight to really high beats per minute when deciding if a song should be classified as a good group song, resulting in songs with a high beats per minute being put in the solo category. 

A drawback of this method is we would need user input to generate the labels for the training data, removing our dreams of creating a fully automated playlist manager. The huge benefit in return here is the algorithm would be adaptable to the dataset we apply it to, and thus can be personalized for each user's listening tastes. I decided this tradeoff was worth it and set to implementing a program that trained and returned a neural network to classify these songs into user specified playlists with minimal user input.


## Tech Stack

### tl;dr

- Rust for literally everything
- Tokio for asynchronous runtime
- SQLite for database management
- burn for constructing the neural network
### What is Rust and why?

I chose to implement this project using pure Rust, a low-level programming language that most relevantly offers incredible speed advantages when compared to traditional data science languages like Python. Training a neural network is a computationally intensive process, and I figured the more efficient I can make that, the better shot I have on making an app with widespread applicability instead of just something only I would use. My hope is the resulting app will be quick enough to genuinely offer an improvement for people rather than the app just being the result of my long-winded coding exercise.

Further, I wanted to conduct a long-winded coding exercise. My background in applied statistics was limited to academic projects - even outside of the classroom. I am determined to transfer these experiences from a purely academic context to a more generally practical purpose. I taught myself the Rust programming language by reading through the incredible [Rust Book](https://www.rust-lang.com/book) and engaging in smaller projects using the language. I am yet however to implement a large project that requires planning and library development, and I aim to use this project to develop and showcase those skills.