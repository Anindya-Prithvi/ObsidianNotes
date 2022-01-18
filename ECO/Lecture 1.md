# First lecture
This is day 2, first lecture of econometrics. The professor is pretty chill. The pre-requisite is Probability and Statistics course. No recording however multiple office hours. Note from professor: Read the course book, it's very good! Motivation to study? High demand field. The course would again revolve around data analysis like PB.

## Course evaluations and reference
- Quiz/Assignments : 20%
- Project : 20%
- Midsem : 25%
- Endsem : 35%
- Introductory econometrics: A modern approach (4th edition, Cengage India) by Jeffery L. Wooldridge

## What is Econometrics
- An envelope of methods to formally
	- Evaluate a govt. or business policy
		- E.g. job training program
		- impact of plagiarism/odd-even policy
	- Test a simple economic theory
		- E.g. Diversification of risks (stonks)
		- Minimum legal wages reduces an individual's prosperity
	- Estimate a simple economic (or even social) relationship
		- E.g. partisan political events increase the number of posts on Twitter
		- higher minimum wages reduce crime rate of city

## A (vague) econometric model
$$y_{[]} =\beta_0+ \beta_1x_{1[]}+\beta_2x_{2[]}+\dots+\beta_kx_{k[]}+u_{[]}$$
where
- $y_{[]}$ is the dependent/explained/predicted response
- $x_{[]}$ is the $k$*th* regressand/explanatory variable/control/predictor/regressor/covariate for unit [],
- $\beta_0$ is the intercept,
- $\beta_k$ is the coefficient of $x_{k[]}$, also termed as slope (multi-dim)
- $u_{[]}$ is the disturbance/error or bias term

## Data Structures
- Cross-sectional data
	- Observation units are individual or entities like persons, states, etc.
	- Variables _height{i}_, _income{i}_
- Time-series data
	- Observation units is time.
	- Variables _gdp{t}_, _runtime{t}_
- Panel or longitudinal data
	- Multiple entries are observed over multiple time-periods.
	- Variable height of a hundred 8<sup>th</sup> graders over 20 years, i.e. _height{i,t}_.

## Causality versus Correlation
- The notion of Ceteris Paribus or _all else held constant_
- Consider $wage_i=\beta_0+\beta_1educ_i+\epsilon_i;i\in\mathbb{N}$
- Can we really *say* that the above equation implies a **causal impact** of education status on wage? Consider the following:  
$$ educ_i = \dfrac{\beta_0}{\beta_1}+\dfrac{1}{\beta1}wage_i - \dfrac{\epsilon_i}{\beta_1}$$