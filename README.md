# Analyzing data from the Human symptoms–disease network 

This repository inspects the bipartite symptom–disease network from the publication:

> [**Human symptoms–disease network**](https://doi.org/10.1038/ncomms5212)<br>
XueZhong Zhou, Jörg Menche, Albert-László Barabási & Amitabh Sharma<br>
_Nature Communications_ (2014) DOI: 10.1038/ncomms5212

The repository is minimal, consisting of a single R Markdown document that is viewable at http://git.dhimmel.com/hsdn/.

## Repository contents

[`index.Rmd`](index.Rmd) is the [R Markdown](http://rmarkdown.rstudio.com/) source code, which is executed and exported to [`index.html`](index.html). Hosted via GitHub Pages, `index.html` is available as a webpage at http://git.dhimmel.com/hsdn/.

[`figure/figS4.png`](figure/figS4.png "Supplementary Figure 4. Illustration of the automated protocol to obtain disease
and symptom related bibliographic data") is a supplementary figure from [Zhou et al. 2014](https://doi.org/10.1038/ncomms5212) describing their pipeline for extracting symptom and disease topics from MEDLINE.

## Notes

The supplementary data from Zhou et al. is not directly consumed in this repository. Instead, the data is retrieved from [`LABrueggs/HSDN`](https://github.com/LABrueggs/HSDN), which mapped symptom and disease names to their corresponding MeSH identifiers.

Since we were interested in using the Zhou et al. data for [Project Rephetio](https://thinklab.com/p/rephetio), we mapped MeSH diseases to the Disease Ontologies [diseases](https://thinklab.com/discussion/unifying-disease-vocabularies/44#6) used in Hetionet v1.0.

Ultimately we did not use the Zhou et al. data in Hetionet, but instead [re-extracted symptom–disease relationships](https://thinklab.com/discussion/mining-knowledge-from-medline-articles-and-their-indexed-mesh-terms/67#4) from MEDLINE topic cooccurrence. The primary motivations for redoing the extraction were:

1. The TF-IDF scores of Zhou et al. are only comparable within a disease and not across diseases.
2. Zhou et al. didn't provide a computational pipeline to recompute relationships in the future or for other relationship types.

See [`dhimmel/MEDLINE`](https://github.com/dhimmel/MEDLINE) for our MEDLINE topic extraction and cooccurrence analysis. The symptom–disease relationships are available in [`disease-symptom-cooccurrence.tsv`](https://github.com/dhimmel/medline/blob/0c9e2905ccf8aae00af5217255826fe46cba3d30/data/disease-symptom-cooccurrence.tsv).

## License

Original content is this repository is released under [CC0 v1.0](https://creativecommons.org/publicdomain/zero/1.0/ "Creative Commons Zero 1.0 Universal") (public domain dedication). Hence, feel free to reuse any of the code, figures, or datasets without restriction if they are original to this repository.

Unfortunately, the copyright to [Zhou et al. 2014](https://doi.org/10.1038/ncomms5212), which presumably covers the supplementary materials, is owned by Macmillan Publishers Limited with all rights reserved. Therefore users should only reuse content from Zhou et al. with discretion and at their own risk.
