
# Econometrics

## Literature Review

A review of the existing literature is can occur in the form of a _rapid literature review_, which, as the name suggests is conducted over a very short period of time. For larger, longer term projects, it may be desirable to conduct a more thorough review of the literature. There are three main goals when conducting a review of the literature:

1. Summarize and analyse previous research, theories and analytical approaches
2. Identify contested areas or conflicting findings
3. Highlight gaps within the literature

The literature review is important as it can help inform the analytical approach (e.g. what econometric model, what other factors need to be controlled for etc). Furthermore, it can provide a means to quality assure your analysis through a simple sense check, for example checking whether your findings are in alignment with, or contradictory to the majority of existing literature.

Some resources for accessing academic journals are as follows:

- OpenAthens: You can register an OpenAthens account through the National Institute for Health and Care Excellence (NICE) 
- EconLit: Members and Associate Members (e.g. NHSE) of the Government Economics Service (GES) receive free access to [EconLit Journal Access](https://members.ges.gov.uk/your-career/your-continued-professional-development/core-resources-and-guidance/ebsco/). Note this is only open those with an Economics degree and working in the Economics profession.

## Theoretical and conceptual frameworks

## Hypothesis identification

## Modelling

## Robustness checks

## Analysing and reporting outputs

### Statistical significance

The use of special characters to represent the statistical significance level within a regression output, for example `*`, `**` and `.`, is common practice within research. As there may be slight variations how these are reported across various analytical platforms and packages, the following definitions are recommended to avoid confusion. When communicating results to less technical audiences, we may also wish to phrase the significance level in words, which are also presented below.

| p value | representation | text representation |
| :---: | :---: | :--- |
| p < 0.001 (p<0.1%) | `***` | strongly significant |
| p < 0.01 (p<1%) | `**` | strongly significant |
| p < 0.05 (p<5%) | `*` | strongly significant | 
| p < 0.1 (p<10%) | `.` or `+` | weakly significant |

###  Guide to interpreting regression coefficients

| model | variable | relationship|  description | interpretation |
| :--- | :--- | :--- | :--- | :--- |
| Linear (OLS) | $$ \beta_x $$ | linear-linear | $\\x$ is not a proportion/share | All things equal, a **1 unit** increase in $\\x$ is _associated_ with a $\\\beta_x$ increase in $\\y$ | 
| Linear (OLS) | $$ \beta_x $$ | linear-linear | $\\x$ is a proportion/share | Where $\\x$ is a proportion/share, a **1 percentage point** increase in $\\x$ is _associated_ with a $\frac{\beta_x}{100}$ increase in $\\y$ |
| Linear (OLS) | $$ log(\beta_x) $$ | linear-log | $\\x$ is not a proportion/share | test | 
| Linear (OLS) | $$ log(\beta_x) $$ | linear-log | $\\x$ is a proportion/share | test |
| Generalized Linear - Poisson/Negative Binomial count models with log-link | $$ \beta_x $$ | log-linear | $\\x$ is not a proportion/share | All things equal, a **1 unit** increase in $\\x$ is _associated_ with a $\\\beta_x$ increase in the log of the ratio of expected counts ***or*** a **1 unit** increase in $\\x$ is _associated_ with a $\\(exp(\beta_x)-1)*100\%$ increase in the **rate** of $\\y$ |
| Generalized Linear - Poisson/Negative Binomial count models with log-link | $$ \beta_x $$ | log-linear | $\\x$ is a proportion/share | All things equal, a **1 percentage point** increase in $\\x$ is _associated_ with a $\frac{\beta_x}{100}$ increase in log of the ratio of expected counts ***or*** a **1 percentage point** increase in $\\x$ is _associated_ with a $\\(exp(\frac{\beta_x}{100})-1)*100\%$ increase in the **rate** of $\\y$ |

### Control variables

Frequently, reporting of results from an econometric analysis will focus around one, or a few main _variables of interest_. It is however important, and may raise interesting findings from a policy perspective, to review findings from _all_ variables, including controls within the model. It is recommended that regression outputs are either **tabulated** into an Excel/CSV document, or **visualized using coefficient plots**.

Example: tabulating regression outputs into a csv in R

```r
# install if necessary, or load the broom package
if(!require('broom')) install.packages('broom')
model <- lm(data=df,formula=y~x1+x2+x3+x4)
modelOutput <- broom::tidy(model)
write.csv(modelOutput,here('outputs/model_output.csv'))
```

Example: creating a simple coefficient plot using `ggplot2` in R

```r

```