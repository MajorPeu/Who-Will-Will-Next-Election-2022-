# 🗳️ Who Will Win the Next Election? – STA304 Assignment 2 (Fall 2022)

**Author:** Peush Gomes  
**Course:** STA304 – Fall 2022  
**Date Submitted:** November 24, 2022  

## 📌 Project Overview

This project investigates whether any Canadian province is likely to have at least half of its population vote for the Liberal Party in the next federal election. Using 2019 Canadian Election Study data as a sample and the 2013 General Social Survey as a pseudo-census, a logistic regression model was built and then post-stratified to generate province-level predictions.

---

## 🔍 Research Question

**Do any of the Canadian provinces have at least 50% of the vote share projected to go to the Liberal Party?**

---

## 📊 Data Sources

- **Survey Data:** 2019 Canadian Election Study (CES)  
  - Conducted via phone interviews (both mobile and landline) between September–October 2019.
  - Key variables: age, sex, province, marital status, Canadian-born status, and vote choice (Liberal or not).

- **Census Data:** 2013 General Social Survey (GSS)  
  - Interviewed Canadians over 15 via CATI or online questionnaires between June 2013 and March 2014.
  - Used for post-stratification across population-level demographic cells.

---

## ⚙️ Methodology

1. **Modeling:**
   - A logistic regression model was built using the CES 2019 data to predict `vote_liberal` (1 = Liberal, 0 = otherwise).
   - Predictors included: age, sex, province, place of birth, and marital status.

2. **Model Equation:**

   \[
   \log\left(\frac{p}{1 - p}\right) = \beta_0 + \beta_1(\text{Age}) + \beta_2(\text{Male}) + \cdots + \beta_{16}(\text{Widowed})
   \]

3. **Post-Stratification:**
   - Predictions from the logistic model were weighted using population frequencies from the GSS dataset.
   - Estimates were computed per province to approximate national vote distribution trends.

---

## 📈 Results Summary

| Province               | Sample Size | Liberal Vote Proportion |
|------------------------|-------------|--------------------------|
| Alberta                | 1708        | 0.085                    |
| British Columbia       | 2509        | 0.221                    |
| Manitoba               | 1180        | 0.235                    |
| New Brunswick          | 1318        | 0.211                    |
| Newfoundland & Labrador| 1086        | 0.287                    |
| Nova Scotia            | 1412        | 0.284                    |
| Ontario                | 5585        | 0.344                    |
| Prince Edward Island   | 697         | 0.301                    |
| Quebec                 | 3804        | 0.249                    |
| Saskatchewan           | 1147        | 0.140                    |

**Key Takeaway:**  
None of the 10 provinces are predicted to have at least 50% support for the Liberal Party. Ontario leads with 34.4%, while Alberta shows the lowest projected support at 8.5%.

---

## 📚 Conclusions

- The hypothesis that at least one province would have a majority Liberal vote was **rejected**.
- While provinces like Ontario and the Maritimes were expected to show stronger support, results indicated otherwise, possibly due to model limitations or sample bias.
- Future work should explore additional models, incorporate data from more recent elections, or adjust for underrepresented groups.

---

## 🧪 Tools Used

- R version 4.0.2  
- Libraries: `tidyverse`, `ggplot2`, `glm()` for logistic regression

---

## 📖 References

1. Grolemund, G. (2014). *Introduction to R Markdown.* [rmarkdown.rstudio.com](https://rmarkdown.rstudio.com/articles_intro.html)  
2. Dekking, F. M., et al. (2005). *A Modern Introduction to Probability and Statistics.* Springer.  
3. Allaire, J.J., et al. *R Markdown Documentation.* [rmarkdown.rstudio.com/docs](https://rmarkdown.rstudio.com/docs/)