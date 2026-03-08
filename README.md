# Data Anonymization Using K-Anonymity and L-Diversity with ARX

This project explores privacy-preserving data publishing techniques by applying **K-Anonymity** and **L-Diversity** to a financial dataset using the **ARX Data Anonymization Tool**. The study aims to evaluate how different anonymization techniques reduce the risk of re-identification while maintaining data utility.

## Background

In the era of big data, organizations often need to share datasets for analysis while ensuring the privacy of individuals. However, sensitive attributes within datasets can potentially reveal personal identities when combined with other information.

To address this issue, privacy-preserving techniques such as **K-Anonymity** and **L-Diversity** are used to anonymize datasets while maintaining analytical value.

This project evaluates the effectiveness of these two methods using the **Bank Marketing dataset**.

## Objectives

The objectives of this project are:

- To implement **L-Diversity** and **K-Anonymity** for privacy protection.
- To analyze the **risk of re-identification** before and after anonymization.
- To compare the **impact of both methods on data utility and privacy protection**.
- To understand how anonymization techniques balance **privacy and data usability**.

## Dataset

The dataset used in this project is the **Bank Marketing dataset**, which contains demographic and interaction information of bank customers.

Some attributes are categorized as:

### Quasi Identifiers
Attributes that may identify individuals when combined:

- Age
- Job
- Education

### Sensitive Attributes

Attributes that must be protected due to their sensitive nature:

- Deposit
- Balance
- Default

These attributes contain financial information that could expose personal details if not properly anonymized.

## Methodology

The anonymization process was conducted using the **ARX Data Anonymization Tool**.

### 1. L-Diversity

L-Diversity ensures that each equivalence class contains at least **l different values** of sensitive attributes.

Configuration used:

- Model: **Distinct L-Diversity**
- Parameter: **l = 2**
- Sensitive attributes: `deposit`, `balance`, `default`

Results show that the dataset already satisfies the L-Diversity requirement **without requiring additional generalization**, meaning the sensitive attributes already have sufficient diversity.

### 2. K-Anonymity

K-Anonymity ensures that each record is indistinguishable from at least **k − 1 other records**.

Configuration used:

- Parameter: **k = 5**
- Quasi-identifiers: `age`, `job`, `education`

To achieve K-Anonymity, the ARX tool applied **generalization**, particularly on the **education attribute**, to ensure that each equivalence class contains at least five records.

## Results

### L-Diversity

- The dataset satisfied **L-Diversity (l = 2)** without generalization.
- Information loss: **0%**
- Data utility remained **very high**.
- Sensitive attributes already had sufficient variation.

### K-Anonymity

- The dataset required **generalization on the education attribute**.
- Highest prosecutor risk decreased from **100% to 20%**.
- All **unique record patterns were eliminated**.
- Data utility slightly decreased due to generalization.

## Comparison

| Aspect | L-Diversity | K-Anonymity |
|------|------|------|
| Generalization | Not required | Required (education attribute) |
| Privacy protection | Protects attribute disclosure | Protects identity disclosure |
| Information loss | 0% | Slight increase |
| Data utility | Very high | Slightly reduced |

L-Diversity provides strong protection for sensitive attributes, while K-Anonymity reduces the risk of identity re-identification by enlarging equivalence classes.

## Conclusion

Both **L-Diversity** and **K-Anonymity** play important roles in privacy-preserving data analysis.

- **L-Diversity** maintained the original dataset structure while protecting sensitive attributes.
- **K-Anonymity** significantly reduced re-identification risk but required slight data generalization.

The results demonstrate that combining multiple anonymization techniques provides a better balance between **data privacy and analytical usability**.

## Tools Used

- ARX Data Anonymization Tool
- Python (for data preparation)
- Bank Marketing Dataset

## Repository Structure
