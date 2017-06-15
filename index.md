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
    {{ post.excerpt }}
    {% if post.content contains site.excerpt_separator %}
        <a href="{{ post.url | prepend: site.baseurl }}">...Read more</a>
    {% endif %}

    <!--
    <p class="summary">
      {{ post.category }}
    </p>
    -->

  </div>
{% endfor %}
