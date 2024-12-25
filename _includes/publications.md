<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
  </div>
</div>
</li>

{% endfor %}

</ol>
</div>

