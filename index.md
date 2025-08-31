---
layout: default
---

<div class="main-wrapper">
    <div class="logo-container">
        <img src="/assets/images/logo.png" height="30">
    </div>
    
    <div class="container">
        <h1>Fulcrum Research</h1>
        
        <p>Much of the work of the future will be executed by AI agents. They will write software, perform research, and carry out knowledge tasks we can't yet imagine.</p>

        <p>Our current stack for understanding is not ready for a world that humans didn't build. We want to scale human oversight with model intelligence.</p>

        <p>Currently, we are building tooling that tells you what your ML evals and environments are truly testing for. In the long run, we want to build the inference time infrastructure to safely deploy agents in the world.</p>

        <p>If you are building RL environments, evals, or deploying agents, <a href="mailto:{{ site.email }}">contact us</a> to try our tooling.</p>

        {% if site.posts.size > 0 %}
        <div class="posts-section" style="margin: 3rem 0;">
            <h2 style="font-size: 1.6rem; margin-bottom: 2rem; font-weight: normal;">Posts</h2>
            <ul style="list-style: none; padding: 0;">
            {% for post in site.posts %}
                <li style="margin-bottom: 1.5rem;">
                    <a href="{{ post.url | relative_url }}" style="font-size: 1.05rem;">{{ post.title }}</a>
                    <time style="display: block; font-size: 0.85rem; opacity: 0.6; margin-top: 0.25rem;">{{ post.date | date: "%B %d, %Y" }}</time>
                </li>
            {% endfor %}
            </ul>
        </div>
        {% endif %}
        
        <p>You can reach us here: <a href="mailto:{{ site.email }}">{{ site.email }}</a>.</p>

        <div style="margin-top: 3rem; padding-top: 2rem; border-top: 1px dotted #333;">
            <p style="margin-bottom: 1rem;">Sign up for updates:</p>
            <form action="https://formspree.io/f/xyzdejre" method="POST" class="email-form" style="display: flex; gap: 0.5rem; max-width: 400px;">
                <input 
                    type="email" 
                    name="email" 
                    required
                    placeholder="your@email.com"
                    style="flex: 1; padding: 0.5rem; font-family: 'Courier Prime', monospace; font-size: 0.95rem; border: 1px solid #333; background-color: transparent; color: #333;">
                <button 
                    type="submit"
                    style="padding: 0.5rem 1.5rem; font-family: 'Courier Prime', monospace; font-size: 0.95rem; background-color: #333; color: #ded5bd; border: 1px solid #333; cursor: pointer; transition: all 0.2s;"
                    onmouseover="this.style.backgroundColor='transparent'; this.style.color='#333';"
                    onmouseout="this.style.backgroundColor='#333'; this.style.color='#ded5bd';">
                    Subscribe
                </button>
            </form>
        </div>
    </div>
</div>
