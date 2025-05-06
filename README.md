<!DOCTYPE html>
<html>
<body>
<div id="profile-container" style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
  <style>
    /* Animations */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0px); }
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    @keyframes slideIn {
      from { transform: translateX(-30px); opacity: 0; }
      to { transform: translateX(0); opacity: 1; }
    }
    
    /* Main Styles */
    .profile-container {
      max-width: 1000px;
      margin: 0 auto;
      animation: fadeIn 1s ease-out;
    }
    .header {
      background: linear-gradient(135deg, #2b5876 0%, #4e4376 100%);
      border-radius: 20px;
      padding: 30px;
      margin-bottom: 30px;
      color: white;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      position: relative;
      overflow: hidden;
    }
    .header:before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Cpath fill='%23ffffff' fill-opacity='0.05' d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z'%3E%3C/path%3E%3C/svg%3E");
    }
    .name {
      font-size: 48px;
      font-weight: 700;
      margin: 0;
      text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
    }
    .tagline {
      font-size: 18px;
      margin-top: 10px;
      margin-bottom: 20px;
      opacity: 0.9;
      max-width: 80%;
      line-height: 1.6;
    }
    .section {
      background: #ffffff;
      border-radius: 15px;
      padding: 25px;
      margin-bottom: 25px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
      animation: fadeIn 1s ease-out;
    }
    .section-title {
      font-size: 24px;
      font-weight: 600;
      margin-top: 0;
      margin-bottom: 20px;
      color: #2b5876;
      display: flex;
      align-items: center;
    }
    .section-title:after {
      content: "";
      flex: 1;
      height: 1px;
      background: linear-gradient(to right, #2b5876, transparent);
      margin-left: 15px;
    }
    .highlight-box {
      display: inline-block;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      border-radius: 50px;
      padding: 7px 15px;
      font-size: 14px;
      font-weight: 500;
      margin-right: 8px;
      margin-bottom: 8px;
      transition: all 0.3s ease;
      animation: pulse 2s infinite;
    }
    .highlight-box:hover {
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }
    .grid-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: all 0.3s ease;
    }
    .grid-item:hover {
      transform: translateY(-5px);
    }
    .grid-item img {
      width: 50px;
      height: 50px;
      margin-bottom: 8px;
    }
    .grid-item span {
      font-size: 12px;
      text-align: center;
      color: #555;
    }
    .info-item {
      display: flex;
      align-items: flex-start;
      margin-bottom: 15px;
      animation: slideIn 0.5s ease-out;
    }
    .info-icon {
      width: 24px;
      margin-right: 15px;
      color: #4e4376;
    }
    .info-content {
      flex: 1;
    }
    .info-title {
      font-weight: 600;
      margin: 0;
      color: #333;
    }
    .info-desc {
      margin: 5px 0 0 0;
      color: #666;
    }
    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      margin-top: 20px;
    }
    .social-link {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 45px;
      height: 45px;
      border-radius: 50%;
      background: #f5f5f5;
      color: #444;
      transition: all 0.3s ease;
    }
    .social-link:hover {
      transform: scale(1.1);
      background: linear-gradient(135deg, #2b5876 0%, #4e4376 100%);
      color: white;
    }
    .stats {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      margin-top: 15px;
    }
    .stat-item {
      flex: 1;
      min-width: 150px;
      background: #f9f9f9;
      border-radius: 10px;
      padding: 15px;
      text-align: center;
      transition: all 0.3s ease;
    }
    .stat-item:hover {
      background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    }
    .stat-value {
      font-size: 24px;
      font-weight: 700;
      color: #2b5876;
      margin: 0;
    }
    .stat-label {
      font-size: 14px;
      color: #666;
      margin: 5px 0 0 0;
    }
    .projects {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }
    .project-card {
      background: #f9f9f9;
      border-radius: 12px;
      overflow: hidden;
      transition: all 0.3s ease;
    }
    .project-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    }
    .project-color {
      height: 8px;
      background: linear-gradient(90deg, #4e4376, #2b5876);
    }
    .project-content {
      padding: 20px;
    }
    .project-title {
      margin: 0 0 10px 0;
      font-size: 18px;
      font-weight: 600;
      color: #333;
    }
    .project-desc {
      margin: 0;
      font-size: 14px;
      color: #666;
      line-height: 1.5;
    }
    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 15px;
    }
    .project-tech-item {
      background: #e9ecef;
      border-radius: 50px;
      padding: 5px 10px;
      font-size: 12px;
      color: #495057;
    }
    .footer {
      text-align: center;
      color: #666;
      margin-top: 30px;
      font-size: 14px;
    }
    .wave {
      animation: float 3s ease-in-out infinite;
      display: inline-block;
      transform-origin: 70% 70%;
    }
    
    @media (max-width: 768px) {
      .header {
        padding: 20px;
      }
      .name {
        font-size: 36px;
      }
      .tagline {
        font-size: 16px;
        max-width: 100%;
      }
      .grid {
        grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
      }
      .projects {
        grid-template-columns: 1fr;
      }
    }
  </style>

  <div class="profile-container">
    <!-- Header Section -->
    <div class="header">
      <h1 class="name">Yasser Al-Ariqi <span class="wave">👋</span></h1>
      <p class="tagline">Full Stack Developer crafting responsive, user-focused web applications with modern technologies and clean code architecture.</p>
      <div style="display: flex; flex-wrap: wrap; gap: 10px; margin-top: 25px;">
        <div class="highlight-box">React.js Expert</div>
        <div class="highlight-box">JavaScript Wizard</div>
        <div class="highlight-box">UI/UX Enthusiast</div>
        <div class="highlight-box">PHP/Laravel Developer</div>
      </div>
    </div>

    <!-- About Me Section -->
    <div class="section">
      <h2 class="section-title">About Me</h2>
      <p style="line-height: 1.7; color: #444;">
        I'm a passionate Full Stack Developer who thrives on building elegant, efficient web solutions. With a strong foundation in both frontend and backend technologies, I bring a holistic approach to software development. I'm committed to writing clean, maintainable code and creating intuitive user experiences that solve real problems.
      </p>
      
      <div style="margin-top: 25px;">
        <div class="info-item">
          <div class="info-icon">🔭</div>
          <div class="info-content">
            <h4 class="info-title">Currently Working On</h4>
            <p class="info-desc">My Portfolio Website - showcasing my skills and projects with modern technologies</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">🌱</div>
          <div class="info-content">
            <h4 class="info-title">Currently Learning</h4>
            <p class="info-desc">Laravel, Advanced React Patterns, and TypeScript</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">👯</div>
          <div class="info-content">
            <h4 class="info-title">Looking to Collaborate On</h4>
            <p class="info-desc">Open Source Next.js Projects</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">💬</div>
          <div class="info-content">
            <h4 class="info-title">Ask Me About</h4>
            <p class="info-desc">Frontend best practices, React optimization, and responsive design</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">📫</div>
          <div class="info-content">
            <h4 class="info-title">How to Reach Me</h4>
            <p class="info-desc">yaaser10esam1010@gmail.com</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">📄</div>
          <div class="info-content">
            <h4 class="info-title">My Experiences</h4>
            <p class="info-desc"><a href="https://drive.google.com/file/d/1EGaIIsYV_5qNyQue-bwbmk-FQxi5_SFn/view?usp=sharing" style="color: #2b5876; text-decoration: none; font-weight: 500;">View My Resume</a></p>
          </div>
        </div>
      </div>
    </div>

    <!-- Skills Section -->
    <div class="section">
      <h2 class="section-title">Skills & Technologies</h2>
      
      <div style="margin-bottom: 20px;">
        <h3 style="margin: 0 0 15px 0; font-size: 18px; color: #444;">Frontend Development</h3>
        <div style="display: flex; flex-wrap: wrap; gap: 8px;">
          <div class="highlight-box">JavaScript</div>
          <div class="highlight-box">React.js</div>
          <div class="highlight-box">Next.js</div>
          <div class="highlight-box">TypeScript</div>
          <div class="highlight-box">HTML5</div>
          <div class="highlight-box">CSS3</div>
          <div class="highlight-box">SASS</div>
          <div class="highlight-box">Tailwind CSS</div>
          <div class="highlight-box">Bootstrap</div>
        </div>
      </div>
      
      <div style="margin-bottom: 20px;">
        <h3 style="margin: 0 0 15px 0; font-size: 18px; color: #444;">Backend Development</h3>
        <div style="display: flex; flex-wrap: wrap; gap: 8px;">
          <div class="highlight-box">PHP</div>
          <div class="highlight-box">Laravel</div>
          <div class="highlight-box">MySQL</div>
          <div class="highlight-box">REST API</div>
          <div class="highlight-box">Firebase</div>
        </div>
      </div>
      
      <div style="margin-bottom: 20px;">
        <h3 style="margin: 0 0 15px 0; font-size: 18px; color: #444;">Tools & Others</h3>
        <div style="display: flex; flex-wrap: wrap; gap: 8px;">
          <div class="highlight-box">Git</div>
          <div class="highlight-box">Docker</div>
          <div class="highlight-box">Webpack</div>
          <div class="highlight-box">Jest</div>
          <div class="highlight-box">Figma</div>
          <div class="highlight-box">AWS</div>
          <div class="highlight-box">Postman</div>
        </div>
      </div>
      
      <div>
        <h3 style="margin: 0 0 15px 0; font-size: 18px; color: #444;">Programming Languages</h3>
        <div style="display: flex; flex-wrap: wrap; gap: 8px;">
          <div class="highlight-box">JavaScript</div>
          <div class="highlight-box">TypeScript</div>
          <div class="highlight-box">PHP</div>
          <div class="highlight-box">Python</div>
          <div class="highlight-box">Java</div>
          <div class="highlight-box">C++</div>
        </div>
      </div>
    </div>

    <!-- Featured Projects -->
    <div class="section">
      <h2 class="section-title">Featured Projects</h2>
      
      <div class="projects">
        <div class="project-card">
          <div class="project-color"></div>
          <div class="project-content">
            <h3 class="project-title">FinBiz UI</h3>
            <p class="project-desc">A modern React.js financial business website with responsive design and dynamic content management.</p>
            <div class="project-tech">
              <span class="project-tech-item">React.js</span>
              <span class="project-tech-item">JavaScript</span>
              <span class="project-tech-item">CSS</span>
            </div>
          </div>
        </div>
        
        <div class="project-card">
          <div class="project-color"></div>
          <div class="project-content">
            <h3 class="project-title">Movies Website</h3>
            <p class="project-desc">Interactive movie browsing platform with search functionality, reviews, and user authentication.</p>
            <div class="project-tech">
              <span class="project-tech-item">JavaScript</span>
              <span class="project-tech-item">API Integration</span>
              <span class="project-tech-item">CSS</span>
            </div>
          </div>
        </div>
        
        <div class="project-card">
          <div class="project-color"></div>
          <div class="project-content">
            <h3 class="project-title">PHP Blogs API</h3>
            <p class="project-desc">Powerful RESTful API built with PHP for blog content management and user interactions.</p>
            <div class="project-tech">
              <span class="project-tech-item">PHP</span>
              <span class="project-tech-item">MySQL</span>
              <span class="project-tech-item">REST API</span>
            </div>
          </div>
        </div>
        
        <div class="project-card">
          <div class="project-color"></div>
          <div class="project-content">
            <h3 class="project-title">Your Position</h3>
            <p class="project-desc">Job posting platform built with Laravel, featuring user profiles, job listings, and application tracking.</p>
            <div class="project-tech">
              <span class="project-tech-item">Laravel</span>
              <span class="project-tech-item">PHP</span>
              <span class="project-tech-item">MySQL</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- GitHub Stats -->
    <div class="section">
      <h2 class="section-title">GitHub Stats</h2>
      
      <div class="stats">
        <div class="stat-item">
          <p class="stat-value">30+</p>
          <p class="stat-label">Repositories</p>
        </div>
        
        <div class="stat-item">
          <p class="stat-value">8</p>
          <p class="stat-label">Followers</p>
        </div>
        
        <div class="stat-item">
          <p class="stat-value">3</p>
          <p class="stat-label">Following</p>
        </div>
        
        <div class="stat-item">
          <p class="stat-value">2</p>
          <p class="stat-label">Starred Projects</p>
        </div>
      </div>
    </div>

    <!-- Connect With Me -->
    <div class="section">
      <h2 class="section-title">Connect With Me</h2>
      
      <div class="social-links">
        <a href="https://github.com/YasserEsam" class="social-link" title="GitHub">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
        </a>
        
        <a href="https://www.linkedin.com/in/yasser-al-ariqi/" class="social-link" title="LinkedIn">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
        </a>
        
        <a href="https://www.facebook.com/yasser.esam.1234/" class="social-link" title="Facebook">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path></svg>
        </a>
        
        <a href="https://www.youtube.com/@yemenitechnician" class="social-link" title="YouTube">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z"></path><polygon points="9.75 15.02 15.5 11.75 9.75 8.48 9.75 15.02"></polygon></svg>
        </a>
        
        <a href="mailto:yaaser10esam1010@gmail.com" class="social-link" title="Email">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
        </a>
      </div>
    </div>
    
    <div class="footer">
      <p>✨ Thanks for visiting my profile! Let's build something amazing together! ✨</p>
    </div>
  </div>
</div>

<script>
  // Add scroll animations
  document.addEventListener('DOMContentLoaded', function() {
    const sections = document.querySelectorAll('.section');
    
    const observerOptions = {
      threshold: 0.1
    };
    
    const observer = new IntersectionObserver(function(entries) {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = 1;
          entry.target.style.transform = 'translateY(0)';
        }
      });
    }, observerOptions);
    
    sections.forEach(section => {
      section.style.opacity = 0;
      section.style.transform = 'translateY(20px)';
      section.style.transition = 'all 0.5s ease-out';
      observer.observe(section);
    });
  });
</script>
</body>
</html>
