# 500 Class 05: 2023-02-16

[Main Website](https://thomaselove.github.io/500-2023/) | [Calendar](https://thomaselove.github.io/500-2023/calendar.html) | [Syllabus](https://thomaselove.github.io/500-syllabus-2023) | [Canvas](https://canvas.case.edu) | [Data/Code](https://github.com/THOMASELOVE/500-data) |  [Sources](https://github.com/THOMASELOVE/500-classes-2023/tree/main/sources) | For help, email
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :------: | :-----------: 
links for everything | deadlines | expectations | zoom, submissions | downloads | to read | `Thomas` dot `Love` at `case` dot `edu`

## Today's Slides

Class | Date | PDF | Quarto .qmd | Recording
:---: | :--------: | :------: | :------: | :-------------:
05 | 2023-02-16 | **[Slides 05](https://github.com/THOMASELOVE/500-slides-2023/blob/main/500_slides05.pdf)** | **[Code 05](https://github.com/THOMASELOVE/500-slides-2023/blob/main/500_slides05.qmd)** | Visit [Canvas](https://canvas.case.edu/), select **Zoom** and **Cloud Recordings**

## Today's Agenda

1. Our R Examples So Far
    - [The toy example](https://github.com/THOMASELOVE/500-data/tree/master/toy) (discussed in Class 04)
    - [The lindner example](https://github.com/THOMASELOVE/500-data/tree/master/lindner) (lightly touched on in Class 04)
2. [The dm2200 example](https://github.com/THOMASELOVE/500-data/tree/master/dm2200) (new today)
    - Using the MatchIt and Matching packages to match
    - Varying the Matching Structure
    - What happens when the matched sample outcome analysis won't converge?
3. Matching with (or without) a Propensity Score
4. Discussion of [OSIA Claims and Scheduling](https://github.com/THOMASELOVE/500-osia-2023/blob/main/claims.md)
5. Rosenbaum, Chapters 1-4
6. Feinstein's Model for Research Architecture
7. Extending "Matching" in a few other ways

## What Should I Be Working On?

1. [Project Proposal (draft 1)](https://thomaselove.github.io/500-2023/proj500.html) is due to Canvas at 7 PM on Wednesday 2023-02-22.
    - You'll also present your idea orally in class on 2023-02-23 (this "presentation" will just be you briefly summarizing your data source, outcome, treatment and covariates from your seat - no slides and it shouldn't take more than two minutes, each.)
    - The second and final version of your Proposal is due on Wednesday 2023-03-08.
2. [Lab 3](https://thomaselove.github.io/500-2023/lab3.html) is due to Canvas at 7 PM the following Wednesday 2023-03-01. In Lab 3, you will do the following:
    - fit two logistic regression models in Task 1
    - fit a propensity model in Task 2
    - evaluate Rubin's Rule 1 and Rule 2 before propensity scores are applied in Task 3 
    - use direct adjustment for the (logit of the) propensity score to fit an outcome model in Task 4 (see the `toy` or `lindner` examples for help with these first four tasks)
    - do a 1:1 (greedy) match without replacement on the propensity score, in several parts, captured in Task 5 (see the examples above, or the `dm2200` example) 
    - compare the estimates you receive from Tasks 1, 4 and 5 in Task 6 using a table or (better) graph.

## References from Today's Class include...

- Austin Peter C 2014 [A comparison of 12 algorithms for matching on the propensity score](https://github.com/THOMASELOVE/500-classes-2023/blob/main/sources/articles/Austin%202014%20Comparing%2012%20PS%20matching%20algorithms.pdf) *Statistics in Medicine* 33, 1057-69.
- Hansen Ben B 2004 [Full Matching in an Observational Study of Coaching for the SAT](https://github.com/THOMASELOVE/500-classes-2023/blob/main/sources/articles/Hansen%202004%20JASA%20Full%20Matching%20in%20SAT%20Coaching.pdf) *Journal of the American Statistical Association*
- Kubo Yusuke et al. 2020 [Effects of preoperative low-intensity training with slow movement on early quadriceps weakness after total knee arthroplasty in patients with knee osteoarthritis: a retrospective propensity score-matched study](https://github.com/THOMASELOVE/500-classes-2023/blob/main/sources/articles/Kubo_2020_extra.pdf) *BMC Sports Science, Medicine and Rehabilitation*
- Rosenbaum Paul E 2010 [Design of Observational Studies](https://github.com/THOMASELOVE/500-classes-2023/blob/main/sources/articles/Rosenbaum%20PR%202010%20Design%20of%20Observational%20Studies.pdf)
- Rubin Donald B 2001 [Using Propensity Scores to help Design Observational Studies: Application to the Tobacco Litigation](https://github.com/THOMASELOVE/500-classes-2023/blob/main/sources/articles/Rubin%202001%20Tobacco%20Litigation%20article.pdf) *Health Services & Outcomes Research Methodology*

Some potentially useful resources related to the dm2200 example include:
- Noah Greifer's [MatchIt: Getting Started](https://cran.r-project.org/web/packages/MatchIt/vignettes/MatchIt.html) vignette
- Noah Greifer's [Covariate Balance Tables and Plots: A Guide to the cobalt Package](https://cran.r-project.org/web/packages/cobalt/vignettes/cobalt.html) vignette
- Jasjeet Sekhon's [Multivariate and Propensity Score Matching Software for Causal Inference](http://sekhon.berkeley.edu/matching/) describes the Matching package.

## Can I Still See Your Show?

We have fewer than 20 seats available for each of our final two performances of The Play That Goes Wrong, this Friday and Saturday at 8 PM. Visit https://www.auroracommunitytheatre.com/ for tickets.

![](two_TPTGW.png)

## One Last Thing

A poem guide for **The Road Not Taken** by Robert Frost is available at https://www.poetryfoundation.org/articles/89511/robert-frost-the-road-not-taken. Its subtitle is "Our choices are clear in hindsight."
