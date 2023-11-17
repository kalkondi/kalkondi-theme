---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<script>
  function triggerGitAutomation() {
    const url = 'https://git-client-automation-fd017bcfd77c.herokuapp.com/process';

    const data = {
      title: 'title from button click',
      description: 'some new description from button click'
    };

    fetch(url, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(data),
    })
            .then(response => response.json())
            .then(data => {
              console.log('Success:', data);
              alert('Git automation triggered successfully!');
            })
            .catch((error) => {
              console.error('Error:', error);
              alert('Error triggering Git automation.');
            });
  }
</script>
{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
<button onclick="triggerGitAutomation()">Trigger Git Automation</button>
