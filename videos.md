---
layout: page
title: Video Gallery
---

<div class="video-gallery">
  {% for video in site.data.videos.videos %}
  <div class="video-item">
    <h3>{{ video.title }}</h3>
    <div class="video-container">
      <iframe width="100%" height="400" 
        src="https://www.youtube.com/embed/{{ video.youtube_id }}" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
      </iframe>
    </div>
    <p>{{ video.description }}</p>
  </div>
  {% endfor %}
</div>

<style>
.video-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 30px;
  margin: 40px 0;
}

.video-item {
  background: #f8f9fa;
  padding: 20px;
  border-radius: 8px;
}

.video-container {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
}

.video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>