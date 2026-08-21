<div class="publications">

{% for section in site.data.publications.main %}

<h3><u>{{ section.title }}</u></h3>

<ol class="bibliography">

{% for link in section.papers %}

<li>

<div class="pub-row">

  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">

    <div class="title">
      {{ link.title }}
      {% if link.note %}
      <span style="font-weight: normal;"> ({{ link.note }})</span>
      {% endif %}
    </div>

    <div class="author">
      {{ link.authors }}
    </div>

    <!-- Abstract -->
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


  <!-- Links -->
  <div class="links">

    {% if link.pdf %}
    <a href="{{ link.pdf }}"
       class="btn btn-sm z-depth-0"
       role="button"
       target="_blank"
       style="font-size:12px;">
       PDF
    </a>
    {% endif %}

    {% if link.ssrn %}
    <a href="{{ link.ssrn }}"
       class="btn btn-sm z-depth-0"
       role="button"
       target="_blank"
       style="font-size:12px;">
       SSRN
    </a>
    {% endif %}

  </div>

</div>

</li>

{% endfor %}

</ol>

{% endfor %}

</div>
