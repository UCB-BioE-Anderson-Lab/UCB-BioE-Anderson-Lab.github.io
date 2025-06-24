# Publications

The Anderson Lab develops tools and strategies to make biology more engineerable, combining computational modeling with synthetic biology wetlab research. This list of publications reflects work on enzyme specificity prediction, biological design validation, and optimization strategies. It also includes foundational contributions to unnatural amino acid incorporation, biosafety systems, and standards in biological design automation.

---

## Papers

<div id="publications-list"></div>

---

## Patents

<div id="patents-list"></div>

<script type="text/javascript">
async function fetchYAML(url) {
  const response = await fetch(url);
  const text = await response.text();
  return jsyaml.load(text);
}

function renderEntries(entries, containerId) {
  const container = document.getElementById(containerId);
  if (!container) return;
  const list = document.createElement("ul");
  list.style.listStyle = "none";
  list.style.padding = 0;

  Object.values(entries).forEach(entry => {
    const item = document.createElement("li");
    item.style.marginBottom = "1em";

    let citation = "";
    if (entry.authors) {
      citation += `${entry.authors.join(", ")}. `;
    }
    if (entry.title) {
      citation += `"<strong>${entry.title}</strong>." `;
    }
    if (entry.journal) {
      citation += `<em>${entry.journal}</em>`;
    }
    if (entry.year) {
      citation += ` (${entry.year})`;
    }
    citation += ".";
    if (entry.doi) {
      citation += ` <a href="https://doi.org/${entry.doi}" target="_blank">DOI</a>`;
    }
    if (entry.pmid) {
      citation += ` <a href="https://pubmed.ncbi.nlm.nih.gov/${entry.pmid}/" target="_blank">PubMed</a>`;
    }
    if (entry.biorxiv) {
      citation += ` bioRxiv doi: <a href="https://www.biorxiv.org/content/${entry.biorxiv}.full" target="_blank">${entry.biorxiv}</a>`;
    }
    if (entry.patent_number) {
      citation += `<br>Patent No: ${entry.patent_number}`;
    }
    if (entry.origin) {
      citation += ` — ${entry.origin}`;
    }

    item.innerHTML = citation;
    list.appendChild(item);
  });

  container.appendChild(list);
}

document.addEventListener("DOMContentLoaded", async () => {
  const [papers, patents] = await Promise.all([
    fetchYAML("/data/papers.yml"),
    fetchYAML("/data/patents.yml"),
  ]);
  renderEntries(papers, "publications-list");
  renderEntries(patents, "patents-list");
});
</script>
<script src="https://cdn.jsdelivr.net/npm/js-yaml@4.1.0/dist/js-yaml.min.js"></script>