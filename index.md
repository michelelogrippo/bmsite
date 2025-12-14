---
layout: page
---
<!-- Header -->
{% include header.html %}

<!-- Render sections in order -->
{% assign locale = site.locale | default: 'en' %}
{% assign sitetext = site.data.sitetext[locale] %}

<!-- Servizi Section -->
{% if sitetext.servizi %}
  <section class="page-section" id="servizi">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">{{ sitetext.servizi.title }}</h2>
          <h3 class="section-subheading text-muted">{{ sitetext.servizi.text }}</h3>
        </div>
      </div>
      <div class="row text-center">
        {% for service in sitetext.servizi.list %}
          <div class="col-md-3">
            <span class="fa-stack fa-4x">
              <i class="fas fa-circle fa-stack-2x text-primary"></i>
              <i class="fas {{ service.icon }} fa-stack-1x fa-inverse"></i>
            </span>
            <h4 class="service-heading">{{ service.title }}</h4>
            <p class="text-muted">{{ service.desc }}</p>
          </div>
        {% endfor %}
      </div>
    </div>
  </section>
{% endif %}

<!-- Video Section -->
{% if sitetext.video %}
  <section class="page-section bg-light" id="video">
    <div class="container">
      <div class="text-center">
        <h2 class="section-heading text-uppercase">{{ sitetext.video.title }}</h2>
        <h3 class="section-subheading text-muted">{{ sitetext.video.text }}</h3>
      </div>
      <div class="row">
        <div class="col-lg-10 mx-auto">
          <div class="playlist-container">
            <iframe 
              width="100%" 
              height="500"
              src="https://www.youtube.com/embed/videoseries?list={{ sitetext.video.playlist.playlist_id }}" 
              frameborder="0" 
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
              allowfullscreen>
            </iframe>
          </div>
        </div>      
        <!-- {% for video in sitetext.video.videos %}
          <div class="col-md-4 col-sm-6 mb-5">
            <div class="video-item">
              <div class="video-container">
                <iframe 
                  width="100%" 
                  height="250"
                  src="https://www.youtube.com/embed/{{ video.youtube_id }}" 
                  frameborder="0" 
                  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                  allowfullscreen>
                </iframe>
              </div>
              <div class="video-caption">
                <h4>{{ video.title }}</h4>
                <p class="text-muted">{{ video.description }}</p>
              </div>
            </div>
          </div>
        {% endfor %} -->
      </div>
    </div>
  </section>
{% endif %}

<!-- Audio Section -->
{% if sitetext.audio %}
  <section class="page-section" id="audio">
    <div class="container">
      <div class="text-center">
        <h2 class="section-heading text-uppercase">{{ sitetext.audio.title }}</h2>
        <h3 class="section-subheading text-muted">{{ sitetext.audio.text }}</h3>
      </div>
      <div class="row">
        {% for item in sitetext.audio.items %}
          <div class="col-md-4 col-sm-6 mb-5">
            <div class="audio-item">
              <!-- aggiungi qui il contenuto audio -->
              <h4>{{ item.title }}</h4>
              <p class="text-muted">{{ item.description }}</p>
            </div>
          </div>
        {% endfor %}
      </div>
    </div>
  </section>
{% endif %}


  <!-- Bio Section -->
  {% if sitetext.bio %}
    <section class="page-section bg-light" id="bio">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h2 class="section-heading text-uppercase">{{ sitetext.bio.title }}</h2>
            <h3 class="section-subheading text-muted">{{ sitetext.bio.text }}</h3>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-12 mx-auto">
            {{ sitetext.bio.body }}
          </div>
        </div>
        <div class="row">
          <div class="col-lg-6 mx-auto">
            <div class="contact-box">
              <h4>Contattami<br/>
                <a href="mailto:info@biancamicheletti.it">info@biancamicheletti.it</a>
              </h4>
            </div>
          </div>
        </div>
      </div>
    </section>
  {% endif %}

<style>
  .contact-box {
  background-color: #ab40d5;
  color: white;
  padding: 40px;
  border-radius: 8px;
  text-align: center;
}

.contact-box h4 {
  color: white;
  margin-bottom: 20px;
  font-size: 1.5rem;
  font-weight: bold;
}

.contact-box p {
  margin: 0;
  font-size: 1.1rem;
}

.contact-box a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.contact-box a:hover {
  text-decoration: underline;
}    

.video-container {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  border-radius: 8px;
  margin-bottom: 15px;
  background: #f8f9fa;
}

.video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 8px;
}

.video-caption h4 {
  margin-top: 15px;
  font-weight: bold;
}

.video-caption p {
  font-size: 0.9rem;
  margin: 0;
}

#mainNav {
    background-color: #ab40d5 !important;
}


#pagecontainer {
  width: 100%;
  max-width: none;            /* neutralizza i max-width responsive */
  padding-left: 0;
  padding-right: 0;
  margin-left: 0;
  margin-right: 0;
  box-sizing: border-box;
  padding-top: 0;
}

#mainNav .navbar-nav .nav-item .nav-link.active, #mainNav .navbar-nav .nav-item .nav-link:hover {
    color: #ffffffff;
    font-weight:bold;
}

.intro-heading {
  text-shadow: 1px 1px 0px #ccc, 2px 2px 0px #050202, 2px 7px 5px #ab40d5;
  font-size:10vh;
}

.intro-lead-in {
  text-shadow: 2px 3px 2px #323131;
}




@media (min-width: 1200px) {
    .container:not(#pagecontainer) {
        max-width: 75rem;
    }

    header.masthead {
      height:100vh;
    }
}
</style>