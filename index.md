---
layout: default
title: Welcome
---

<ul class="events-listing">
  {% for post in site.posts reversed offset: 1 limit: 3%}
  {% assign expires = post.Date | date: "%s" %}
  {% assign current_time = site.time | date: "%s" %}
  {% if current_time < expires %}
    <li class="events-listing-item">
      <a href="{{ post.url }}">
        <span class="events-listing-date">{{ post.Date | date: "%b %d, %Y" }}</span>
        <img src="{{ post.smallImage }}" class="events-listing-image" />
        <span class="events-listing-title">{{ post.title }}</span>
          </a>
        <span class="events-listing-price">${{ post.price }}</span>
        {% if post.soldOut %}
          <span class="sold-out">Sold Out</span>
        {% else %}
        <form target="paypal" action="https://www.paypal.com/cgi-bin/webscr" method="post" style="float:right;">
          <input type="hidden" name="cmd" value="_s-xclick">
          <input type="hidden" name="hosted_button_id" value="{{post.paypalValue}}">
          <button name="submit" class="btn btn-buy-now">Buy tickets</button>
        </form>

        {% endif %}

        <p class="events-listing-short-description">{{ post.shortDescription }}</p>
        <div class="events-listing-item-footer">
        <span class="events-listing-time-doors">Doors {{post.TimeDoors}}</span>
        <span class="events-listing-time-start">Show {{post.TimeStart}}</span>
        <span class="events-listing-ages">{{post.Ages}}</span>
      </div>
    </li>
    {% else %}

    {% endif %}
  {% endfor %}
</ul>


Located off the Nanny Goat Strut, behind Decca Restaurant, in the heart of NuLu, DREAMLAND is a 120-person black-box theater with adjoining bar, lounge, and gallery space. Dreamland is a venue dedicated to exploring the nexus of progressive art forms, filling a much-needed gap in the Louisville arts community. We promote experimental and innovative music, dance, film and visual art forms.

We have offered more than 100 live performances, hosted lectures, and offer our space for community events. Our smaller size has allowed for engaging experiences, and our intimate setting brings the patrons closer in on the action. We have also provide opportunities for young composers, improvisors, and emerging artists to perform.
