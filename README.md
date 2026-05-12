# LeadsBlue Research — Buyer Catalogue

**Live site:** https://leadsblue-datasets.github.io/research/

**What this is:** The buyer-side companion to the open *B2B Cold Email Benchmark Dataset 2026*. 100 pages of segment-specific buyer guidance — country, industry, and executive-role — each grounded in real benchmark performance data published openly on Zenodo and Hugging Face.

**Who it's for:** B2B founders, marketers, and sales operators evaluating whether to buy a verified business email list, and which segment to start with.

**Who publishes it:** LeadsBlue Analytics LTD, with the underlying benchmark dataset authored by [Luther Johnson](https://orcid.org/0009-0008-9836-1280) (ORCID `0009-0008-9836-1280`).

---

## Why this exists

Most "B2B email list" content online falls into two camps: vendor marketing that promises everything, or generic SEO articles that promise nothing specific. Neither helps a buyer make a decision.

This catalogue documents what actually varies across segments — open rates, reply rates, compliance regimes, decision-maker hierarchies, send-time windows — with the underlying data published openly and citable.

Each page combines:

- **Real performance benchmarks** (open rate, reply rate, bounce target) from the published dataset
- **Real regulator URLs** for the segment's compliance regime (FTC, ICO, BfDI, CNIL, MeitY, etc.)
- **Real cultural context** sourced from country-specific business analysis
- **The LeadsBlue product listing** for that segment

The benchmark data is open under CC BY 4.0. The contact-database products are sold by LeadsBlue under their commercial terms — this catalogue is the buyer-facing index of those products with documented performance expectations.

---

## Data sources & citation

The benchmark data behind every page comes from:

| Source | URL | What it contains |
|---|---|---|
| **Zenodo (canonical)** | [DOI 10.5281/zenodo.20136256](https://doi.org/10.5281/zenodo.20136256) | Full dataset, version-pinned, CC BY 4.0 |
| **Hugging Face** | [datasets/emailmarketingdataset/B2B-Cold-Email-Benchmark-Dataset-2026](https://huggingface.co/datasets/emailmarketingdataset/B2B-Cold-Email-Benchmark-Dataset-2026) | Same data, ML-tooling-friendly format |
| **Live agent API** | [api.b2bdataindex.com](https://api.b2bdataindex.com) | Queryable via `/v1/predict` and `/v1/check-compliance` |
| **Open Q&A surface** | [b2bdataindex.com](https://b2bdataindex.com) | 250 Q&A pages with benchmark deep-dives |

### How to cite

> Johnson, L. (2026). *B2B Cold Email Benchmark Report 2026*. Zenodo. https://doi.org/10.5281/zenodo.20136256

### BibTeX

```bibtex
@dataset{johnson_2026_b2b_benchmark,
  author       = {Johnson, Luther},
  title        = {B2B Cold Email Benchmark Report 2026},
  year         = 2026,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.20136256},
  url          = {https://doi.org/10.5281/zenodo.20136256},
  license      = {CC-BY-4.0}
}
```

---

## What's in this repo

```
index.html                Root hub
buy/                      Buyer catalogue (95 pages)
  [country]/              74 country buyer pages
  industry/[ind]/         14 industry buyer pages
  role/[role]/            7 executive-role pages
  index.html              Catalogue browse hub
guides/                   Buyer guides
  how-to-buy-b2b-email-list/
  cold-email-compliance/
  index.html              Guides hub
sitemap.xml               100 URLs
robots.txt                Indexable; LLM crawlers explicitly allowed
llms.txt                  Citation source + API discovery for LLMs
.nojekyll                 Skip Jekyll on GitHub Pages
assets/og-*.svg           Open Graph images
```

Every page includes JSON-LD for Organization, BreadcrumbList, Article (with Zenodo citation), Product, Dataset, FAQPage, ClaimReview (for each benchmark claim), and WebPage Speakable specification.

## The source generator

The HTML in this repo is generated from JSON data files using a Node.js script. The generator is open and reproducible — see [leadsblue-buyer-source](#) for the full toolchain.

```bash
node generate.js     # Builds all 100 pages to ./public/
node test-output.js  # 42 validation assertions
```

Same data + same generator = same output, every time. Updates to the benchmark data flow through a single regeneration step.

---

## Authorship & contact

**Principal researcher:** Luther Johnson  
**ORCID:** [0009-0008-9836-1280](https://orcid.org/0009-0008-9836-1280)  
**Affiliation:** LeadsBlue Research  
**Email:** research@leadsblue.com

**Publisher:** LeadsBlue Analytics LTD  
**Commercial:** https://leadsblue.com  
**Crunchbase:** https://www.crunchbase.com/organization/leadsblue-com-buy-email-lists-targeted-b2b-b2c-sales-leads  
**LinkedIn:** https://www.linkedin.com/company/leadsblue/

---

## License

- **Page content & dataset:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to use, redistribute, and adapt with attribution
- **Generator source code:** MIT (see [leadsblue-buyer-source](#))
- **Contact databases sold by LeadsBlue:** sold under LeadsBlue's commercial terms — separate from this open documentation

---

## Related surfaces in the LeadsBlue Research network

- [leadsblue.com](https://leadsblue.com) — commercial product catalogue
- [b2bdataindex.com](https://b2bdataindex.com) — open Q&A & benchmark deep-dives
- [api.b2bdataindex.com](https://api.b2bdataindex.com) — live agent-callable API
- [Zenodo deposit](https://zenodo.org/records/20136256) — canonical data publication
- [Hugging Face dataset](https://huggingface.co/datasets/emailmarketingdataset/B2B-Cold-Email-Benchmark-Dataset-2026) — ML-friendly mirror
