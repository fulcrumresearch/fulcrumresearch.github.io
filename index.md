---
layout: default
---

<div style="display: flex; align-items: flex-start; max-width: 850px; margin: 0 auto;">
    <div style="flex-shrink: 0; width: 150px; padding-top: 2rem;">
        <img src="/assets/images/logo.png" height="30">
    </div>
    
    <div class="container" style="flex: 1;">
        <h1>Fulcrum Research</h1>
        
        <p>Much of the work of the future will be executed by AI agents. They will write software, perform research, and carry out knowledge tasks we can't yet imagine.</p>

        <p>Our current stack for understanding is not ready for a world that humans didn't build.</p>

        <p>We build products that scale human understanding with model labor. Currently, we are building tooling that tells you what your ML evals and environments are truly testing for. In the long run, we want to build the inference time infrastructure to safely deploy agents in the world.</p>

        <p>If you are building environments or deploying agents, <a href="mailto:{{ site.email }}">contact us</a> to try our tooling.</p>

        {% if site.posts.size > 0 %}
        <div class="posts-section" style="margin: 3rem 0;">
            <h2 style="font-size: 1.6rem; margin-bottom: 2rem; font-weight: normal;">Essays</h2>
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
    </div>
</div>
