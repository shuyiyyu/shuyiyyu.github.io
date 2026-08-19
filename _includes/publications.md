<div class="publications">

{% for section in site.data.publications.main %}

<h3><u>{{ section.title }}</u></h3>

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
<div class="pub-row">

  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">

      <div class="title">
        {{ link.title }}
        {% if link.note %}
        <span style="font-weight: normal;"> ({{ link.note }})</span>
        {% endif %}
      </div>

      <div class="author">{{ link.authors }}</div>

  </div>

  <div class="links">
      {% if link.pdf %}
      <a href="{{ link.pdf }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">PDF</a>
      {% endif %}
  </div>

</div>
</li>

{% endfor %}

</ol>

{% endfor %}

</div>
