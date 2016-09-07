---
layout: post
title: Speed Vs. Accuracy in Moses
---
I ran a few experiments for Speed Vs. Accuracy in Moses SMT. 3000 sentences were translated from de, fr, es to en, while varying the following params:

1. Stack size   
2. Translation option size  
3. Cube Pruning limit  

By changing the stack size and cube pruning limit, we are effectively controlling the speed of the translation. Smaller stack and cube pruning limit will make translation faster at the cost of model score. (TODO:use Bleu score instead) I then plot Model Score Vs. Time taken for various settings of stack size, translation option size and cube pruning limit.

For each language there are 4 plots, _all_, _short_, _medium_ and _long_ for different sentences lengths. Short sentences are $$ \le 10$$ words, medium are $$11$$ to $$30$$ and the rest are considered long.


### French-English Experiments:  
Varying stack size and translation options (in this experiment stack size was made equal to cube prune limit)  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.all.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.all.time.vs.score.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.short.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.short.time.vs.score.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.medium.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.medium.time.vs.score.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.long.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.long.time.vs.score.png)  
Adjusting stack size in steps until it's equal to cube pruning limit. These experiments fix translation option size to 20.  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.all.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.all.time.vs.score.vary.stack.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.short.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.short.time.vs.score.vary.stack.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.medium.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.medium.time.vs.score.vary.stack.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.long.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/fr.long.time.vs.score.vary.stack.png)  


### German-English Experiments:  
Varying stack size and translation options (in this experiment stack size was made equal to cube prune limit)  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.short.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.short.time.vs.score.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.medium.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.medium.time.vs.score.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.long.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.long.time.vs.score.png)  
Adjusting stack size in steps until it's equal to cube pruning limit. These experiments fix translation option size to 20.  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.all.time.vs.score.vary.stack.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.short.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.short.time.vs.score.vary.stack.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.medium.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.medium.time.vs.score.vary.stack.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.long.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/de.long.time.vs.score.vary.stack.png)  
Adjusting stack size in steps until it's equal to cube pruning limit. These experiments fix translation option size to 20.  

### Spanish-English Experiments:  
Varying stack size and translation options (in this experiment stack size was made equal to cube prune limit)  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.all.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.all.time.vs.score.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.short.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.short.time.vs.score.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.medium.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.medium.time.vs.score.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.long.time.vs.score.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.long.time.vs.score.png)  
Adjusting stack size in steps until it's equal to cube pruning limit. These experiments fix translation option size to 20.  
- All sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.all.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.all.time.vs.score.vary.stack.png)  
- Short sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.short.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.short.time.vs.score.vary.stack.png)  
- Medium sentences: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.medium.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.medium.time.vs.score.vary.stack.png)  
- Long lengths: [interactive](https://cdn.rawgit.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.long.time.vs.score.vary.stack.html), [static](https://raw.githubusercontent.com/arendu/arendu.github.io/master/images/speed-vs-acc-plots/es.long.time.vs.score.vary.stack.png)  
