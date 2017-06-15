{% for post in site.posts %}
  <div class="blog-post spacing">
    <span class="date">
      {{ post.date | date: '%B %d, %Y' }}
    </span>
    <h3>
      <a href="http://twitter.com/{{ site.data.authors[post.author].twitter_handle }}">
        <img src="{{ site.data.authors[post.author].image_path }}" alt="{{ site.data.authors[post.author].full_name }}" class="profile" />
      </a>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h3>
    {% if post.content contains site.excerpt_separator %}
      {{ post.excerpt }}
      <a href="{{ post.url | prepend: site.baseurl }}">...Read more</a>
    {% else %}
      {{ post.content | replace_first: "<!--more-->", "blahblah" }}
    {% endif %}
  </div>
{% endfor %}
