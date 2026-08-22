<div class="publications">

{% for section in site.data.publications.main %}

<h3><u>{{ section.title }}</u></h3>

<!-- Project-level abstract -->
{% if section.abstract %}
<details style="margin-bottom: 18px;">
  <summary style="cursor: pointer;">
    Abstract
  </summary>

  <div style="margin-top: 8px; line-height: 1.5;">
    {{ section.abstract }}
  </div>
</details>
{% endif %}

<ol class="bibliography">

{% for link in section.papers %}

<li>

  <div style="padding-right: 15px; padding-left: 20px;">

    <!-- Paper title + note always on the same line -->
    <div class="title" style="white-space: nowrap;">
      {{ link.title }}{% if link.note %}<span style="font-weight: normal;"> ({{ link.note }})</span>{% endif %}
    </div>

    <!-- Author + links on the same line -->
    <div style="
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        margin-top: 2px;
    ">

      <div class="author">
        {{ link.authors }}
      </div>

      <div class="links"
           style="
             display: flex;
             flex-direction: row;
             gap: 6px;
             align-items: center;
             white-space: nowrap;
           ">

        {% if link.pdf %}
        <a href="{{ link.pdf }}"
           class="btn btn-sm z-depth-0"
           role="button"
           target="_blank"
           style="font-size: 12px;">
          PDF
        </a>
        {% endif %}

        {% if link.ssrn %}
        <a href="{{ link.ssrn }}"
           class="btn btn-sm z-depth-0"
           role="button"
           target="_blank"
           style="font-size: 12px;">
          SSRN
        </a>
        {% endif %}

      </div>

    </div>

    <!-- Paper-level abstract -->
    {% if link.abstract %}
    <details style="margin-top: 8px; margin-bottom: 12px;">

      <summary style="cursor: pointer;">
        Abstract
      </summary>

      <div style="margin-top: 8px; line-height: 1.5;">
        {{ link.abstract }}
      </div>

    </details>
    {% endif %}

  </div>

</li>

{% endfor %}

</ol>

{% endfor %}

</div>
