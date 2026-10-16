# Methodology items to resolve

1. Document dataset source, licence, sample size, collection process, target meaning, and feature definitions.
2. Verify the encoding and meaning of `Gender`, `EducationLevel`, and `RecruitmentStrategy`.
3. Choose and document a missing-value strategy; the notebook currently reports missingness but does not resolve it.
4. Review preprocessing and use suitable categorical encodings; fit transformations on training data only.
5. Explain whether `Gender` is included as a predictor or retained only for auditing, based on the research question.
6. Report class balance and assess robustness beyond one train/test split.
7. Define fairness metrics and explain their relevance to recruitment.
8. Justify or replace the custom bias score and thresholds; do not describe them as an established standard without evidence.
9. Report group sample sizes, uncertainty, limitations, and metric trade-offs.
10. Do not treat accuracy or fairness metrics alone as proof of ethical acceptability.
