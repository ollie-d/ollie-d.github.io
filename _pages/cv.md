---
layout: archive
title: "Curriculum vitae"
title_tag: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

<p>
  <a href="{{ site.baseurl }}/files/DAMICO_CV.pdf" target="_blank" rel="noopener">Open CV PDF</a>
  <br>
  <span id="cv-last-modified" style="font-size: 0.8rem; color: var(--global-dark-text);"></span>
</p>

<embed
  src="{{ site.baseurl }}/files/DAMICO_CV.pdf"
  type="application/pdf"
  width="100%"
  height="900px">

<script>
  (function () {
    // --- 1. Existing PDF Embed Fix ---
    function killPdfEmbeds() {
      document.querySelectorAll('embed[type="application/pdf"], object[type="application/pdf"], iframe[src$=".pdf"]').forEach(function (el) {
        var ph = document.createElement('div');
        ph.style.height = (el.getBoundingClientRect().height || 600) + 'px';
        el.replaceWith(ph);
      });
    }

    document.addEventListener('click', function (e) {
      var a = e.target.closest && e.target.closest('a');
      if (!a) return;
      if (a.origin === location.origin) killPdfEmbeds();
    }, true);

    window.addEventListener('beforeunload', killPdfEmbeds);

    // --- 2. New: Fetch PDF Last Modified Date ---
    var cvUrl = "{{ site.baseurl }}/files/DAMICO_CV.pdf";
    
    fetch(cvUrl, { method: "HEAD" })
      .then(function(response) {
        var lastModified = response.headers.get("Last-Modified");
        if (lastModified) {
          var date = new Date(lastModified);
          // Format: "19 Feb 2026"
          var options = { day: '2-digit', month: 'short', year: 'numeric' };
          var formattedDate = date.toLocaleDateString('en-GB', options);
          
          var dateSpan = document.getElementById("cv-last-modified");
          if (dateSpan) {
            dateSpan.textContent = "Last updated: " + formattedDate;
          }
        }
      })
      .catch(function(e) { console.error("Could not fetch CV date", e); });

  })();
</script>
