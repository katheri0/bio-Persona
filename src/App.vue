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

      <section id="about" class="brief">
        <div class="brief-card">
          <h2>Brief</h2>

          <h3>Background & Story</h3>
          <p>{{ persona.background }}</p>

          <div class="two-col">
            <div>
              <h3>Personality</h3>
              <p><strong>Traits:</strong> {{ persona.personality.traits }}</p>
              <p><strong>Communication Style:</strong> {{ persona.personality.communication }}</p>
              <p><strong>Behaviors:</strong> {{ persona.personality.behaviors }}</p>
            </div>

            <div class="quote-box">
              <h3>Quote</h3>
              <blockquote>“{{ persona.quote }}”</blockquote>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="site-footer" id="contact">
      <div class="footer-left">© {{ new Date().getFullYear() }} — {{ persona.name }}</div>
      <div class="footer-right">GitHub · LinkedIn · Portfolio</div>
    </footer>
  </div>
</template>

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
  margin: 24px auto;
  padding: 18px
}

.site-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 8px
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
  grid-template-columns: 1fr 1.4fr;
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
  align-items: center
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
  background: white;
  padding: 20px;
  border-radius: var(--radius);
  border: 1px solid var(--border)
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
  margin: 18px 0
}

.highlight {
  flex: 1;
  text-align: center;
  font-size: 13px;
  color: var(--muted)
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
  grid-template-columns: 1fr 260px;
  gap: 18px;
  margin-top: 12px
}

.quote-box blockquote {
  font-style: italic;
  color: var(--muted);
  border-left: 3px solid var(--accent);
  padding-left: 10px
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
</style>