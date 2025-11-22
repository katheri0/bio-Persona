<script setup>
import { reactive } from 'vue'

// Clear, descriptive reactive object for the persona data
const persona = reactive({
  name: 'Maya / Sarah',
  age: '28',
  gender: 'Female',
  occupation: 'Software Engineer',
  location: 'San Francisco, CA',
  familyStatus: 'Single',
  photoUrl: '/src/assets/profile.jpg',
  photoUrlIcon: '/src/assets/icon.png',
  bio: 'Sarah is a tech enthusiast who is passionate about learning programming and expanding her knowledge in computer science. She enjoys solving complex problems and building innovative products.',
  motivations: 'Becoming proficient in CS, building career-ready projects, and collaborating with startups and nonprofits.',
  background:
    'Maya grew up in a multicultural household where creativity was always encouraged. After studying Computer Science at UT Austin, she worked in two agencies before going independent. She now collaborates with startups and nonprofits, helping them launch intuitive and human-centered digital products.',
  personality: {
    traits: 'Curious, detail-oriented, warm, energetic',
    communication: 'Clear, visual, collaborative',
    behaviors: 'Takes notes on everything; always prototyping ideas; loves brainstorming workshops'
  },
  quote: 'programming should feel like a conversation—clear, intuitive, and human.'
})
</script>

<template>
  <div class="persona-page">
    <header class="site-header">
      <div class="brand">BIO</div>
      <nav class="main-nav">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>
    <hr>
    <main>
      <section id="home" class="hero">
        <div class="hero-left">
          <div class="photo-card">
            <img :src="persona.photoUrl" :alt="persona.name + ' photo'" />
            <ul class="meta-list">
              <li><strong>Age/Gender</strong><span>{{ persona.age }} / {{ persona.gender }}</span></li>
              <li><strong>Occupation</strong><span>{{ persona.occupation }}</span></li>
              <li><strong>Location</strong><span>{{ persona.location }}</span></li>
              <li><strong>Family Status</strong><span>{{ persona.familyStatus }}</span></li>
            </ul>
          </div>
        </div>

        <div class="hero-right">
          <div class="bio-card">
            <h2>Bio</h2>
            <p>{{ persona.bio }}</p>

            <h3>Motivations</h3>
            <p>{{ persona.motivations }}</p>
          </div>
        </div>
      </section>

      <section class="highlights">
        <div class="highlight">To become proficient in CS concepts and advance her career in software development</div>
        <div class="highlight">Struggles with complex algorithms and finding time to balance work and learning</div>
        <div class="highlight">GitHub, Udemy courses</div>
      </section>
      <section class="boldhighlight">

        <div class="highlight"><b>Goals</b></div>
        <div class="highlight"><b>Struggle</b></div>
        <div class="highlight"><b>Brand Affiliation</b>s</div>
      </section>
      <br>
      <br>
      <br>
      <section id="about" class="brief">
        <div class="brief-card">
          <h1 class="center">Brief</h1>

          <h1>Background & Story</h1>
          <br>
          <p class="P">{{ persona.background }}</p>
          <br>
          <br>
          <br>
          <div class="two-col">
            <div class="per">
              <h1>Personality</h1>
              <p><strong>Traits:</strong> {{ persona.personality.traits }}</p>
              <p><strong>Communication Style:</strong> {{ persona.personality.communication }}</p>
              <p><strong>Behaviors:</strong> {{ persona.personality.behaviors }}</p>
            </div>
            <img style="scale: .5;" :src="persona.photoUrlIcon" alt="icon photo" />
          </div>

          <div class="quote-box">
            <h1>Quote</h1>
            <blockquote>“{{ persona.quote }}”</blockquote>
          </div>
        </div>
      </section>
    </main>
    <hr>
    <footer class="site-footer" id="contact">
      <div class="footer-left">© {{ new Date().getFullYear() }} — {{ persona.name }}</div>
      <div class="footer-right">GitHub · LinkedIn · Portfolio</div>
    </footer>
  </div>
</template>



<style scoped>
:root {
  --accent: #c9b8ff;
  --muted: #6b6b6b;
  --card-bg: #f5f3ff;
  --border: #e0dff7;
  --radius: 12px;
  --max-width: 980px;
}

* {
  box-sizing: border-box
}

body,
html,
#app {
  height: 100%;
  margin: 0;
  font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial
}

.persona-page {
  max-width: var(--max-width);
  margin: auto;
  padding: 18px
}

.site-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 8px;
  font-size: 24px;
}

.hero-right {
  font-size: 20px;
  background-color: #DEDEFD;
  border-radius: 24px;


}

.per {

  display: block;
  align-content: center;
  font-size: 20px;
}

blockquote {
  font-size: 20px;
}

.brand {
  background: #0f172a;
  color: white;
  padding: 10px 14px;
  border-radius: 999px;
  font-weight: 700
}

.main-nav a {
  margin-left: 12px;
  text-decoration: none;
  color: var(--muted)
}

.hero {
  display: grid;
  grid-template-columns: 1fr 1.7fr;
  gap: 20px;
  margin-top: 14px
}

.photo-card {
  background: var(--card-bg);
  padding: 12px;
  border-radius: var(--radius);
  border: 1px solid var(--border);
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #DEDEFD;
  border-radius: 30px;

}

.photo-card img {
  width: 220px;
  height: 220px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 6px 18px rgba(16, 24, 40, 0.08)
}

.meta-list {
  list-style: none;
  padding: 8px;
  margin: 12px 0 0 0;
  width: 100%
}

.meta-list li {
  display: flex;
  justify-content: space-between;
  padding: 6px 8px;
  font-size: 14px;
  color: var(--muted)
}

.bio-card {
  background-color: #DEDEFD;
  padding: 20px;
  border-radius: var(--radius);
  border: 1px solid var(--border);
  border-radius: 24px;
}

.bio-card h2 {
  margin: 0 0 8px 0
}

.bio-card h3 {
  margin-top: 12px
}

.highlights {
  display: flex;
  gap: 12px;
  justify-content: space-between;
  margin: 18px 0;
  height: 236px;
  text-align: center;
}

.boldhighlight {
  display: flex;
  gap: 12px;
  justify-content: space-between;
  margin: 28px 0;
  text-align: center;
}

.highlight {
  flex: 1;
  text-align: center;
  font-size: 20px;
  color: var(--muted);
  display: flex;
  justify-content: center;
  align-items: end;
}


.brief {
  margin-top: 12px
}

.brief-card {
  border: 1px solid var(--border);
  padding: 18px;
  border-radius: 10px;
  background: #fff
}

.brief-card h2 {
  margin-top: 0
}

.two-col {
  display: grid;
  grid-template-columns: 1fr 1.4fr;
  gap: 18px;
  margin-top: 12px
}

.quote-box {
  align-items: center;
  display: flex;
  justify-content: center;
}

.quote-box blockquote {
  font-style: italic;
  color: var(--muted);
  border-left: 3px solid var(--accent);
  padding-left: 10px;
  align-items: center;
  display: flex;
  justify-content: center;
}

.site-footer {
  display: flex;
  justify-content: space-between;
  padding: 14px 8px;
  margin-top: 18px;
  border-top: 1px solid var(--border);
  color: var(--muted);
  font-size: 13px
}

/* Responsive */
@media (max-width:880px) {
  .hero {
    grid-template-columns: 1fr;
  }

  .two-col {
    grid-template-columns: 1fr
  }

  .photo-card img {
    width: 160px;
    height: 160px
  }
}

.center {
  display: flex;
  justify-content: center;

}

.P {
  font-size: 20px;
  text-align: center;
}
</style>