---
layout: post
title: Speed Vs. Accuracy in Moses
---
I ran a few experiments for Speed Vs. Accuracy in Moses SMT. 3000 sentences were translated from de, fr, es to en, while varying the following params:

1. Stack size   
2. Translation option size  
3. Cube Pruning limit  

By changing the static size and cube pruning limit, we are effectivly controlling the speed of the translation. Smaller stack and cube pruning limit will make translation faster at the cost of model score. (TODO:use Bleu score instead) I then plot Model Score Vs. Time taken for various settings of stack size, translation option size and cube pruning limit.

The following thumbnails can be opened in a interactive [bokeh](http://bokeh.pydata.org/en/latest/) environment.

[![smiley](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.png){: style="width: 200px;"}](https://raw.githubusercontent.com/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.html)
