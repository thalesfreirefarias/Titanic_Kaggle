# Titanic_Kaggle
Titanic Project using SQL

![GitHub repo size](https://img.shields.io/github/repo-size/iuricode/README-template?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/iuricode/README-template?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/iuricode/README-template?style=for-the-badge)
![Bitbucket open issues](https://img.shields.io/bitbucket/issues/iuricode/README-template?style=for-the-badge)
![Bitbucket open pull requests](https://img.shields.io/bitbucket/pr-raw/iuricode/README-template?style=for-the-badge)

---

### Project Introduction 
By analyzing the Titanic dataset, I aim to identify the key factors that influenced passenger survival during the disaster.
The analysis focuses on variables such as gender, passenger class, age, and embarkation point to understand patterns and differences in survival rates.

The goal of this project is to apply SQL queries to extract meaningful insights and simulate real-world data analysis scenarios, supporting data-driven conclusions.

Data Quality Note: Missing values were identified in the Age and Cabin columns. These were considered during the analysis, with null values handled appropriately to avoid distortion in the results.

---


### How many passengers are in the Titanic dataset?

```
Select count(*) from TitanicDataset;
```

The Titanic dataset contains 891 passengers.

---
### How many passengers survived and did not survive?

```
SELECT survived, COUNT(*) as total
FROM TitanicDataset
GROUP BY survived;
```

In this dataset:

0 = did not survive
1 = survived

A total of 549 passengers did not survive, while 342 survived.

<table>
  <tr>
    <td align="center">
      <a href="#" title="Age">
        <img src="1.png" width="1000" alt="Titanic Survived"/><br>
      </a>
    </td>
  </tr>
</table>

---

###  What is the percentage of survivors?

```
SELECT 
    survived,
    COUNT(*) AS total,
    ROUND(
        COUNT(*) * 100.0 / SUM(COUNT(*)) OVER(),
        2
    ) AS porcentagem
FROM TitanicDataset
GROUP BY survived;


```
38.62% survived
61.38% did not survive

----

### How many men and women were on the Titanic?
```
SELECT sex, COUNT(*) as total
FROM TitanicDataset
GROUP BY sex


```
Approximately 64.76% of the passengers were male.
---

### How many passengers embarked at each port?
```
select embarked, COUNT(*) 
from TitanicDataset
as total
group by embarked;
C 168 (France) Rich 
Q  77 (Newzeland) poor
S 644 (England) General
nULL 2

```
C (Cherbourg, France): 168 passengers
Q (Queenstown, Ireland): 77 passengers
S (Southampton, England): 644 passengers
NULL: 2 passengers (missing data)

---

### How many survived by gender?
```
SELECT 
    sex,
    survived,
    COUNT(*) AS total,
        ROUND(
        COUNT(*) * 100.0 / SUM(COUNT(*)) OVER(),
        2
    ) AS porcentagem
FROM TitanicDataset
GROUP BY sex, survived
ORDER BY sex, survived;
```
Approximately 342 survived
---

Qual a quantidade de sobreviventes por gênero?
Qual a taxa de sobrevivência por gênero (%)?
Quantos passageiros existem por classe (pclass)?
Qual a taxa de sobrevivência por classe (%)?
Qual a média de idade dos passageiros?


### Adjustments and improvements.

The project is still under development, and the upcoming updates will focus on the following tasks:

- [x] Advanced courses about SQL

The following tools were used in the construction of the project:

- [SQL](<[https://www.python.org/doc//](https://sqliteonline.com/)>)
- [Google colab](<https://colab.google/>)



## 🤝 Creator

<table>
  <tr>
    <td align="center">
      <a href="#" title="Thales Farias">
        <img src="grecia.jpg" width="100" alt="Foto do Thales Farias no GitHub"/><br>
        <sub>
          <b><a href="https://www.linkedin.com/in/thalesfreirefarias/" target="_blank">Thales Farias</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

