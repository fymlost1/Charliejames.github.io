<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Charlie James | Portfolio</title>
  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      margin: 0;
      background: #121212;
      color: #eaeaea;
      line-height: 1.6;
    }

    header {
      background: linear-gradient(135deg, #1f1f1f, #2a2a2a);
      color: #fff;
      padding: 3rem 2rem;
      text-align: center;
      position: relative;
      box-shadow: 0 4px 10px rgba(0,0,0,0.5);
    }
    header h1 { color: #ff6b6b; margin: 0; font-size: 2.5rem; }
    header p { color: #ccc; font-size: 1.2rem; }

/* Hamburger */
    .hamburger {
      position: fixed;   /* stays visible while scrolling */
      top: 20px;
      left: 20px;
      width: 30px;
      height: 22px;
      cursor: pointer;
      z-index: 2000;     /* above everything */
    }
    .hamburger span {
      display: block;
      height: 4px;
      background: #ff6b6b;
      margin: 5px 0;
      border-radius: 2px;
      transition: 0.3s;
    }
    /* Animate to X */
    .hamburger.active span:nth-child(1) {
      transform: rotate(45deg) translate(5px, 5px);
    }
    .hamburger.active span:nth-child(2) {
      opacity: 0;
    }
    .hamburger.active span:nth-child(3) {
      transform: rotate(-45deg) translate(6px, -6px);
    }

    /* Side menu */
    .side-menu {
      position: fixed;
      top: 0;
      left: -250px;
      width: 250px;
      height: 100%;
      background: #1e1e1e;
      padding: 2rem 1rem;
      box-shadow: 2px 0 10px rgba(0,0,0,0.5);
      transition: left 0.3s ease;
      z-index: 1000;
    }
    .side-menu.active { left: 0; }
    .side-menu h3 { color: #ff6b6b; }
    .side-menu a {
      display: block;
      color: #eaeaea;
      text-decoration: none;
      margin: 1rem 0;
    }
    .side-menu a:hover { color: #ff6b6b; }

    section { padding: 2rem; max-width: 1000px; margin: auto; }
    section h2 { color: #ff6b6b; border-bottom: 2px solid #ff6b6b; display: inline-block; }

    .projects {
      max-height: 500px;
      overflow-y: auto;
      cursor: grab;
      scrollbar-width: none;
    }
    .projects::-webkit-scrollbar { display: none; }
    .project {
  background: #1e1e1e;
  padding: 2rem;
  margin-bottom: 2rem;
  border-radius: 10px;
  min-height: 750px;
  font-size: 1.1rem;
  user-select: none;   /* 🚫 disables text selection */
  -webkit-user-select: none; /* Safari/Chrome */
  -moz-user-select: none;    /* Firefox */
  -ms-user-select: none;     /* IE/Edge */
}
    .project h3 { color: #ff6b6b; }

    footer { background: #1a1a1a; text-align: center; padding: 1rem; color: #777; }
  </style>
</head>
<body>
  <!-- Side Menu -->
  <div class="side-menu" id="sideMenu">
    <h3>Navigation</h3>
    <a href="https://github.com/" target="_blank">GitHub</a>
    <a href="https://linkedin.com/" target="_blank">LinkedIn</a>
    <a href="https://twitter.com/" target="_blank">Twitter</a>
    <a href="https://dribbble.com/" target="_blank">Dribbble</a>
  </div>

  <header>
    <!-- Hamburger Icon -->
    <div class="hamburger" id="hamburger">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <h1>Charlie James</h1>
    <p>Creative Developer | Designer | Problem Solver</p>
  </header>

  <section>
    <h2>About Me</h2>
    <p>Write a short bio here about who you are and what you do.</p>
  </section>

  <section>
    <h2>Projects</h2>
    <div class="projects" id="projects">
      <div class="project"><h3>Project One</h3><p>Description of your project.</p></div>
      <div class="project"><h3>Project Two</h3><p>Description of your project.</p></div>
      <div class="project"><h3>Project Three</h3><p>Description of your project.</p></div>
    </div>
  </section>

  <section>
    <h2>Contact</h2>
    <p>Email: <a href="mailto:you@example.com">you@example.com</a></p>
  </section>

  <footer>
    <p>© 2025 Charlie James</p>
  </footer>

  <script>
    // Hamburger toggle
    const hamburger = document.getElementById('hamburger');
    const sideMenu = document.getElementById('sideMenu');

    hamburger.addEventListener('click', () => {
      hamburger.classList.toggle('active');
      sideMenu.classList.toggle('active');
    });

    // Click-and-drag scroll for projects
    const projects = document.getElementById('projects');
    let isDown = false, startY, scrollTop;

    projects.addEventListener('mousedown', (e) => {
      isDown = true;
      startY = e.pageY - projects.offsetTop;
      scrollTop = projects.scrollTop;
    });
    projects.addEventListener('mouseleave', () => isDown = false);
    projects.addEventListener('mouseup', () => isDown = false);
    projects.addEventListener('mousemove', (e) => {
      if (!isDown) return;
      e.preventDefault();
      const y = e.pageY - projects.offsetTop;
      const walk = (y - startY) * 1.5;
      projects.scrollTop = scrollTop - walk;
    });
  </script>
</body>
</html>
