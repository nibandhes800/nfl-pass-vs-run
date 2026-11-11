NFL 2024 Pass vs Run: A Hypothesis Test on EPA per Play

A statistical comparison of pass and run plays in the 2024 NFL season. It asks whether the small average edge for passing is real, how big it is, and whether it holds by down and distance.

Question

Is a pass play really more efficient than a run play, or is the gap just chance?

Data

NFL 2024 play by play data from nflverse (the same file as my Project 1). I kept run and pass plays that have an EPA value: 35,050 plays (20,007 pass and 15,043 run).

EPA (expected points added) measures how much a play changes the offense's expected points. Success is a yes or no outcome for each play.

The data file is about 100 MB, so it is not included in this repo. Download the 2024 play by play data from nflverse and set the file path in the notebook.

Method
Compared mean EPA by play type
Welch two sample t test on EPA
95% confidence interval for the gap
Chi square test on success rate
Effect size (Cohen's d)
Repeated the t test by down, with a Bonferroni corrected cutoff of 0.0125
Checked the average yards to go for run and pass plays on 3rd and 4th down
Compared pass and run on 3rd down within distance groups
Charted mean EPA by down
Findings
Pass plays averaged 0.025 EPA per play and run plays averaged -0.009, a gap of 0.034. The Welch t test gave t = 2.402 and p = 0.016, so the gap is unlikely to be luck.
The 95% confidence interval for the gap is 0.006 to 0.062 EPA per play.
Effect size is tiny: Cohen's d = 0.025, well below the 0.2 line for a small effect.
Pass plays succeeded 44.9% of the time and run plays 42.7%. The chi square test gave p = 0.00005.
The overall result hides opposite results by down. Pass leads on 1st and 2nd down, and run leads on 3rd and 4th down. All four differences are significant after the correction.
Run plays on 3rd and 4th down happen at shorter distances (4.90 against 7.74 yards on 3rd down, and 1.66 against 5.16 on 4th down).
On 3rd down, run plays still have higher mean EPA than pass plays within each distance group (1 to 3, 4 to 6 and 7 plus yards). I compared averages only and did not test significance within groups.

Mean EPA per play by down

Limitations
Plays in the same game are not fully independent.
Teams choose pass or run based on the situation, so these results show an association, not that one play type causes better results.
I controlled for distance only. Score, field position, opponent and the exact play call are not controlled.
Some groups are small, for example 4th down (488 pass and 327 run plays).
One season only.
Possible next steps

Use a regression to control for distance, field position, score and quarter at the same time, and add more seasons.

Tools

Python, pandas, SciPy, Matplotlib, Jupyter

Files
`project2-Pass_vs_Run.ipynb`: the analysis notebook
epa_by_down.png: the chart
README.md: this file