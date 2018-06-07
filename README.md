# staticvignette

a minimal package to illustrate the behavior of a static vignette depending on different R versions,
specifically between version 3.3.3 (2017-03-06) Another Canoe and the current R-devel version (at creation date) 3.6.0 version.string R Under development (unstable) (2018-06-06 r74855).

  *   built with the current R-devel version the ´´R CMD build staticvignette´´ yells the following warning and sets the the dependency on R version 3.5.0, which is not the case an older R version is used than 3.5.0:
      
      NB: this package now depends on R (>= 3.5.0)

      WARNING: Added dependency on R >= 3.5.0 because serialized objects in  serialize/load version 3 cannot be read in older versions of R.  File(s) containing such objects:  'staticvignettepkg/build/vignette.rds'

A possible context for this behavior give the R-devel NEWS https://cran.r-project.org/doc/manuals/r-devel/NEWS.html:

''R has new serialization format (version 3) which supports custom serialization of ALTREP framework objects. These objects can still be serialized in format 2, but less efficiently. Serialization format 3 also records the current native encoding of unflagged strings and converts them when de-serialized in R running under different native encoding. Format 3 comes with new serialization magic numbers (RDA3, RDB3, RDX3). Format 3 can be selected by version = 3 in save(), serialize() and saveRDS(), but format 2 remains the default for all serialization and saving of the workspace. Serialized data in format 3 cannot be read by versions of R prior to version 3.5.0.''



# pkg content

The package contains the R package helloworld file from RStudio as well as the directory ''vignettes''.
This directory contains the a pdf document and the .pdf.asis, as described by Henrik Bengtsson in ''R packages: Static PDF and HTML vignettes'', available under https://cran.r-project.org/web/packages/R.rsp/vignettes/R_packages-Static_PDF_and_HTML_vignettes.spdf (copy link in a browser).

furthermore, the DESCRIPTION file contains the additional entries

  *   Suggests: R.rsp
  *   VignetteBuilder: R.rsp


# session info
``` r
> R version 3.3.3 (2017-03-06)
> Platform: x86_64-pc-linux-gnu (64-bit)
> Running under: Ubuntu 16.04.4 LTS

> locale:
>  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8        LC_COLLATE=C
>  [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8    LC_PAPER=de_CH.UTF-8       LC_NAME=C
>  [9] LC_ADDRESS=C               LC_TELEPHONE=C             LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C

> attached base packages:
> [1] stats     graphics  grDevices utils     datasets  methods   base

> other attached packages:
> [1] staticvignettepkg_0.1.0

> loaded via a namespace (and not attached):
>  [1] backports_1.0.5   magrittr_1.5      rsconnect_0.4.1.4 rprojroot_1.2     htmltools_0.3.6   tools_3.3.3
>  [7] yaml_2.1.14       Rcpp_0.12.17      stringi_1.1.2     rmarkdown_1.9     knitr_1.20        stringr_1.2.0
> [13] digest_0.6.15     evaluate_0.10
```


