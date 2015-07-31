{{ partial head.html }}
<body>
  <div class="mdl-layout mdl-js-layout has-drawer is-upgraded">
      <header class="mdl-layout__header mdl-layout__header--scroll mdl-layout__header--transparent is-casting-shadow mdl-color-text--white">
      </header>
      <main class="mdl-layout__content mdl-grid">
        {% for post in site.posts reverse %}
<div class="mdl-card mdl-cell mdl-cell--8-col">
  <div class="mdl-card__media mdl-color-text--grey-50" style="{%if post.image_header %}background-image: url('{{post.image_header}}');{% endif %}">
    <h3><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></h3>
  </div>
  {% if post.description %}
  <div class="mdl-color-text--grey-600 mdl-card__supporting-text index-entry__description">
    <p>{{ post.description }}</p>
    <a class="mdl-button mdl-js-button mdl-js-ripple-effect" href="{{ root_url }}{{ post.url }}">
       Read More
    </a>
  </div>
  {% endif %}
  <div class="mdl-card__supporting-text meta mdl-color-text--grey-600">
    <div class="minilogo"></div>
    <div>
      <strong>Paul Kinlan</strong>
      <span><time pubdate>{{ post.date | date: '%B %d, %Y' }}</time></span>
    </div>
  </div>
</div>
{% endfor %}
        
      <nav class="mdl-cell mdl-cell--12-col">
          <div class="empty"></div>
          <div>
            More
            <button class="mdl-button mdl-js-button mdl-js-ripple-effect mdl-button--icon">
              <i class="material-icons">arrow_forward</i>
            </button>
          </div>
        </nav>
        </main>
     </div>

  </body>
 </html>
      