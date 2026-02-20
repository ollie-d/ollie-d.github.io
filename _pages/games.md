---
layout: archive
title: "Games"
permalink: /games/
author_profile: true
---

<p>You may find additional games on my <a href="https://ollie-d.itch.io" target="_blank" rel="noopener noreferrer">itch.io page</a>.</p>

<style>
.game-gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.game-item {
  text-align: center;
  /* Removed background, border, and padding for a clean look */
  background: transparent;
  transition: transform 0.2s;
}

.game-item:hover {
  transform: translateY(-5px);
  /* Optional: Add a glow to the image on hover instead of a box shadow */
  filter: drop-shadow(0 4px 6px rgba(0,0,0,0.2));
}

.game-item img {
  width: 100%;
  aspect-ratio: 315 / 250; 
  max-width: 315px; 
  height: auto;
  object-fit: cover;
  border-radius: 4px;
  margin-bottom: 8px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.game-title {
  font-weight: bold;
  font-size: 0.9em;
  display: block;
  line-height: 1.2;
  margin-top: 5px;
  color: inherit; /* Uses your site's default text color */
}

@media (max-width: 900px) {
  .game-gallery { grid-template-columns: repeat(2, 1fr); }
}
</style>



<div class="game-gallery">
  {% for game in site.data.games %}
    <div class="game-item">
      <a href="{{ game.url }}" target="_blank">
        <img src="{{ game.image }}" alt="{{ game.title }}">
        <span class="game-title">{{ game.title }}</span>
      </a>
    </div>
  {% endfor %}
</div>
