<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Janice | Portfolio</title>
  <style>
    :root {
      --gold: #d4af37;
      --rose-pink: rgba(255, 228, 232, 0.5);
      --text-color: #222;
      --background-light: var(--rose-pink);
      --background-dark: #111;
      --text-dark: #fff;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: var(--background-light);
      color: var(--text-color);
      transition: background 0.5s ease, color 0.5s ease;
    }

    .border-wrapper {
      border: double medium var(--gold);
      padding: 1rem;
      margin: 1rem;
    }

    header nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .nav-links {
      list-style: none;
      display: flex;
      gap: 1rem;
    }

    .nav-links a {
      text-decoration: none;
      color: inherit;
      font-weight: bold;
    }

    .hero {
      text-align: center;
      padding: 2rem 0;
    }

    .headshot {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      border: 4px double var(--gold);
    }

    section {
      margin: 2rem 0;
    }

    .project-gallery {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .project {
      width: 200px;
      transition: transform 0.3s ease;
      cursor: pointer;
    }

    .project:hover {
      transform: scale(1.05);
    }

    .project img {
      width: 100%;
      border: 2px solid var(--gold);
    }

    article {
      margin-bottom: 1rem;
    }

    blockquote {
      border-left: 4px solid var(--gold);
      padding-left: 1rem;
      font-style: italic;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      max-width: 400px;
    }

    input, textarea, button {
      padding: 0.5rem;
      font-size: 1rem;
    }

    button {
      background-color: var(--gold);
      color: white;
      border: none;
      cursor: pointer;
    }

    #chatbox {
      max-width: 400px;
      border: 2px solid var(--gold);
      padding: 1rem;
    }

    .chatlog {
      height: 150px;
      overflow-y: auto;
      margin-bottom: 0.5rem;
      background: white;
      padding: 0.5rem;
    }

    #modeToggle {
      background: none;
      border: 2px solid var(--gold);
      border-radius: 50%;
      padding: 0.5rem;
      font-size: 1rem;
      cursor: pointer;
    }

    body.dark-mode {
      background-color: var(--background-dark);
      color: var(--text-dark);
    }
  </style>
  <script defer>
    document.addEventListener('DOMContentLoaded', () => {
      const toggle = document.getElementById('modeToggle');
      toggle.addEventListener('click', () => {
        document.body.classList.toggle('dark-mode');
        toggle.textContent = document.body.classList.contains('dark-mode') ? '☀️' : '🌙';
      });

      window.sendMessage = function () {
        const input = document.getElementById('userInput');
        const log = document.querySelector('.chatlog');
        const userText = input.value.trim();
        if (userText) {
          const userMessage = document.createElement('div');
          userMessage.textContent = `You: ${userText}`;
          log.appendChild(userMessage);

          const botMessage = document.createElement('div');
          botMessage.textContent = `Janice Bot: Thanks for your message! I'll get back to you soon.`;
          log.appendChild(botMessage);

          input.value = '';
          log.scrollTop = log.scrollHeight;
        }
      };
    });
  </script>
</head>

<body>
  <div class="border-wrapper">
    <header>
      <nav>
        <h1 class="logo">Janice</h1>
        <ul class="nav-links">
          <li><a href="#about">About Me</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#blog">Blog</a></li>
          <li><a href="#testimonials">Testimonials</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
        <button id="modeToggle">🌙</button>
      </nav>
    </header>

    <section class="hero">
      <img src="janice pic.jpg" alt="Professional Headshot" class="headshot" />
      <h2>Janice</h2>
      <p>Innovative | Technical | Artistic</p>
    </section>

    <section id="about">
      <h2>About Me</h2>
      <p>Hello! I'm Janice, an 18-year-old B.Tech student specializing in Computer Science with Cloud Computing. I am deeply passionate about programming, coding, and web designing, and I love exploring creative ways to merge technology with design. Alongside my technical interests, I have a strong artistic side—I enjoy drawing and painting—and I aspire to integrate these skills to create visually appealing and innovative digital experiences. My goal is to combine my technical expertise with my creativity to build solutions that captivate and engage people.Excited to learn, grow, and contribute to the world of tech and design! 🚀🎨.</p>
    </section>

    <section id="projects">
      <h2>Projects</h2>
      <div class="project-gallery">
        <div class="project" title="An artistic portfolio web app">
          <img src="project1.jpg" alt="Project 1 Thumbnail" />
          <p>Art Portfolio Website</p>
        </div>
        <div class="project" title="A storytelling blog with custom UI">
          <img src="project2.jpg" alt="Project 2 Thumbnail" />
          <p>Story Blog Design</p>
        </div>
        <div class="project" title="UI/UX redesign of a mobile app">
          <img src="project3.jpg" alt="Project 3 Thumbnail" />
          <p>App UI Redesign</p>
        </div>
      </div>
    </section>

    <section id="blog">
      <h2>Blog</h2>
      <article>
        <h3>Designing with Emotion</h3>
        <p>Emotion-driven design is what makes users stay. In this post, I talk about how storytelling and visual harmony come together in great UX design.</p>
      </article>
      <article>
        <h3>Color Palettes that Speak</h3>
        <p>Choosing the right palette isn't just aesthetic—it's psychology. Here's how I approach color in my creative process.</p>
      </article>
    </section>

    <section id="testimonials">
      <h2>Testimonials</h2>
      <blockquote>
        "Janice's portfolio is a reflection of her passion. Her design sense is impeccable and working with her was a joy."
        <footer>— Aditi Rao, UX Designer</footer>
      </blockquote>
      <blockquote>
        "Her creativity and dedication are unmatched. Highly recommended!"
        <footer>— Rahul Mehta, Project Manager</footer>
      </blockquote>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <form>
        <input type="text" name="name" placeholder="Your Name" required />
        <input type="email" name="email" placeholder="Your Email" required />
        <textarea name="message" placeholder="Your Message" required></textarea>
        <button type="submit">Send Message</button>
      </form>
    </section>

    <section id="chatbot">
      <h2>Chat with Me</h2>
      <div id="chatbox">
        <div class="chatlog"></div>
        <input type="text" id="userInput" placeholder="Type your message..." />
        <button onclick="sendMessage()">Send</button>
      </div>
    </section>
  </div>
</body>

</html>
