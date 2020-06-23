---
title: "Survival analysis with Risk Score from gene signatures"


date: "June 23, 2020"
layout: post
---

<script src="{{ site.url }}{{ site.baseurl }}/knitr_files/knitr-minimal_files/accessible-code-block-0.0.1/empty-anchor.js"></script>

<section class="main-content">
<div id="idea" class="section level2">
<h2>Idea</h2>
<p>Big data experiments lead to big results. But what to do with a large gene signature from an experiment like <a href="https://de.wikipedia.org/wiki/RNA-Seq">RNASeq</a>? In 2019, <a href="https://clincancerres.aacrjournals.org/content/25/5/1505.long">Hess et al.</a> described a convenient way to filter out gene candidates from a large pool and compress it into a <strong>Risk Score</strong>. I applied this idea to a gene signature described by <a href="https://www.cell.com/cell/fulltext/S0092-8674(17)31270-9?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0092867417312709%3Fshowall%3Dtrue">Puram et al.</a>.</p>
</div>
<div id="what-did-i-do" class="section level2">
<h2>What did I do?</h2>
<ul>
<li>Extract Puram gene signature</li>
<li>Extract genes for <a href="https://www.cancer.gov/about-nci/organization/ccg/research/structural-genomics/tcga">TCGA</a> patient cohort</li>
<li>Use Cox PH models &amp; <a href="https://www.bioconductor.org/packages/release/bioc/vignettes/rbsurv/inst/doc/rbsurv.pdf"><em>rbsurv</em></a> to identify genes</li>
<li>Compress gene expression into Risk Score</li>
<li>Quick survival analysis with <a href="https://www.cbioportal.org/study/summary?id=hnsc_tcga_pub">clinical data</a> from TCGA</li>
</ul>
</div>
<div id="results" class="section level2">
<h2>Results</h2>
<p>This is a glimpse on the actual analysis I did with the clinical data from TCGA. Take look.</p>
<div class="figure" style="text-align: center">
<img src="{{ site.url }}{{ site.baseurl }}/knitr_files/knitr-minimal_files/figure-html/unnamed-chunk-1-1.png" alt="Correlation of all genes described by Puram et al."  />
<p class="caption">
Correlation of all genes described by Puram et al.
</p>
</div>
<div class="figure" style="text-align: center">
<img src="{{ site.url }}{{ site.baseurl }}/knitr_files/knitr-minimal_files/figure-html/unnamed-chunk-1-2.png" alt="Risk Score in accordance to Hess et al."  />
<p class="caption">
Risk Score in accordance to Hess et al.
</p>
</div>
<div class="figure" style="text-align: center">
<img src="{{ site.url }}{{ site.baseurl }}/knitr_files/knitr-minimal_files/figure-html/unnamed-chunk-1-3.png" alt="Testing performance of Risk Score in survival analysis"  />
<p class="caption">
Testing performance of Risk Score in survival analysis
</p>
</div>
<p>In short, I was able to simply extract 4 genes from 100 potential candidates and compress them into one simple number: a Risk Score. Then, I used the Risk Score to see if I could group the TCGA patients into high and low Risk (Risk- and Risk+). So, out of 100 genes I could describe 4 genes that do play a role for patient survival and would be candidates for further analysis, e.g. by <em>in vitro</em> experiments on functionality. The whole analysis with necessary data sets is uploaded to my <a href="https://github.com/HenrikSchinke/RiskScore_pEMT">GitHub page</a> and a more detailled description is in my <a href="https://henrikschinke.github.io/RiskScore_pEMT.html">R section on my website</a>.</p>
</div>
<div id="what-do-you-need-to-do-it-yourself" class="section level2">
<h2>What do you need to do it yourself?</h2>
<ul>
<li>A gene signature you expect to impact clinical outcome</li>
<li>Patient data, e.g. from TCGA</li>
<li>Basic to intermediate R knowledge</li>
<li>Basic understanding of Cox models</li>
</ul>
</div>
</section>
