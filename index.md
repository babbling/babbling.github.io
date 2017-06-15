{% for post in site.posts %}
  <div class="blog-post spacing">
    <h3>
      <a href="http://twitter.com/{{ site.data.authors[post.author].twitter_handle }}">
        <img src="{{ site.data.authors[post.author].image_path }}" alt="{{ site.data.authors[post.author].full_name }}" class="profile" />
      </a>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </h3>
    <p class="summary">
      {{ post.category }}
      <span class="date">
        {{ post.date | date: '%B %d, %Y' }}
      </span>
    </p>

  </div>
{% endfor %}
