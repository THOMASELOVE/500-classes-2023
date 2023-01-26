# 500 Class 02: 2023-01-26

[Main Website](https://thomaselove.github.io/500-2023/) | [Calendar](https://thomaselove.github.io/500-2023/calendar.html) | [Syllabus](https://thomaselove.github.io/500-syllabus-2023) | [Canvas](https://canvas.case.edu) | [Data/Code](https://github.com/THOMASELOVE/500-data) |  [Sources](https://github.com/THOMASELOVE/500-classes-2023/tree/main/sources) | For help, email
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :------: | :-----------: 
links for everything | deadlines | expectations | zoom, submissions | downloads | to read | `Thomas` dot `Love` at `case` dot `edu`

![](https://imgs.xkcd.com/comics/methodology_trial.png) from <https://xkcd.com/2726>

## Today's Slides

Class | Date | PDF | Quarto .qmd | Recording
:---: | :--------: | :------: | :------: | :-------------:
02 | 2023-01-26 | **[Slides 02](https://github.com/THOMASELOVE/500-slides-2023/blob/main/500_slides02.pdf)** | **[Code 02](https://github.com/THOMASELOVE/500-slides-2023/blob/main/500_slides02.qmd)** | Visit [Canvas](https://canvas.case.edu/), select **Zoom** and **Cloud Recordings**

# Today's Agenda

1. Today we'll start by discussing Lucy D'Agostino McGowan's [February 2017 blog post](https://www.kdnuggets.com/2017/02/hill-data-scientist-xkcd-story.html) "[Causation or Correlation: Explaining Hill Criteria using `xkcd`](https://www.kdnuggets.com/2017/02/hill-data-scientist-xkcd-story.html)."
    - It was inspired by Roger Peng and Hilary Parker's [Not So Standard Deviations podcast, Episode 28](http://nssdeviations.com/episode-28-writing-is-a-lot-harder-than-just-talking).
2. Then I'll ask you to tell me a little about how your review of Lab 0 went.
3. The Hormone Replacement Therapy Story
4. Tools for Assessing Causal Effects
5. Defining and Motivating the Propensity Score
6. Matching using the Propensity Score: The Key Ideas
7. Discussion of Rosenbaum, Chapters 1-2

## References from Today's Class

Articles posted on our [Sources page]([https://github.com/THOMASELOVE/500-2022/tree/main/sources](https://github.com/THOMASELOVE/500-classes-2023/tree/main/sources))

- Cochran WG 1968 [The Effectiveness of Adjustment by Subclassification in Removing Bias in Observational Studies](https://github.com/THOMASELOVE/500-classes-2023/tree/main/sources/articles/Cochran%201968.pdf) *Biometrics* 24, 205-213.
- Gum Patricia A Thamailarasan Maran Watanabe Junko et al. 2001 [Aspirin Use and All-Cause Mortality among Patients being Evaluated for Known or Suspected Coronary Artery Disease](https://github.com/THOMASELOVE/500-classes-2023/tree/main/sources/articles/Gum%202001%20JAMA%20Aspirin%20Use%20Propensity%20Analysis.pdf) *JAMA* 2001 286(10): 1187-1194.
- Riederer Emily 2021 [Causal design patterns for data analysts](https://emilyriederer.netlify.app/post/causal-design-patterns/) blog published 2021-01-31.
- Women's Health Initiative Writing Group 2002 [Risks and Benefits of Estrogen Plus Progestin in Healthy Postmenopausal Women: Principal Results From the Women's Health Initiative Randomized Controlled Trial](https://jamanetwork.com/journals/jama/fullarticle/195120) *JAMA* 2002; 288(3):321-333. doi:10.1001/jama.288.3.321

Other articles I refer to in the slides, if you're interested in tracking down further details...

- Barrett-Connor E Estrogen and estrogen-progestogen replacement: therapy and cardiovascular diseases. *Am J Med* 1993 Nov 30;95(5A):40S-43S. doi: 10.1016/0002-9343(93)90381-x. [PubMed](https://pubmed.ncbi.nlm.nih.gov/8256794/)
- Burkman RT Collins JA Greene RA Current perspectives on benefits and risks of hormone replacement therapy. *Amer J of Obstetrics and Gynecology* 2001 185 (2): S13-S23. [PubMed](https://pubmed.ncbi.nlm.nih.gov/11521117/)
- Col Nananda F Eckman MH Karas RH et al. Patient-specific decisions about hormone replacement therapy in postmenopausal women. *JAMA* 1997 Apr 9;277(14):1140-7. [PubMed](https://pubmed.ncbi.nlm.nih.gov/9087469/)
- Craig Michael C Maki Pauline M Murphy Declan G M The Women's Health Initiative Memory Study: findings and implications for treatment. *Lancet Neurol* 2005 Mar; 4(3): 190-4. doi: 10.1016/S1474-4422(05)01016-1 [PubMed](https://pubmed.ncbi.nlm.nih.gov/15721829/)
- Espeland Mark A Rapp Stephen R Shumaker Sally A et al. Conjugated equine estrogens and global cognitive function in postmenopausal women: Women's Health Initiative Memory Study. *JAMA* 2004 Jun 23;291(24):2959-68. doi: 10.1001/jama.291.24.2959. [PubMed](https://pubmed.ncbi.nlm.nih.gov/15213207/)
- Shumaker Sally A Legault Claudine Rapp Stephen R et al. Estrogen plus progestin and the incidence of dementia and mild cognitive impairment in postmenopausal women: the Women's Health Initiative Memory Study: a randomized controlled trial. *JAMA* 2003 May 28;289(20):2651-62. doi: 10.1001/jama.289.20.2651. [PubMed](https://pubmed.ncbi.nlm.nih.gov/12771112/)
- Shumaker Sally A Legault Claudine Kuller Lewis et al. Conjugated equine estrogens and incidence of probable dementia and mild cognitive impairment in postmenopausal women: Women's Health Initiative Memory Study. *JAMA* 2004 Jun 23;291(24):2947-58. doi: 10.1001/jama.291.24.2947. [PubMed](https://pubmed.ncbi.nlm.nih.gov/15213206/)
- Stampfer MJ Willett WC Colditz GA et al. A prospective study of postmenopausal estrogen therapy and coronary heart disease. *N Engl J Med* 1985 Oct 24;313(17):1044-9. doi: 10.1056/NEJM198510243131703. [PubMed](https://pubmed.ncbi.nlm.nih.gov/4047106/)
- Stampfer MJ Colditz GA Willett WC et al. Postmenopausal estrogen therapy and cardiovascular disease. Ten-year follow-up from the nurses' health study. *N Engl J Med* 1991 Sep 12;325(11):756-62. doi: 10.1056/NEJM199109123251102. [PubMed](https://pubmed.ncbi.nlm.nih.gov/1870648/)
- Yaffe K Sawaya G Lieberburg I Grady D Estrogen therapy in postmenopausal women: effects on cognitive function and dementia. *JAMA* 1998 Mar 4;279(9):688-95. doi: 10.1001/jama.279.9.688. [PubMed](https://pubmed.ncbi.nlm.nih.gov/9496988/)
- Zandi Peter P Anthony James M Hayden Kathleen M et al. 2002 Reduced incidence of AD with NSAID but not H2 receptor antagonists: the Cache County Study. *Neurology* 2002 Sep 24;59(6):880-6. doi: 10.1212/wnl.59.6.880. [PubMed](https://pubmed.ncbi.nlm.nih.gov/12297571/)

# Reminders / What Should I Be Working On?

1. [Lab 1](https://thomaselove.github.io/500-2023/lab1.html) due Wednesday 2023-02-01 at 7 PM to [Canvas](https://canvas.case.edu).
    - Here are the R packages I used to build my answer sketch for Lab 1, not counting the xfun package which I used only to present the session information.
        - broom, janitor, knitr, mosaic, naniar, rsample, simputation and tidyverse
2. Rosenbaum: Read Chapter 3 for our next class
3. It's not too early to start thinking about:
    - claiming an [Observational Studies In Action](https://thomaselove.github.io/500-2023/osia.html) article (due 2023-02-15)
    - developing a [project proposal](https://thomaselove.github.io/500-2023/proj500.html) and identifying an available data set (initial draft due 2023-02-22)

## Shameless Promotion: The Play That Goes Wrong 

[The Play That Goes Wrong at Aurora Community Theatre](https://www.auroracommunitytheatre.com/) starts its run tomorrow (Friday) night and continues through 2023-02-18. Thanks for putting up with these reminders. Come, if you like, but buy your tickets in advance if at all possible. [Here's the video promoting the show](https://conta.cc/3R5WGCJ).
