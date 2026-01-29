---
title: "Design documents"
layout: single
---
## [Go back to the main page](/)


<div class="search js-only">
  <input type="text" id="search" placeholder="Search for a specific document...">
  <button id="clear-search">
    <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><title>Backspace</title><path d="M135.19 390.14a28.79 28.79 0 0021.68 9.86h246.26A29 29 0 00432 371.13V140.87A29 29 0 00403.13 112H156.87a28.84 28.84 0 00-21.67 9.84v0L46.33 256l88.86 134.11z" fill="none" stroke="currentColor" stroke-linejoin="round" stroke-width="32"></path><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="32" d="M336.67 192.33L206.66 322.34M336.67 322.34L206.66 192.33M336.67 192.33L206.66 322.34M336.67 322.34L206.66 192.33"></path></svg>
  </button>
</div>

<script>
// @license magnet:?xt=urn:btih:5ac446d35272cc2e4e85e4325b146d0b7ca8f50c&dn=unlicense.txt Unlicense

document.addEventListener("DOMContentLoaded", () => {
  for (e of document.getElementsByClassName("js-only")) {
    e.classList.remove("js-only");
  }

  const designdocs = document.querySelectorAll("#doclist li");
  const search = document.getElementById("search");
  const oldheading = document.getElementById("newest-design-doc");
  const clearSearch = document.getElementById("clear-search");
  const doclist = document.getElementById("doclist");

  designdocs.forEach(designdoc => {
    if (designdoc.classList.contains("older-document")) {
      designdoc.style.display = "none";
    }
  });

  search.addEventListener("input", () => {
    const searchText = search.value.toLowerCase().trim().normalize('NFD').replace(/\p{Diacritic}/gu, "");
    const searchTerms = searchText.split(" ");
    const hasFilter = searchText.length > 0;

    doclist.classList.toggle("list-searched", hasFilter);
    if (oldheading) oldheading.classList.toggle("hidden", hasFilter);

    designdocs.forEach((designdoc) => {
      const searchString = `${designdoc.textContent} ${designdoc.dataset.tags}`.toLowerCase().normalize('NFD').replace(/\p{Diacritic}/gu, "");
      const isMatch = searchTerms.every(term => searchString.includes(term));
      const isRecentDoc = !designdoc.classList.contains("older-document");

      if (hasFilter ? isMatch : isRecentDoc) {
        designdoc.style.display = "list-item";
        designdoc.classList.add("matched-designdoc");
      } else {
        designdoc.style.display = "none";
        designdoc.classList.remove("matched-designdoc");
      }
    });
  });

  clearSearch.addEventListener("click", () => {
    search.value = "";
    
    designdocs.forEach(designdoc => {
      designdoc.style.display = designdoc.classList.contains("older-document") ? "none" : "list-item";
      designdoc.classList.remove("matched-designdoc");
    });

    doclist.classList.remove("list-searched");
    if (oldheading) oldheading.classList.remove("hidden");
  });
});
// @license-end
</script>

### Newest design doc
{{< doclist >}}

### View by category

{{< tagcloud >}}