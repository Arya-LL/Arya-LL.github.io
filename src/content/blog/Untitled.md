---
author: Arya Lyngdoh Lakshmanan
pubDatetime: 2024-01-27T23:38:50.459Z
title: Spotify Playlist Organizer Intro
slug: spotify-playlist-organizer-intro
featured: true
draft: true
tags:
  - Techincal
  - Personal
  - Spotify
  - Rust
description: An introduction to my definitely not convoluted spotify playlist organizer project
---
I was too lazy to maintain my spotify playlists, so here's an overview of a multi-month long project so I no longer have to spend a second maintaining my spotify playlists.

## Table of Contents

## What Even Is This or Overview

I listen to an odd variety of music. The music I listen to on my own when running or working is very different than the music I play in the car with friends or family. 

## Different Ways to Organize

### Mutual and Complete

The simplest and most intuitive way of turning our saved tracks into groups of playlists is by creating a bunch of playlists where every song in our saved tracks appears in exactly one of those playlists. In the language of set theory, we are partitioning the set of saved tracks.

> Partitioning our saved tracks means to map every element within the set of saved tracks to a non-empty subset. Each element is included in only one of these subsets.