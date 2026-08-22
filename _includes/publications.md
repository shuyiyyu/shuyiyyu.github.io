<div class="publications">

{% for section in site.data.publications.main %}

<h3><u>{{ section.title }}</u></h3>

<!-- Project-level abstract -->
{% if section.abstract %}
<details style="margin-bottom: 16px;">
  <summary style="cursor: pointer;">
    Project Overview
  </summary>

  <div style="margin-top: 8px; line-height: 1.5;">
    {{ section.abstract }}
  </div>
</details>
{% endif %}

<ol class="bibliography">

{% for link in section.papers %}

<li style="margin-bottom: 18px;">

  <div style="
      padding-right: 15px;
      padding-left: 20px;
  ">

    <!-- Paper title: wraps naturally if long -->
    <div class="title"
         style="
           line-height: 1.35;
           margin-bottom: 3px;
         ">
      {{ link.title }}{% if link.note %}<span style="font-weight: normal; white-space: nowrap;"> ({{ link.note }})</span>{% endif %}
    </div>

    <!-- Author -->
    <div class="author"
         style="
           margin-bottom: 4px;
         ">
      {{ link.authors }}
    </div>

    <!-- PDF + SSRN directly under author -->
    {% if link.pdf or link.ssrn %}
    <div class="links"
         style="
           display: flex;
           flex-direction: row;
           gap: 6px;
           align-items: center;
           justify-content: flex-start;
           margin-bottom: 6px;
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
    {% endif %}

    <!-- Paper-level abstract -->
    {% if link.abstract %}
    <details style="margin-top: 4px; margin-bottom: 6px;">

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
