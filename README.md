Professional and dynamic GitHub profile page with animations and interactive elements.



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/typed.js/2.0.12/typed.min.js"></script>
    <title>GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        }

        body {
            background: #0d1117;
            color: #c9d1d9;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 4px solid #238636;
            margin-bottom: 1rem;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

        .name {
            font-size: 2.5rem;
            color: #58a6ff;
            margin-bottom: 0.5rem;
        }

        .title {
            color: #8b949e;
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .stat-item {
            background: #161b22;
            padding: 1rem;
            border-radius: 6px;
            text-align: center;
            transition: transform 0.3s;
        }

        .stat-item:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 1.5rem;
            color: #58a6ff;
            font-weight: bold;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .project-card {
            background: #161b22;
            border-radius: 6px;
            padding: 1.5rem;
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-title {
            color: #58a6ff;
            margin-bottom: 0.5rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .skill-tag {
            background: #238636;
            color: white;
            padding: 0.25rem 0.75rem;
            border-radius: 15px;
            font-size: 0.9rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-link {
            color: #8b949e;
            text-decoration: none;
            transition: color 0.3s;
        }

        .social-link:hover {
            color: #58a6ff;
        }

        .contribution-graph {
            margin-top: 2rem;
            background: #161b22;
            padding: 1rem;
            border-radius: 6px;
        }

        .typing-text {
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <img src="/api/placeholder/200/200" alt="Profile Picture" class="profile-img">
            <h1 class="name">John Doe</h1>
            <div class="typing-text">
                <span id="typed-text"></span>
            </div>
            <p class="title">Full Stack Developer | Open Source Enthusiast</p>
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number">50+</div>
                    <div>Repositories</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">1.2K</div>
                    <div>Contributions</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">500+</div>
                    <div>Followers</div>
                </div>
            </div>
        </header>

        <div class="projects">
            <div class="project-card">
                <h3 class="project-title">Project Alpha</h3>
                <p>A modern web application built with React and Node.js</p>
                <div class="skills">
                    <span class="skill-tag">React</span>
                    <span class="skill-tag">Node.js</span>
                    <span class="skill-tag">MongoDB</span>
                </div>
            </div>
            <div class="project-card">
                <h3 class="project-title">Project Beta</h3>
                <p>Mobile-first responsive dashboard template</p>
                <div class="skills">
                    <span class="skill-tag">Vue.js</span>
                    <span class="skill-tag">Tailwind</span>
                    <span class="skill-tag">Firebase</span>
                </div>
            </div>
            <div class="project-card">
                <h3 class="project-title">Project Gamma</h3>
                <p>AI-powered data visualization tool</p>
                <div class="skills">
                    <span class="skill-tag">Python</span>
                    <span class="skill-tag">TensorFlow</span>
                    <span class="skill-tag">D3.js</span>
                </div>
            </div>
        </div>

        <div class="social-links">
            <a href="#" class="social-link">Twitter</a>
            <a href="#" class="social-link">LinkedIn</a>
            <a href="#" class="social-link">Portfolio</a>
        </div>
    </div>

    <script>
        // Initialize Typed.js
        new Typed('#typed-text', {
            strings: [
                'Building awesome software',
                'Contributing to open source',
                'Learning new technologies',
                'Solving complex problems'
            ],
            typeSpeed: 50,
            backSpeed: 30,
            loop: true
        });

        // Add animation to project cards on scroll
        const observerOptions = {
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.project-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'all 0.5s ease-out';
            observer.observe(card);
        });
    </script>
</body>
</html>

```

I've created a modern and interactive GitHub profile page with several features:

1. Animated Elements:
   - Floating profile picture animation
   - Typing text effect showing different roles/activities
   - Smooth hover animations on stats and project cards
   - Scroll-triggered animations for project cards

2. Layout Sections:
   - Header with profile picture and name
   - Key statistics display
   - Featured projects grid
   - Skills tags
   - Social links

3. Styling Features:
   - GitHub's dark theme colors
   - Responsive design that works on all screen sizes
   - Modern card-based layout
   - Smooth transitions and hover effects

4. Interactive Elements:
   - Animated typing text using Typed.js
   - Hover effects on all cards
   - Intersection Observer for scroll animations

To use this template:
1. Replace the profile image placeholder
2. Update the name, title, and statistics
3. Modify the project cards with your actual projects
4. Update the social links
5. Customize the colors and animations as needed
