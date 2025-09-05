---
layout: page
title: Tags
permalink: /tags/
---

<div class="tags-page">
  <!-- Tag Cloud Overview -->
  <div class="tag-cloud">
    <h2>All Tags</h2>
    <div class="tag-cloud-list">
      {% assign sorted_tags = site.tags | sort %}
      {% for tag in sorted_tags %}
        {% assign tag_name = tag[0] %}
        {% assign tag_posts = tag[1] %}
        <a href="#{{ tag_name | slugify }}" class="tag-cloud-item">
          #{{ tag_name }} <span class="tag-count">({{ tag_posts.size }})</span>
        </a>
      {% endfor %}
    </div>
  </div>

  <!-- Detailed Tag Sections -->
  <div class="tag-sections">
    {% for tag in sorted_tags %}
      {% assign tag_name = tag[0] %}
      {% assign tag_posts = tag[1] %}
      <div class="tag-section">
        <h3 id="{{ tag_name | slugify }}"># {{ tag_name }} <span class="tag-post-count">({{ tag_posts.size }} post{% if tag_posts.size != 1 %}s{% endif %})</span></h3>
        <ul class="post-list">
          {% assign sorted_posts = tag_posts | sort: 'date' | reverse %}
          {% for post in sorted_posts %}
            <li>
              <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
              <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
              {% if post.tags.size > 1 %}
                <div class="post-other-tags">
                  Other tags: 
                  {% for other_tag in post.tags %}
                    {% unless other_tag == tag_name %}
                      <a href="#{{ other_tag | slugify }}" class="other-tag-link">#{{ other_tag }}</a>{% unless forloop.last %}, {% endunless %}
                    {% endunless %}
                  {% endfor %}
                </div>
              {% endif %}
            </li>
          {% endfor %}
        </ul>
      </div>
    {% endfor %}
  </div>
</div>

<style>
.tags-page {
  margin-top: 2rem;
}

/* Tag Cloud Styles */
.tag-cloud {
  margin-bottom: 3rem;
  padding-bottom: 2rem;
  border-bottom: 2px solid #e1e4e8;
}

.tag-cloud h2 {
  margin-bottom: 1rem;
}

.tag-cloud-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag-cloud-item {
  display: inline-block;
  padding: 0.3rem 0.6rem;
  background-color: #f6f8fa;
  border: 1px solid #d1d9e0;
  border-radius: 6px;
  text-decoration: none;
  color: #0366d6;
  font-size: 0.9rem;
  transition: all 0.2s ease;
}

.tag-cloud-item:hover {
  background-color: #0366d6;
  color: white;
  text-decoration: none;
}

.tag-count {
  font-size: 0.8rem;
  color: #6a737d;
}

.tag-cloud-item:hover .tag-count {
  color: rgba(255, 255, 255, 0.8);
}

/* Tag Sections Styles */
.tag-sections {
  margin-top: 2rem;
}

.tag-section {
  margin-bottom: 3rem;
}

.tag-section h3 {
  margin-bottom: 1rem;
  border-bottom: 1px solid #e1e4e8;
  padding-bottom: 0.5rem;
  display: flex;
  align-items: baseline;
  justify-content: space-between;
}

.tag-post-count {
  font-size: 0.8rem;
  color: #6a737d;
  font-weight: normal;
}

.post-list {
  list-style: none;
  padding-left: 0;
}

.post-list li {
  margin-bottom: 1rem;
  padding: 0.75rem;
  border: 1px solid #e1e4e8;
  border-radius: 6px;
  background-color: #fafbfc;
}

.post-meta {
  font-size: 0.875rem;
  color: #6a737d;
  display: block;
  margin-bottom: 0.3rem;
}

.post-link {
  text-decoration: none;
  color: inherit;
  font-weight: 600;
  display: block;
  margin-bottom: 0.3rem;
}

.post-link:hover {
  text-decoration: underline;
  color: #0366d6;
}

.post-other-tags {
  font-size: 0.8rem;
  color: #6a737d;
}

.other-tag-link {
  color: #0366d6;
  text-decoration: none;
}

.other-tag-link:hover {
  text-decoration: underline;
}

/* Responsive Design */
@media (max-width: 600px) {
  .tag-cloud-list {
    gap: 0.3rem;
  }
  
  .tag-cloud-item {
    font-size: 0.8rem;
    padding: 0.2rem 0.4rem;
  }
  
  .post-list li {
    padding: 0.5rem;
  }
  
  .tag-section h3 {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
