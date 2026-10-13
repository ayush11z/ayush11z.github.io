---
layout: project
title: "Spotify Song Recommender"
description: A song recommendation engine that clusters tracks by audio features like danceability and energy to surface similar songs from your own Spotify library.
importance: 7
category: Software
stack: ["Python", "scikit-learn", "Spotipy", "Pandas"]
github: https://github.com/ayush11z/Spotify-song-recommender
summary: >-
  Most recommendation engines treat songs as opaque IDs, so I built one that recommends based on
  what a track actually sounds like. Using the Spotify Web API via Spotipy, the pipeline pulls
  tracks straight from a user's own playlists and library, then represents each one as a feature
  vector of danceability, energy, valence, tempo, acousticness, and other audio characteristics. A
  k-nearest-neighbors model over that feature space finds the closest-sounding tracks to any seed
  song, while a separate K-Means clustering step groups the library into natural sonic clusters for
  exploring by mood or vibe rather than title.
---

Most music recommendation systems lean on collaborative filtering — what similar listeners also played — which works well at scale but says nothing about why two songs actually sound alike. This project takes the opposite approach: cluster and recommend songs purely from their audio characteristics.

---

#### 🎧 Data & Feature Engineering

- **Spotify integration**: Used **Spotipy** to authenticate against the Spotify Web API and pull tracks directly from a user's own playlists and saved library.
- **Audio features**: Represented each track as a feature vector across danceability, energy, valence, tempo, acousticness, instrumentalness, liveness, speechiness, and loudness.
- **Preprocessing**: Scaled and normalized features before modeling, with a cosine-similarity pipeline (min-max scaling + L2 normalization) as the default and an alternative Euclidean/standardized path.

---

#### 🔍 Recommendation & Clustering

- **K-Nearest Neighbors**: Built a nearest-neighbors recommender that finds the closest-sounding tracks to any seed song, with fuzzy title matching so a partial song or artist name is enough to find the right seed.
- **K-Means clustering**: Clustered the full library into groups of sonically similar tracks, useful for browsing by mood or vibe instead of searching by name.

---

#### 🛠️ Tech Stack

Python, scikit-learn, Spotipy, Pandas, NumPy

---

#### 💡 Why It's Relevant

This was a chance to work hands-on with a real external API and turn unstructured audio metadata into a feature space a model could actually reason over, rather than relying on pre-packaged recommendation data.
