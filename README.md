# BMCM 2024

## Primary Strategy
- Build weighted interaction digraph between teams, with edge weights representing performance in a given game (e.g. margin of victory)
- Use a weighted version of PageRank algorithm to determine win probabilities for each team if two teams were randomly selected to play each other (odds ratio)
- Use RANSAC algorithm to drop outlying games (i.e. luck-determined games) to make PageRank approach robust
- Compute RANSAC threshold based on the mean (over teams) of (mean **absolute** difference in skill according to PageRank with and without a particular game) -- we can assume normality with CLT, apply Chebyshev's inequality to define outliers
- Use graph of RANSAC inliers to compute relative skill metrics on network of teams
- Track and characterize "luck"-determined games (i.e.RANSAC outliers) &rarr; with more features, potentially predict these games

## Considerations:
- Stratify season into several periods &rarr; Account for potential variability in performance over time due to injuries, etc.
- Consider offensive and defensive performance separately
- Normalize skill levels when entering the championship tournaments and NCAA tournament? Normalize so that skill is evenly distributed amongst different conferences/regions?

## Data
- Main dataset provided by competition
- Additional data
    - CBB dataset [here](https://www.kaggle.com/datasets/andrewsundberg/college-basketball-dataset?resource=download)
    - NCAA dataset [here](https://www.kaggle.com/datasets/ncaa/ncaa-basketball?select=mbb_historical_teams_games)




